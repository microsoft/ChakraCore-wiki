NuGet packages are a convenient way to provide developers with official builds of our project while enabling

See [our plans for NuGet (#85)](https://github.com/Microsoft/ChakraCore/issues/85).

# NuGet Feed (Stable Builds)

_Coming soon! (Check back when we finalize the `release/1.2` milestone.)_

# MyGet Feed (Preview Builds)

We publish preview builds of our NuGet package at the
[Microsoft.ChakraCore](https://www.myget.org/feed/chakracore-preview/package/nuget/Microsoft.ChakraCore)
MyGet Feed.

Currently, packages on the MyGet feed are built from the `release/1.2` branch.
We have plans to expand this to preview packages built from any branches under active development
(such as `master`). Builds are published regularly at a rate consistent with changes to the branch
(daily in active branches, perhaps less often in stabilization branches).

# Grabbing Preview Binaries from NuGet Packages

NuGet packages are .zip files with a different extension. To extract files from a NuGet package,
simply rename the file.

`rename ChakraCore.nuget ChakraCore.zip`

Then you can open the file in your favorite zip file browser and extract the appropriate binaries
for your system architecture (currently supported are x64 and x86).

```
x64
    ch.exe
    ch.pdb
    ChakraCore.dll
    ChakraCore.pdb
x86
    ch.exe
    ch.pdb
    ChakraCore.dll
    ChakraCore.pdb
```

# Using NuGet Packages Automatically

_Coming soon!_

Unfortunately, the **Microsoft.ChakraCore** package does not yet contain the necessary data
to make automatic inclusion of the Microsoft.ChakraCore in a project.

We have plans to enable this as soon as it is viable.
See [our plans for NuGet (#85)](https://github.com/Microsoft/ChakraCore/issues/85).
