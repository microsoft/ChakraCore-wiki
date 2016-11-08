## Windows ##

You can build ChakraCore on Windows 7 SP1 or above, and Windows Server 2008 R2
or above, with either Visual Studio 2013 or 2015, as long as C++ support is
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

## Linux ##

Steps below are tested on Ubuntu 16.04LTS. In order to compile ChakraCore on other Linux distrubitions,
use distro's package manager instead of `apt-get` to install given dependencies below.

To build ChakraCore on Linux: (requires Clang 3.7+)

* Open terminal and start the update process.
	* ```sudo apt-get update```
	* ```sudo apt-get dist-upgrade```
* Install git.
	* ```sudo apt-get install -y git```
* Clone ChakraCore.
	* ```mkdir Github && cd Github```
	* ```git clone https://github.com/Microsoft/ChakraCore```
* Install dependencies.
	* ```sudo apt-get install -y build-essential cmake clang libunwind-dev libicu-dev```
* Let's build!
	* ```cd ChakraCore```
	* ```./build.sh```
	* You can specify `--debug` or `--test-build` to `build.sh` to select Debug or Test build flavors respectively. Default is Release build.
	* You can specify `--static` to build ChakraCore as a static library.
* If you'd like to build using `ninja` instead of `cmake`:
	* ```sudo apt-get install -y ninja-build```
	* Run `ninja --version` and ensure that at least version 1.3 is installed.
	* Specify the `-n` flag to `build.sh` to build with `ninja`.
* [Optional] Install some useful packages for better development experience.
	* ```sudo apt-get install -y meld```
	* Download and install [VSCode](https://code.visualstudio.com/Docs/editor/setup#_linux).

## OS X ##

You may need to setup [Homebrew](http://brew.sh/) to install additional dependencies.

To build ChakraCore on OS X: (requires OSX 10.8+ and XCode 7.0)

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
