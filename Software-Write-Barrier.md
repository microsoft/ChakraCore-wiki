
## Introduction
The chakra implementation of concurrent GC do rescan the dirty pages to determine the newly added rooted objects during initial scan/mark. 
- On windows, the OS kernel provides a feature called Write Watch( we also call it hardware write barrier), which the system keeps track of the pages that are written to in the committed memory region. ChakraCore GC use this information to determine which pages are dirty and do rescan/mark on them. 
- On non-Windows platform the hardware write barrier is not available, so we use software write barrier to track the dirty pages. 

In implementation of software write barrier ChakraCore uses a card table to map the whole address space, every page in the process has one byte in the card table corresponding to it. And all the recycler allocated non-Leaf struct have smart pointer wrapped to all its recycler pointer fields, while updating the pointer field, the smart pointer will update the corresponding byte in the card table which marking the page as dirty. 

The key to make the software write barrier work correctly and stably is to make sure all necessary pointer fields are annotated with the smart pointer correctly. In order to achieve this, here's a few coding rules to obey:

## Coding Rules

1. Annotate all fields recycler allocated struct/class with "Field" macro like below. Please also annotate non-pointer as well, it is a no-op for now but can use to provide more information for precised GC in the future. If you believe a pointer field will not be pointing to recycler memory, or, if it's pointing to recycler memory but the target recycler memory lifetime is tracked specifically on another struct/class, you can explicitly mark this field with FieldNoBarrier, while won't do barrier bit updating while modifying this field.
    ```c++
        struct A
        {
            Field(int)              intField;
            Field(int*)             intArray;
            Field(Var)              aVar;
            Field(Field(Var)*)      varArray;
            FieldNoBarrier(Recycler*)   recycler; // e.g: recycler is heap allocated
        }
    ```

2. If your function receive a recycler pointer to update, please wrap the parameter with Field
    ```c++
        void UpdateSlot(Field(Var)* slots, int idx)
        {
            slots[idx] = RecyclerNew(...);
        }
    ```

3. Use PointerValue() to cast a Field(T\*) to T\*, PointerValue() retrieves the pointer from "Field(T\*)" type, no matter it is wrapped in smart pointer or not.

4. Try the best to avoid 'plus Array' at the end of structure, if that's really necessary make sure #2 above is applied, also make sure the 'plus Array is annotated as Field(T*) [], eg:
    ```c++
        class ConcatStringMulti
        {
            ...
            Field(uint) slotCount;
            Field(JavascriptString*) m_slots[];   // These contain the child nodes.
        };
    ```

5. In the initialization list of constructor, if you have a write barrier pointer need to be initialized as null, use nullptr instead of NULL or 0. There's special overload to avoid unnecessary barrier update in this case.

6. If you are going to add a global static instance of annotated structure, please design a special contructor to avoid updating barrier bits. This is because on x64 the card table is not initialized for the image. See FunctionInfo structure as an example.


## Clang Plugin
In linux build, there is a clang plugin to help preventing missing annotations, if you hit build error in CI please do following

- TBD

## Test Utilities
Other than the plugin, there's runtime flags to help check if there's missing barrier. 
- You can run test with -VerifyBarrierBit switch. This records every write barrier pointer update, and do the verification during marking or verifying mark
- You can additionally add "-RecyclerConcurrentStress -RecyclerVerifyMark" switches to make the issue easier to appear.
- You can also additionally add -KeepRecyclerTrackData, which saves more tracking info to help the debugging.
But to be noticed both -VerifyBarrierBit and -RecyclerVerifyMark can report false positives.

If would like to test this with windows, run "jenkens\buildone.cmd x64 debug swb" to build the bits, the result will be under Build\VcBuild.SWB\

