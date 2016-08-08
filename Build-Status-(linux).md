Currently showing the Build Status page for the `linux` branch. You can also view the build status for other branches by clicking the links in the sidebar.

# Rolling Builds

For every commit we build and test of all of our build configurations on Windows 8.1 (Windows Server 2012 R2) using VS 2015.

|                               | __Debug__ | __Test__ | __Release__ |
|:-----------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__             | [![x64debug][x64dbgicon]][x64dbglink] | [![x64test][x64testicon]][x64testlink] | [![x64release][x64relicon]][x64rellink] |
| __Windows (x86)__             | [![x86debug][x86dbgicon]][x86dbglink] | [![x86test][x86testicon]][x86testlink] | [![x86release][x86relicon]][x86rellink] |
| __Windows (ARM)__             | [![armdebug][armdbgicon]][armdbglink] | [![armtest][armtesticon]][armtestlink] | [![armrelease][armrelicon]][armrellink] |
| __Ubuntu 16.04 (x64)__        | [![linuxdebug][linuxdbgicon]][linuxdbglink] | [![linuxtest][linuxtesticon]][linuxtestlink] | [![linuxrelease][linuxrelicon]][linuxrellink] |
| __Ubuntu 16.04 (x64 static)__ | [![linuxsdebug][linuxsdbgicon]][linuxsdbglink] | [![linuxstest][linuxstesticon]][linuxstestlink] | [![linuxsrelease][linuxsrelicon]][linuxsrellink] |
| __OS X 10.9 (x64 static)__    | [![osxsdebug][osxsdbgicon]][osxsdbglink] | [![osxstest][osxstesticon]][osxstestlink] | [![osxsrelease][osxsrelicon]][osxsrellink] |

*If you see badges reading "Build: Unknown" it is likely because a build was skipped due to changes being only in files known not to affect the health of the build.*

[x86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_debug/badge/icon
[x86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_debug/
[x86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_test/badge/icon
[x86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_test/
[x86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_release/badge/icon
[x86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x86_release/

[x64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_debug/badge/icon
[x64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_debug/
[x64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_test/badge/icon
[x64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_test/
[x64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_release/badge/icon
[x64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/x64_release/

[armdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_debug/badge/icon
[armdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_debug/
[armtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_test/badge/icon
[armtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_test/
[armrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_release/badge/icon
[armrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/arm_release/

[linuxdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_debug/badge/icon
[linuxdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_debug/
[linuxtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_test/badge/icon
[linuxtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_test/
[linuxrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_release/badge/icon
[linuxrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_release/

[linuxsdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_debug_static/badge/icon
[linuxsdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_debug_static/
[linuxstesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_test_static/badge/icon
[linuxstestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_test_static/
[linuxsrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_release_static/badge/icon
[linuxsrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/ubuntu_linux_release_static/

[osxsdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_debug_static/badge/icon
[osxsdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_debug_static/
[osxstesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_test_static/badge/icon
[osxstestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_test_static/
[osxsrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_release_static/badge/icon
[osxsrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/osx_osx_release_static/

# Daily Builds

## Builds with Slow Tests

Once a day, we run all the same builds as the Rolling Builds above, but we run additional slow tests.

|                               | __Debug__ | __Test__ | __Release__ |
|:-----------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__             | [![dslowx64debug][dslowx64dbgicon]][dslowx64dbglink] | [![dslowx64test][dslowx64testicon]][dslowx64testlink] | [![dslowx64release][dslowx64relicon]][dslowx64rellink] |
| __Windows (x86)__             | [![dslowx86debug][dslowx86dbgicon]][dslowx86dbglink] | [![dslowx86test][dslowx86testicon]][dslowx86testlink] | [![dslowx86release][dslowx86relicon]][dslowx86rellink] |
| __Windows (ARM)__             | [![dslowarmdebug][dslowarmdbgicon]][dslowarmdbglink] | [![dslowarmtest][dslowarmtesticon]][dslowarmtestlink] | [![dslowarmrelease][dslowarmrelicon]][dslowarmrellink] |
| __Ubuntu 16.04 (x64)__        | [![dslowlinuxdebug][dslowlinuxdbgicon]][dslowlinuxdbglink] | [![dslowlinuxtest][dslowlinuxtesticon]][dslowlinuxtestlink] | [![dslowlinuxrelease][dslowlinuxrelicon]][dslowlinuxrellink] |
| __Ubuntu 16.04 (x64 static)__ | [![dslowlinuxsdebug][dslowlinuxsdbgicon]][dslowlinuxsdbglink] | [![dslowlinuxstest][dslowlinuxstesticon]][dslowlinuxstestlink] | [![dslowlinuxsrelease][dslowlinuxsrelicon]][dslowlinuxsrellink] |
| __OS X 10.9 (x64 static)__    | [![dslowosxsdebug][dslowosxsdbgicon]][dslowosxsdbglink] | [![dslowosxstest][dslowosxstesticon]][dslowosxstestlink] | [![dslowosxsrelease][dslowosxsrelicon]][dslowosxsrellink] |

[dslowx86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_debug/badge/icon
[dslowx86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_debug/
[dslowx86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_test/badge/icon
[dslowx86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_test/
[dslowx86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_release/badge/icon
[dslowx86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x86_release/

[dslowx64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_debug/badge/icon
[dslowx64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_debug/
[dslowx64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_test/badge/icon
[dslowx64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_test/
[dslowx64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_release/badge/icon
[dslowx64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_x64_release/

[dslowarmdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_debug/badge/icon
[dslowarmdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_debug/
[dslowarmtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_test/badge/icon
[dslowarmtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_test/
[dslowarmrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_release/badge/icon
[dslowarmrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_slow_arm_release/

[dslowlinuxdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_debug/badge/icon
[dslowlinuxdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_debug/
[dslowlinuxtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_test/badge/icon
[dslowlinuxtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_test/
[dslowlinuxrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_release/badge/icon
[dslowlinuxrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_release/

[dslowlinuxsdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_debug_static/badge/icon
[dslowlinuxsdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_debug_static/
[dslowlinuxstesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_test_static/badge/icon
[dslowlinuxstestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_test_static/
[dslowlinuxsrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_release_static/badge/icon
[dslowlinuxsrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_ubuntu_linux_release_static/

[dslowosxsdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_debug_static/badge/icon
[dslowosxsdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_debug_static/
[dslowosxstesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_test_static/badge/icon
[dslowosxstestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_test_static/
[dslowosxsrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_release_static/badge/icon
[dslowosxsrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_osx_osx_release_static/

## DisableJIT Builds

Once a day, we run all of our usual build configurations with JIT excluded from the build.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__ | [![ddjx64debug][ddjx64dbgicon]][ddjx64dbglink] | [![ddjx64test][ddjx64testicon]][ddjx64testlink] | [![ddjx64release][ddjx64relicon]][ddjx64rellink] |
| __Windows (x86)__ | [![ddjx86debug][ddjx86dbgicon]][ddjx86dbglink] | [![ddjx86test][ddjx86testicon]][ddjx86testlink] | [![ddjx86release][ddjx86relicon]][ddjx86rellink] |
| __Windows (ARM)__ | [![ddjarmdebug][ddjarmdbgicon]][ddjarmdbglink] | [![ddjarmtest][ddjarmtesticon]][ddjarmtestlink] | [![ddjarmrelease][ddjarmrelicon]][ddjarmrellink] |

[ddjx86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_debug/badge/icon
[ddjx86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_debug/
[ddjx86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_test/badge/icon
[ddjx86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_test/
[ddjx86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_release/badge/icon
[ddjx86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x86_release/

[ddjx64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_debug/badge/icon
[ddjx64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_debug/
[ddjx64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_test/badge/icon
[ddjx64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_test/
[ddjx64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_release/badge/icon
[ddjx64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_x64_release/

[ddjarmdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_debug/badge/icon
[ddjarmdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_debug/
[ddjarmtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_test/badge/icon
[ddjarmtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_test/
[ddjarmrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_release/badge/icon
[ddjarmrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_disablejit_arm_release/

## Legacy Builds

Once a day, we run builds of some configurations using Windows 7 (Windows Server 2008 R2) and VS 2013.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------------:|:--------------:|:-----------------:|
| __Windows (x64)__ | [![dd12x64dbg][dd12x64dbgicon]][dd12x64dbglink] | [![dd12x64test][dd12x64testicon]][dd12x64testlink] | [![dd12x64release][dd12x64relicon]][dd12x64rellink] |
| __Windows (x86)__ | [![dd12x86dbg][dd12x86dbgicon]][dd12x86dbglink] | [![dd12x86test][dd12x86testicon]][dd12x86testlink] | [![dd12x86release][dd12x86relicon]][dd12x86rellink] |

[dd12x86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_debug/badge/icon
[dd12x86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_debug/
[dd12x86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_test/badge/icon
[dd12x86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_test/
[dd12x86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_release/badge/icon
[dd12x86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x86_release/

[dd12x64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_debug/badge/icon
[dd12x64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_debug/
[dd12x64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_test/badge/icon
[dd12x64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_test/
[dd12x64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_release/badge/icon
[dd12x64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/linux/job/daily_dev12_x64_release/
