The humble JS string is simple to use, but there is a lot of complexity under the hood to make it fast. This page explains the differences between the internal types that we use to represent strings.

# Operations on strings

If you look at JavascriptString.h you'll find a plethora of methods, but for now we'll just focus on a few important ones which are relevant to the distinctions between string classes.

## GetString

A JS string is fundamentally just a sequence of UTF-16 code points. This method returns a pointer to the beginning of that sequence. Note that the data returned this way is **not** necessarily null-terminated, and **can** have null characters within it, so you pretty much always want to pair this method with GetLength so you know how long the data is. The data pointed to by the result of GetString is valid as long as you hold a reference to the JavascriptString itself (or at least until something causes the string to change type, more on that later).

## GetSz

The evil twin of GetString. Sz is Windows-speak for **S**tring of 16-bit characters that is **Z**ero-terminated. This is just like GetString but with an extra guarantee that the character after the end is zero. This can sometimes make the string do extra allocation (as we'll see shortly), and encourages us to write code that would fail on strings that have null characters within, so avoid it when possible.

## CloneToScriptContext

Every JS object needs to specify how it is copied to a different script context (iframe, to web developers), and strings are no exception.

# Types of string

## LiteralString

This is the simplest form of string. It just has a pointer to its data, which must be null-terminated, and a length. GetString and GetSz can return the pointer directly.

LiteralString has an extra piece of semantic meaning, which is asserted in its constructor: the string data must be static or recycler-allocated. This means that when we need to clone one of these strings to a different script context, we can create a new LiteralString object pointing to the same buffer. All script contexts in a thread context (page, to web developers) share a recycler, so the new string object can keep the data alive.

## SingleCharString

This type has two characters of data (one for the character, and one null) directly within the object. This allows us to avoid allocating a separate buffer for the string data. GetString and GetSz return a pointer to where the data is held within the SingleCharString object.

SingleCharStrings are held in a CharStringCache (one per script context). When cloning to a different script context, we ask the CharStringCache in the destination context to get or create a SingleCharString as necessary.

## PropertyString

A PropertyString contains extra data to speed up getting, setting, or querying properties with the `[]` and `in` operators. It contains a cache of a few recently-accessed object types and where to find the property whose key matches this string on that type. `Symbol` objects (JavascriptSymbol internally) have the same cache data.

A PropertyString holds a pointer to a PropertyRecord. The PropertyRecord contains the actual string data, null terminated, within it, so GetString and GetSz on PropertyString return a pointer to the place within the PropertyRecord where the string data is stored.

PropertyRecords are tracked in a hash table on the ThreadContext, and shared among all script contexts in that ThreadContext. PropertyStrings are stored in a dictionary per ScriptContext. When cloning a PropertyString to a different ScriptContext we can ask the destination ScriptContext to get or create a PropertyString for the given PropertyRecord. This may create a new PropertyString instance, but will always reuse the underlying PropertyRecord.

If PropertyStrings are so fast, why would we ever have LiteralStrings? Well, all of that cache data comes at a memory cost, which can actually slow things down because many strings are never used as property keys. We have some heuristics in the parser to guess which strings might end up getting used as property keys and allocate them as PropertyStrings, but it's imperfect. For cases when we're not sure, there is...

## LiteralStringWithPropertyStringPtr

This type is only a little bigger than LiteralString (an extra 16 bytes on x64), but allows us to get some of the benefits of a PropertyString if the string ends up getting used as a property key. It starts out just like a LiteralString, with a buffer and a length. After it is used once as a property key, it remembers its corresponding PropertyRecord and updates its data pointer to point to the string data in the PropertyRecord. If it used as a property key a second time, it asks the ScriptContext for a PropertyString instance and remembers that pointer too. Any further operations can use the PropertyString optimizations, at the cost of one extra indirection.

GetString and GetSz return either the literal buffer or the buffer in the PropertyRecord, depending on whether the string has a PropertyRecord yet.

When cloning to another script context, LiteralStringWithPropertyStringPtr doesn't create another LiteralStringWithPropertyStringPtr. It either asks for a PropertyString, if the PropertyRecord already exists (indicating that this string was used as a property key, so PropertyString is probably the best choice), or otherwise it creates a plain LiteralString.

## SubString

This string type is returned by the Javascript string operations `substr`, `substring`, and `trim`. It has two pointers: one to its string data (somewhere within the data of another string), and one to the thing owning that string data, so the recycler doesn't collect away the string data.

GetString can directly return the data pointer. GetSz, when called for the first time, must make a new copy of the data so it can append a null character.

When cloning to another script context, we first run GetSz to get a recycler-allocated buffer, and then create a LiteralString in the destination context pointing to that buffer.

If a SubString is used as a property key, we swap out its vtable and turn it into a LiteralStringWithPropertyStringPtr.

## ConcatString

A ConcatString represents a fixed number of strings that have been added together. It keeps pointers to each source string. If somebody needs the string data (calls GetString or GetSz for the first time), a new buffer is allocated and filled with the data from each of the source strings. We call this operation finalization, at risk of great confusion with the recycler operation of the same name.

Like SubString, when cloning to another script context, we first run GetSz to ensure we have a recycler-allocated buffer, and then create a LiteralString in the destination context pointing to that buffer.

Also like SubString, if a ConcatString is used as a property key, we swap out its vtable and turn it into a LiteralStringWithPropertyStringPtr.

## CompoundString

CompoundString is pretty much like ConcatString, but used for adding together larger (and non-fixed) numbers of source strings. Everything else in the ConcatString section applies here.

## WritableString

This type is an eager alternative to ConcatString or CompoundString. It allocates a string buffer, writes some data into it, and then acts exactly like LiteralString.

## LazyJSONString

It's pretty common for the next step after a `JSON.serialize` to be a `JSON.parse` of the same data, without ever needing the actual string text. LazyJSONString keeps a simple representation of a serialized JSON tree, so if we need to parse it again we can quickly rebuild the object hierarchy. If the program requests the string data for a LazyJSONString (by calling GetString or GetSz), we allocate a string buffer, write it, and then throw away the JSON tree data.

Like SubString, when cloning to another script context, we first run GetSz to ensure we have a recycler-allocated buffer , and then create a LiteralString pointing to it in the destination context.
