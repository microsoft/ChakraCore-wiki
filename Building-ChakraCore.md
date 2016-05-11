## Windows ##
 
You can build ChakraCore on Windows 7 SP1 or above, and Windows Server 2008 R2 or above, with either Visual Studio 2013 or 2015, as long as C++ support is installed[*](#build_for_arm). For Linux support, ChakraCore is making progress in the [Linux branch](https://github.com/Microsoft/ChakraCore/tree/linux). Refer to the [Linux](#linux) section for building instructions on Linux.  

To build ChakraCore on Windows:

* Clone ChakraCore through ```git clone https://github.com/Microsoft/ChakraCore.git```
* Open ```Build\Chakra.Core.sln``` in Visual Studio.
* Select the target [Platform](#platform) and [Configuration](#configuration) and build the solution.
* Build output will be under ```Build\VcBuild\bin```.

Alternatively, run msbuild on the command line:
```
msbuild /m /p:Platform=... /p:Configuration=... Build\Chakra.Core.sln
```

### Platform ###

ChakraCore on Windows can be built for 3 Platforms: ```x86```, ```x64``` and ```arm```.

<a name="build_for_arm">**Build for arm**:</a> Due to toolset dependency, you will need following to build for the ```arm``` platform:
* Visual Studio 2015
* [Windows 10 SDK](https://dev.windows.com/en-US/downloads/windows-10-sdk)

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

ChakraCore on Linux is still under development. We are making progress on a first implementation of ChakraCore interpreter and runtime, no JIT, on Linux, targeting x64 Ubuntu 16.04 LTS and Clang 3.8+. You can test the current support with the following instructions. 

To build ChakraCore on Linux:
* Make sure you have Ubuntu 16.04 LTS on your machine or VM. Visit http://releases.ubuntu.com/ to download latest LTS (x64).
* Open terminal and start the update process.
	* ```sudo apt-get update```
	* ```sudo apt-get dist-upgrade```
* Install git.
	* ```sudo apt-get install -y git```
* Clone ChakraCore.
	* ```mkdir Github && cd Github```
	* ```git clone https://github.com/Microsoft/ChakraCore```
* Install dependencies.
	* ```sudo apt-get install -y build-essential cmake clang uuid-dev libunwind-dev libicu-dev liblttng-ust-dev```
* Let's build!
	* ```cd ChakraCore```
	* ```git checkout linux```
	* ```./build.sh``` 
* [Optional] Install some useful packages for better development experience.
	* ```sudo apt-get install -y meld```
	* Download and install [VSCode](https://code.visualstudio.com/Docs/editor/setup#_linux).	
