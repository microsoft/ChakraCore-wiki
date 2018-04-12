Visit [[Getting ChakraCore binaries]] if you would simply like to download pre-compiled binaries.

## Windows ##

You can build ChakraCore on Windows 7 SP1 or above, and Windows Server 2008 R2
or above, with either Visual Studio 2015 or 2017, as long as C++ support is
installed[*](#build_for_arm).

Refer to the [Linux](#linux) and [OS X](#os-x) sections for building instructions on these platforms.

To build ChakraCore on Windows:

* Clone ChakraCore through ```git clone https://github.com/Microsoft/ChakraCore.git```
* Open ```Build\Chakra.Core.sln``` in Visual Studio.
* Select the target [Platform](#platform) and [Configuration](#configuration) and build the solution.
* Build output will be under ```Build\VcBuild\bin```.

Alternatively, run msbuild on the command line:
```
msbuild /m /p:Platform=... /p:Configuration=... Build\Chakra.Core.sln
```

### Platforms ###

ChakraCore on Windows can be built for 3 Platforms: ```x86```, ```x64``` and ```arm```.

<a name="build_for_arm">**Building for `arm`**:</a> Due to toolset dependency, you will need following to build for the `arm` platform:
* Visual Studio 2015
* [Windows 10 SDK (July 2015)](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)

### Configuration ###

ChakraCore on Windows supports 3 configurations:
* ```Debug```: Not optimized, with full runtime checks and all test hooks.
* ```Release```: Fully optimized, with fewer runtime checks and no test hooks.
* ```Test```: Optimized, very similar to ```Release``` but with more runtime checks and most test hooks.

### Deployment ###

If you use ChakraCore you will need to deploy ```ChakraCore.dll``` with your application. You may also need to redistribute MSVC runtime libraries because ChakraCore.dll has runtime dependency on MSVC libraries by default. For more information see [Redistributing Visual C++ Files](https://msdn.microsoft.com/en-us/library/ms235299.aspx).
* Note if you build with Visual Studio 2015: There are some new requirements due to universal CRT changes. See [Introducing the Universal CRT](http://blogs.msdn.com/b/vcblog/archive/2015/03/03/introducing-the-universal-crt.aspx).

Alternatively, you can build ChakraCore without MSVC runtime dependency. Pass an additional parameter to msbuild so that ChakraCore links to MSVC libraries statically:
```
msbuild ... /p:RuntimeLib=static_library ...
```

### Windows + ICU (Experimental) ###

ChakraCore on Windows has experimental integration with ICU on x86 and x64. You can choose to download and compile ICU using our helper scripts, provide your own ICU installation, or use the ICU SDK installed alongside the version 16299 or later of the Windows Kit. For any of these options, you will need to provide the `ChakraICU` parameter to `msbuild`, either on the command line (`/p:ChakraICU=value`) or through an environment variable (`set ChakraICU=value`). The possible values are discussed below.

#### Use Chakra helper scripts (Chakra.ICU) ####

To get started with Chakra.ICU, run `python tools\configure_icu.py <version>` from the ChakraCore root directory, where `<version>` is a version of ICU, like 57.1 or 60.2. You can run `python tools\configure_icu.py --help` to see all available configuration options. Running this script will download ICU to `%ChakraCoreRootDirectory%\deps\Chakra.ICU\icu` (by default) and will generate `%ChakraCoreRootDirectory%\deps\Chakra.ICU\Chakra.ICU.props`, which contains all of the files and source information for the given version of ICU in a MSBuild-compatible format.

To build the version of ICU that you just downloaded, you can set `ChakraICU` to `static` or `shared`; `static` links ICU statically into ChakraCore.dll, and `shared` creates `Chakra.ICU.Common.dll`, `Chakra.ICU.i18n.dll`, and `Chakra.ICU.Data.dll`. If you choose `shared`, you will need to redistribute the Chakra.ICU DLLs alongside ChakraCore.dll and the rest of your application.

_note_: When building with `shared`, you will recieve an MSBuild warning about mismatched target names. This is an unfortunate side effect of how both Chakra.ICU and ICU's own default build system works. This will eventually be fixed with the resolution of [#4755](https://github.com/Microsoft/ChakraCore/issues/4755).

_note_: This will use the default data file provided with the ICU source code download, located at `%ICURoot%\source\data\in\icudtXXl.dat`. If you want to customize the data file, you will need to provide your own ICU as described below, replace the default data file, or modify the build files.

#### Using the ICU SDK included with the Windows Kit ####

**Warning**: By enabling this option, you are limiting the range of operating systems that the produced ChakraCore.dll can run on. Normally, ChakraCore.dll can be redistributed back to Windows 7 machines with no modifications. When you enable Windows Kit ICU, the resulting ChakraCore.dll will only be able to run on Windows 10 version 15063 (RS2) or later.

To instruct ChakraCore to use the Windows Kit ICU, set `ChakraICU` to `windows`.

#### Bring your own ICU ####

Chakra also supports bringing your own ICU, in case you are already using it elsewhere in your application. To use this configuration, set `ChakraICU` to `external`, and pass `IcuVersionMajor=<number>`, `IcuIncludeDirectories=<folder(s)>`, and `IcuLibraryDependencies=<libs>` to MSBuild using either the command line or environment variable methods described above. The directory/directories passed to `IcuIncludeDirectories` must have all of the icuuc and icuin headers located within a `unicode` subfolder -- that is, if you pass `C:\ICU\`, then it is expected that headers like `uloc.h`, `udat.h`, etc are located in `C:\ICU\unicode\`.

## Linux ##

Steps below are tested on Ubuntu 16.04LTS and Fedora 24. In order to compile ChakraCore on other Linux distrubitions,
use distro's package manager instead of `apt-get` / `dnf` to install given dependencies below.

To build ChakraCore on Linux: (requires Clang 3.7+ and Python 2)

#### Installing build dependencies ####

##### Dependencies - Centos / Fedora (or similar) #####
```
su
dnf group install -y "Development Tools" "C Development Tools and Libraries"
dnf install -y git cmake clang gcc gcc-c++ kernel-devel python llvm
dnf install -y libuuid-devel lttng-ust-devel.x86_64 libicu-devel.x86_64
dnf install -y libstdc++-static.x86_64
```

##### Dependencies - Debian/Ubuntu (or similar) #####
```
su
apt-get update
apt-get dist-upgrade
apt-get install -y git build-essential cmake clang libicu-dev
```
For version 1.X also need to install the `libunwind8-dev` package:
```
sudo apt-get install -y libunwind8-dev
```

#### Clone and Build ####
* Clone ChakraCore.
	* ```mkdir Github && cd Github```
	* ```git clone https://github.com/Microsoft/ChakraCore```
* Let's build!
	* ```cd ChakraCore```
	* ```./build.sh```
	* You can specify `--debug` or `--test-build` to `build.sh` to select Debug or Test build flavors respectively. Default is Release build.
	* You can specify `--static` to build ChakraCore as a static library.
* If you'd like to build using `ninja` instead of `cmake`:
	* ```sudo apt-get install -y ninja-build``` (for Debian/Ubuntu) ```dnf install -y ....``` (for Centos/Fedora)
	* Run `ninja --version` and ensure that at least version 1.3 is installed.
	* Specify the `-n` flag to `build.sh` to build with `ninja`.
   * [Optional] Install some useful packages for better development experience.
	* Download and install [VSCode](https://code.visualstudio.com/Docs/editor/setup#_linux).

## OS X ##

You may need to setup [Homebrew](http://brew.sh/) to install additional dependencies.

To build ChakraCore on OS X: (requires OSX 10.8+, XCode 7.0, and Python 2)

* Install dependencies.
	* ```xcode-select --install```
	* ```brew install cmake icu4c```
* Clone ChakraCore.
	* ```mkdir Github && cd Github```
	* ```git clone https://github.com/Microsoft/ChakraCore```
* Let's build!
	* ```cd ChakraCore```
	* ```./build.sh --static --icu=/usr/local/opt/icu4c/include --test-build -j=2```

Some details on build script arguments used above:

* ```--static``` embed JSRT as a static library
* ```--icu=..``` specify the location of ICU library (use `--no-icu` if you don't need unicode support)
* ```--test-build``` enable command line options and some optimizations
* ```-j=2``` compile with 2 threads

### Building in XCode ###

Generate an XCode project:
* Clone the ChakraCore repo and install build dependencies as instructed above
* Run ```./build.sh --xcode --icu=/usr/local/opt/icu4c/include --debug --static```
* Open the `CHAKRACORE.xcodeproj` file in the directory printed by the previous command

##### Execute a JavaScript file with ch host #####

* Select `Product -> Scheme -> ch` in the menu
* Open the  `Product -> Scheme -> Edit Scheme` dialog through the menu
	* Select `Run` in the dialog sidebar, open the `Arguments` tab and add the path to your JS file in `Arguments Passed On Launch`
	* Close the dialog
* Press the `Build and Run` arrow button in the top left of the window
