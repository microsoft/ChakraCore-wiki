Our official releases and preview builds will be provided as NuGet packages.
These packages enable the community to preview our binaries as well as to easily develop against ChakraCore.


# NuGet Feed (Stable Builds)

Official NuGet packages are available on the [Microsoft.ChakraCore NuGet Feed](https://www.nuget.org/packages/Microsoft.ChakraCore).


# MyGet Feed (Preview Builds)

Preview NuGet packages will be available on the [Microsoft.ChakraCore MyGet Feed](https://www.myget.org/feed/chakracore-preview/package/nuget/Microsoft.ChakraCore).

_**Disclaimer:** Packages published to the MyGet feed are for preview purposes only. For these packages, we make no guarantees (other than best-effort) about quality, performance, or otherwise. Additionally, these packages may expire and be deleted without notice; therefore, we do not recommend taking a dependency on these packages as you develop your application._


# Using NuGet Packages Automatically

The NuGet packages contain all of the files necessary to automatically embed and develop against `ChakraCore.dll`.

For both Native and .NET projects, these files include `ChakraCore.dll` for each architecture and a `.props` or `.targets` file which is automatically consumed by VS's NuGet automation when you import a NuGet package into a project. For Native projects, the package also includes the necessary header files to develop against `ChakraCore.dll`.

.NET projects will need to implement a PInvoke layer to call into the native `ChakraCore.dll`.


# Manually extracting binaries from NuGet Packages

NuGet packages are `.zip` files with a `.nuget` extension, so to extract files
from a NuGet package, simply rename the file from `ChakraCore.nuget` to `ChakraCore.zip` and proceed to extract the files as with any other `.zip` file.

Refer to the source of the `.nuspec` files [located here](https://github.com/Microsoft/ChakraCore/tree/master/Build/NuGet) for the contents of the various packages.
