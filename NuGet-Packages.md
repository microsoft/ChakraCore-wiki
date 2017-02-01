NuGet packages are a convenient way to provide developers with official builds of our project
as well as enabling development against our binaries.

See [our plans for NuGet (#85)](https://github.com/Microsoft/ChakraCore/issues/85)
for more info about upcoming changes.

# NuGet Feed (Stable Builds)

Official NuGet packages are available on the [Microsoft.ChakraCore NuGet Feed](https://www.nuget.org/packages/Microsoft.ChakraCore).

# MyGet Feed (Preview Builds)

Preview NuGet packages will be available on the [Microsoft.ChakraCore MyGet Feed](https://www.myget.org/feed/chakracore-preview/package/nuget/Microsoft.ChakraCore).

_**Disclaimer:** Packages published to the MyGet feed are for preview purposes only. For these packages, we make no guarantees (other than best-effort) about quality, performance, or otherwise. Additionally, these packages may expire and be deleted without notice; therefore, we do not recommend taking a dependency on these packages as you develop your application._

# Grabbing Preview Binaries from NuGet Packages

NuGet packages are `.zip` files with a `.nuget` extension, so to extract files
from a NuGet package, simply rename the file from `ChakraCore.nuget` to `ChakraCore.zip`,
then you can open the file in your favorite zip file browser and extract the appropriate binaries
for your system architecture. Currently supported: `x64` and `x86`.

The contents of the package at present (subject to change):

```
arm
    ch.exe
    ch.pdb
    ChakraCore.dll
    ChakraCore.pdb
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
to be automatically included in a project via NuGet.

We have plans to enable this as soon as it is viable.
