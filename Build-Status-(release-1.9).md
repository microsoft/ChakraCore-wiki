Currently showing the Build Status page for the `release/1.9` branch. You can also view the build status for other branches by clicking the links in the sidebar.

# Rolling Builds

For every commit we build and test of all of our build configurations on Windows 8.1 (Windows Server 2012 R2) using VS 2015.

|                               | __Debug__ | __Test__ | __Release__ |
|:-----------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__             | [![x64debug][x64dbgicon]][x64dbglink] | [![x64test][x64testicon]][x64testlink] | [![x64release][x64relicon]][x64rellink] |
| __Windows (x86)__             | [![x86debug][x86dbgicon]][x86dbglink] | [![x86test][x86testicon]][x86testlink] | [![x86release][x86relicon]][x86rellink] |
| __Windows (ARM)__             | [![armdebug][armdbgicon]][armdbglink] | [![armtest][armtesticon]][armtestlink] | [![armrelease][armrelicon]][armrellink] |
| __Ubuntu 16.04 (x64)<sup>[a]</sup>__     | [![linux_a_debug][linux_a_dbgicon]][linux_a_dbglink] | [![linux_a_test][linux_a_testicon]][linux_a_testlink] | [![linux_a_release][linux_a_relicon]][linux_a_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s]</sup>__     | [![linux_s_debug][linux_s_dbgicon]][linux_s_dbglink] | [![linux_s_test][linux_s_testicon]][linux_s_testlink] | [![linux_s_release][linux_s_relicon]][linux_s_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s][n]</sup>__  | * | [![linux_sn_test][linux_sn_testicon]][linux_sn_testlink] | * |
| __OS X 10.9 (x64)<sup>[a]</sup>__        | [![osx_a_debug][osx_a_dbgicon]][osx_a_dbglink] | [![osx_a_test][osx_a_testicon]][osx_a_testlink] | [![osx_a_release][osx_a_relicon]][osx_a_rellink] |
| __OS X 10.9 (x64)<sup>[s][n]</sup>__     | * | [![osx_sn_test][osx_sn_testicon]][osx_sn_testlink] | * |

* <sup>[a]</sup> Static (as applies to Linux / OSX)
* <sup>[s]</sup> Shared (as applies to Linux / OSX)
* <sup>[n]</sup> NoJIT: Compiled without JIT support
* \* We do not run these builds because we believe the builds we do run are sufficient for coverage.

*If you see badges reading "Build: Unknown" it is likely because a build was skipped due to changes being only in files known not to affect the health of the build.*

[x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_debug/badge/icon
[x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_debug/
[x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_test/badge/icon
[x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_test/
[x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_release/badge/icon
[x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x64_release/

[x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_debug/badge/icon
[x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_debug/
[x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_test/badge/icon
[x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_test/
[x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_release/badge/icon
[x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/x86_release/

[armdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_debug/badge/icon
[armdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_debug/
[armtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_test/badge/icon
[armtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_test/
[armrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_release/badge/icon
[armrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/arm_release/

[linux_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_debug/badge/icon
[linux_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_debug/
[linux_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_test/badge/icon
[linux_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_test/
[linux_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_release/badge/icon
[linux_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_release/

[linux_s_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_debug/badge/icon
[linux_s_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_debug/
[linux_s_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_test/badge/icon
[linux_s_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_test/
[linux_s_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_release/badge/icon
[linux_s_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_release/

[linux_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_debug/badge/icon
[linux_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_debug/
[linux_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_test/badge/icon
[linux_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_test/
[linux_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_release/badge/icon
[linux_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_release/

[osx_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_debug/badge/icon
[osx_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_debug/
[osx_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_test/badge/icon
[osx_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_test/
[osx_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_release/badge/icon
[osx_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_release/

[osx_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_debug/badge/icon
[osx_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_debug/
[osx_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_test/badge/icon
[osx_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_test/
[osx_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_release/badge/icon
[osx_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_release/

# Daily Builds

## Builds with Slow Tests

Once a day, we run all the same builds as the Rolling Builds above, but we run additional slow tests.

|                               | __Debug__ | __Test__ | __Release__ |
|:-----------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__             | [![dslowx64debug][dslowx64dbgicon]][dslowx64dbglink] | [![dslowx64test][dslowx64testicon]][dslowx64testlink] | [![dslowx64release][dslowx64relicon]][dslowx64rellink] |
| __Windows (x86)__             | [![dslowx86debug][dslowx86dbgicon]][dslowx86dbglink] | [![dslowx86test][dslowx86testicon]][dslowx86testlink] | [![dslowx86release][dslowx86relicon]][dslowx86rellink] |
| __Windows (ARM)__             | [![dslowarmdebug][dslowarmdbgicon]][dslowarmdbglink] | [![dslowarmtest][dslowarmtesticon]][dslowarmtestlink] | [![dslowarmrelease][dslowarmrelicon]][dslowarmrellink] |
| __Ubuntu 16.04 (x64)<sup>[a]</sup>__     | [![dslow_linux_a_debug][dslow_linux_a_dbgicon]][dslow_linux_a_dbglink] | [![dslow_linux_a_test][dslow_linux_a_testicon]][dslow_linux_a_testlink] | [![dslow_linux_a_release][dslow_linux_a_relicon]][dslow_linux_a_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s]</sup>__     | [![dslow_linux_s_debug][dslow_linux_s_dbgicon]][dslow_linux_s_dbglink] | [![dslow_linux_s_test][dslow_linux_s_testicon]][dslow_linux_s_testlink] | [![dslow_linux_s_release][dslow_linux_s_relicon]][dslow_linux_s_rellink] |
| __OS X 10.9 (x64)<sup>[a]</sup>__        | [![dslow_osx_a_debug][dslow_osx_a_dbgicon]][dslow_osx_a_dbglink] | [![dslow_osx_a_test][dslow_osx_a_testicon]][dslow_osx_a_testlink] | [![dslow_osx_a_release][dslow_osx_a_relicon]][dslow_osx_a_rellink] |

[dslowx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_debug/badge/icon
[dslowx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_debug/
[dslowx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_test/badge/icon
[dslowx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_test/
[dslowx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_release/badge/icon
[dslowx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x64_release/

[dslowx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_debug/badge/icon
[dslowx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_debug/
[dslowx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_test/badge/icon
[dslowx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_test/
[dslowx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_release/badge/icon
[dslowx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_x86_release/

[dslowarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_debug/badge/icon
[dslowarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_debug/
[dslowarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_test/badge/icon
[dslowarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_test/
[dslowarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_release/badge/icon
[dslowarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_slow_arm_release/

[dslow_linux_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_debug/badge/icon
[dslow_linux_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_debug/
[dslow_linux_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_test/badge/icon
[dslow_linux_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_test/
[dslow_linux_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_release/badge/icon
[dslow_linux_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_ubuntu_linux_release/

[dslow_linux_s_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_debug/badge/icon
[dslow_linux_s_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_debug/
[dslow_linux_s_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_test/badge/icon
[dslow_linux_s_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_test/
[dslow_linux_s_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_release/badge/icon
[dslow_linux_s_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/shared_ubuntu_linux_release/

[dslow_osx_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_debug/badge/icon
[dslow_osx_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_debug/
[dslow_osx_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_test/badge/icon
[dslow_osx_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_test/
[dslow_osx_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_release/badge/icon
[dslow_osx_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/static_osx_osx_release/

## DisableJIT Builds

Once a day, we run all of our usual build configurations with JIT excluded from the build.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)<sup>[n]</sup>__ | [![ddjx64debug][ddjx64dbgicon]][ddjx64dbglink] | [![ddjx64test][ddjx64testicon]][ddjx64testlink] | [![ddjx64release][ddjx64relicon]][ddjx64rellink] |
| __Windows (x86)<sup>[n]</sup>__ | [![ddjx86debug][ddjx86dbgicon]][ddjx86dbglink] | [![ddjx86test][ddjx86testicon]][ddjx86testlink] | [![ddjx86release][ddjx86relicon]][ddjx86rellink] |
| __Windows (ARM)<sup>[n]</sup>__ | [![ddjarmdebug][ddjarmdbgicon]][ddjarmdbglink] | [![ddjarmtest][ddjarmtesticon]][ddjarmtestlink] | [![ddjarmrelease][ddjarmrelicon]][ddjarmrellink] |
| __Ubuntu 16.04 (x64)<sup>[s][n]</sup>__  | * | [![dslow_linux_sn_test][dslow_linux_sn_testicon]][dslow_linux_sn_testlink] | * |
| __OS X 10.9 (x64)<sup>[s][n]</sup>__     | * | [![dslow_osx_sn_test][dslow_osx_sn_testicon]][dslow_osx_sn_testlink] | * |

[ddjx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_debug/badge/icon
[ddjx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_debug/
[ddjx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_test/badge/icon
[ddjx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_test/
[ddjx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_release/badge/icon
[ddjx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x64_release/

[ddjx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_debug/badge/icon
[ddjx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_debug/
[ddjx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_test/badge/icon
[ddjx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_test/
[ddjx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_release/badge/icon
[ddjx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_x86_release/

[ddjarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_debug/badge/icon
[ddjarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_debug/
[ddjarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_test/badge/icon
[ddjarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_test/
[ddjarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_release/badge/icon
[ddjarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_disablejit_arm_release/

[dslow_linux_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_debug/badge/icon
[dslow_linux_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_debug/
[dslow_linux_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_test/badge/icon
[dslow_linux_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_test/
[dslow_linux_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_release/badge/icon
[dslow_linux_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_ubuntu_linux_release/

[dslow_osx_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_debug/badge/icon
[dslow_osx_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_debug/
[dslow_osx_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_test/badge/icon
[dslow_osx_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_test/
[dslow_osx_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_release/badge/icon
[dslow_osx_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/_no_jit_shared_osx_osx_release/

## Legacy Builds

Once a day, we run builds of some configurations using Windows 7 (Windows Server 2008 R2) and VS 2013.

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------------:|:--------------:|:-----------------:|
| __Windows (x64)__ | [![dd12x64dbg][dd12x64dbgicon]][dd12x64dbglink] | [![dd12x64test][dd12x64testicon]][dd12x64testlink] | [![dd12x64release][dd12x64relicon]][dd12x64rellink] |
| __Windows (x86)__ | [![dd12x86dbg][dd12x86dbgicon]][dd12x86dbglink] | [![dd12x86test][dd12x86testicon]][dd12x86testlink] | [![dd12x86release][dd12x86relicon]][dd12x86rellink] |

[dd12x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_debug/badge/icon
[dd12x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_debug/
[dd12x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_test/badge/icon
[dd12x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_test/
[dd12x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_release/badge/icon
[dd12x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x64_release/

[dd12x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_debug/badge/icon
[dd12x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_debug/
[dd12x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_test/badge/icon
[dd12x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_test/
[dd12x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_release/badge/icon
[dd12x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/release_1.9/job/daily_dev12_x86_release/
