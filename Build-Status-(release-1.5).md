Currently showing the Build Status page for the `release/1.5` branch. You can also view the build status for other branches by clicking the links in the sidebar.

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

[x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_debug/badge/icon
[x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_debug/
[x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_test/badge/icon
[x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_test/
[x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_release/badge/icon
[x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x64_release/

[x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_debug/badge/icon
[x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_debug/
[x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_test/badge/icon
[x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_test/
[x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_release/badge/icon
[x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/x86_release/

[armdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_debug/badge/icon
[armdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_debug/
[armtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_test/badge/icon
[armtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_test/
[armrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_release/badge/icon
[armrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/arm_release/

[linuxdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_debug/badge/icon
[linuxdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_debug/
[linuxtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_test/badge/icon
[linuxtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_test/
[linuxrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_release/badge/icon
[linuxrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_release/

[linuxsdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_debug_static/badge/icon
[linuxsdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_debug_static/
[linuxstesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_test_static/badge/icon
[linuxstestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_test_static/
[linuxsrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_release_static/badge/icon
[linuxsrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/ubuntu_linux_release_static/

[osxsdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_debug_static/badge/icon
[osxsdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_debug_static/
[osxstesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_test_static/badge/icon
[osxstestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_test_static/
[osxsrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_release_static/badge/icon
[osxsrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/osx_osx_release_static/

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

[dslowx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_debug/badge/icon
[dslowx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_debug/
[dslowx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_test/badge/icon
[dslowx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_test/
[dslowx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_release/badge/icon
[dslowx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x64_release/

[dslowx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_debug/badge/icon
[dslowx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_debug/
[dslowx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_test/badge/icon
[dslowx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_test/
[dslowx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_release/badge/icon
[dslowx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_x86_release/

[dslowarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_debug/badge/icon
[dslowarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_debug/
[dslowarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_test/badge/icon
[dslowarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_test/
[dslowarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_release/badge/icon
[dslowarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_slow_arm_release/

[dslowlinuxdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_debug/badge/icon
[dslowlinuxdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_debug/
[dslowlinuxtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_test/badge/icon
[dslowlinuxtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_test/
[dslowlinuxrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_release/badge/icon
[dslowlinuxrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_release/

[dslowlinuxsdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_debug_static/badge/icon
[dslowlinuxsdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_debug_static/
[dslowlinuxstesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_test_static/badge/icon
[dslowlinuxstestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_test_static/
[dslowlinuxsrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_release_static/badge/icon
[dslowlinuxsrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_ubuntu_linux_release_static/

[dslowosxsdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_debug_static/badge/icon
[dslowosxsdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_debug_static/
[dslowosxstesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_test_static/badge/icon
[dslowosxstestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_test_static/
[dslowosxsrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_release_static/badge/icon
[dslowosxsrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_osx_osx_release_static/

## DisableJIT Builds

Once a day, we run all of our usual build configurations with JIT excluded from the build.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__ | [![ddjx64debug][ddjx64dbgicon]][ddjx64dbglink] | [![ddjx64test][ddjx64testicon]][ddjx64testlink] | [![ddjx64release][ddjx64relicon]][ddjx64rellink] |
| __Windows (x86)__ | [![ddjx86debug][ddjx86dbgicon]][ddjx86dbglink] | [![ddjx86test][ddjx86testicon]][ddjx86testlink] | [![ddjx86release][ddjx86relicon]][ddjx86rellink] |
| __Windows (ARM)__ | [![ddjarmdebug][ddjarmdbgicon]][ddjarmdbglink] | [![ddjarmtest][ddjarmtesticon]][ddjarmtestlink] | [![ddjarmrelease][ddjarmrelicon]][ddjarmrellink] |

[ddjx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_debug/badge/icon
[ddjx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_debug/
[ddjx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_test/badge/icon
[ddjx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_test/
[ddjx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_release/badge/icon
[ddjx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x64_release/

[ddjx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_debug/badge/icon
[ddjx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_debug/
[ddjx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_test/badge/icon
[ddjx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_test/
[ddjx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_release/badge/icon
[ddjx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_x86_release/

[ddjarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_debug/badge/icon
[ddjarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_debug/
[ddjarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_test/badge/icon
[ddjarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_test/
[ddjarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_release/badge/icon
[ddjarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_disablejit_arm_release/

## Legacy Builds

Once a day, we run builds of some configurations using Windows 7 (Windows Server 2008 R2) and VS 2013.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------------:|:--------------:|:-----------------:|
| __Windows (x64)__ | [![dd12x64dbg][dd12x64dbgicon]][dd12x64dbglink] | [![dd12x64test][dd12x64testicon]][dd12x64testlink] | [![dd12x64release][dd12x64relicon]][dd12x64rellink] |
| __Windows (x86)__ | [![dd12x86dbg][dd12x86dbgicon]][dd12x86dbglink] | [![dd12x86test][dd12x86testicon]][dd12x86testlink] | [![dd12x86release][dd12x86relicon]][dd12x86rellink] |

[dd12x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_debug/badge/icon
[dd12x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_debug/
[dd12x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_test/badge/icon
[dd12x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_test/
[dd12x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_release/badge/icon
[dd12x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x64_release/

[dd12x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_debug/badge/icon
[dd12x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_debug/
[dd12x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_test/badge/icon
[dd12x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_test/
[dd12x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_release/badge/icon
[dd12x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.5/job/daily_dev12_x86_release/
