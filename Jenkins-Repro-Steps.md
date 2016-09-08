When Jenkins builds or tests fail it is helpful to be able to reproduce the errors locally.

It is possible to run builds and tests locally using the same scripts that the Jenkins checks use.
To run these commands, please follow the instructions below.

Keep in mind that certain builds will have system requirements that make it impossible
to run the builds directly on your system configurations
(e.g. Legacy Windows builds which require Windows 7 and/or VS 2013;
and Linux builds which require a Linux system or VM).
Requirements are detailed below.

The following Jenkins commands are directed at re-running entire sets of Jenkins checks.
If you wish to re-run a *particular* check, see [[Jenkins Build Triggers]].

# Rolling Builds

## Windows

Repro with these commands:

```
jenkins\buildone.cmd x64 debug
jenkins\testone.cmd x64 debug
```

When testing a fix to these builds with Jenkins **you do NOT need to request any additional tests**
because this set of tests is automatic.
If you wish to **RE-RUN tests** due to, e.g., intermittent failures, you can request:

```
@dotnet-bot test this please
```

## Linux and OSX

### Linux Repro Steps

Repro with these commands:

```
./build.sh --debug
./test/runtests.sh -d
```

### OSX Repro Steps

Repro with these commands:

```
./build.sh --debug --static --icu=/usr/local/opt/icu4c/include -j=2
./test/runtests.sh -d
```

### Testing Fixes to Linux and OSX

When testing a fix to these builds with Jenkins **you do NOT need to request any additional tests**
because this set of tests is automatic.
If you wish to **RE-RUN tests** due to, e.g., intermittent failures, you can request:

```
@dotnet-bot test this please
```

# Daily Builds

## Builds with Slow Tests

Builds with Slow Tests are used for daily builds, but are *mostly* the same as the rolling builds above.
**Only trigger these builds if there is an issue revealed in the dailies that does not repro in the
rolling builds (to save build machine resources).**

### Windows Daily Builds with Slow Tests

Repro with these commands:

```
jenkins\buildone.cmd x64 debug
jenkins\testone.cmd x64 debug -includeSlow
```

When testing a fix please request:

```
@dotnet-bot test slow tests please
```

### Linux and OSX Daily Builds

Repro with the commands above:

* [Linux Builds](#linux-repro-steps)
* [OSX Builds](#osx-repro-steps)

When testing a fix please request:

```
@dotnet-bot test linux tests please
```

## DisableJIT Daily Builds (Windows-only)

Repro with these commands:

```
jenkins\buildone.cmd x64 debug "/p:BuildJIT=false"
jenkins\testone.cmd x64 debug -disablejit
```

When testing a fix please request:

```
@dotnet-bot test nojit tests please
```

(You can also replace `test nojit tests` with `test disablejit tests` if you prefer -- they are equivalent.)

## Legacy Daily Builds (Windows-only)

_Note: **These tests are designed to run under VS 2013 + Windows 7.**
In most cases, failures are related to running under msbuild 12.0 so you can most likely
reproduce failures using msbuild 12.0 without needing to run on Windows 7. If you still cannot repro,
you might consider setting up a Windows 7 VM to repro._

Repro with these commands:

```
jenkins\buildone.cmd x64 debug msbuild12
jenkins\testone.cmd x64 debug -win7 -includeSlow
```

When testing a fix please request the following:

```
@dotnet-bot test dev12 tests please
```

(You can also replace `test dev12 tests` with `test legacy tests` if you prefer -- they are equivalent.)

# Footnotes

## Windows Alternate Flags

You can replace `x64` with `x86` or `arm`. (Running tests on `arm` builds is not supported).

You can replace `debug` with `test` or `release`. (Running tests on `release` builds is not supported).

Rolling Builds and NoJIT Daily builds of `release` configurations also perform PreFAST code analysis. Modified commands are below:

```
jenkins\buildone.cmd x64 debug "/p:runcodeanalysis=true"
jenkins\testone.cmd x64 debug
powershell .\Build\scripts\check_prefast_error.ps1 . CodeAnalysis.err
```

## Linux Alternate Flags

See [Building ChakraCore](https://github.com/Microsoft/ChakraCore/wiki/Building-ChakraCore#linux)

You can replace `--debug` with `--test-build` or omit this flag for a release build.

You can replace `-d` (corresponding with `--debug` in `build.sh`)
with `-t` (corresponding with `--test-build` in `build.sh`).

(Running tests on release builds is not supported.)

## Systems

See [Building ChakraCore](https://github.com/Microsoft/ChakraCore/wiki/Building-ChakraCore)
for specific details on the platforms and build configurations we support and requirements to build them.

* **Windows:** We will primarily support Windows 8.1+ with VS 2015.
We currently support systems with Windows 7 or VS 2013 as Legacy configurations.
* **Linux:** We will support Ubuntu 16.04 LTS with Clang 3.8+.
* **OS X:** We will support OS X with Clang 3.8+.

## Shorthand and System Compatibility Notes

For purposes of shorthand the following terms are considered more or less equivalent here:

* VS 2015 = Visual Studio 2015 = Dev14 = msbuild 14.0
* VS 2013 = Visual Studio 2013 = Dev12 = msbuild 12.0

Compatibility testing notes:

* All of our compatibility is either targeted at Windows 7 SP1 or Windows 8.1+ (which includes Windows 10).
* Windows 7 SP1 is actually tested on Windows Server 2008 R2 (for our purposes, an equivalent Server OS).
* Windows 8.1+ is actually tested on Windows Server 2012 R2 (for our purposes, an equivalent Server OS).
