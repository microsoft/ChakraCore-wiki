NuGet packages are a convenient way to provide developers with official builds of our project
as well as enabling development against our binaries.

See [our plans for NuGet (#85)](https://github.com/Microsoft/ChakraCore/issues/85)
for more info about upcoming changes.

# NuGet Feed (Stable Builds)

_Coming soon! (Check back when we finalize the `release/1.2` milestone.)_

# MyGet Feed (Preview Builds)

For preview builds of our NuGet package, see the
[Microsoft.ChakraCore](https://www.myget.org/feed/chakracore-preview/package/nuget/Microsoft.ChakraCore)
MyGet Feed.

Currently, packages on the MyGet feed are built from the `release/1.2` branch.

We have plans to expand our preview packages to include any branches under active development
(such as `master`). Builds will be published daily, or as needed for slow-moving branches.

_**Disclaimer:** Packages published to the MyGet feed are for preview purposes only. For these packages, we make no guarantees (other than best-effort) about quality, performance, or otherwise. Additionally, these packages may expire and be deleted without notice, so we do not recommend taking a dependency on any particular version of these packages as you develop your application (although it should be reasonably safe to always develop against the latest preview version of the package)._

# Grabbing Preview Binaries from NuGet Packages

NuGet packages are `.zip` files with a `.nuget` extension, so to extract files
from a NuGet package, simply rename the file from `ChakraCore.nuget` to `ChakraCore.zip`,
then you can open the file in your favorite zip file browser and extract the appropriate binaries
for your system architecture. Currently supported: `x64` and `x86`.

The contents of the package at present (subject to change):

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
