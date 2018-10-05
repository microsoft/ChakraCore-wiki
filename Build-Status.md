Currently showing the Build Status page for the `master` branch. You can also view the build status for other branches by clicking the links in the sidebar.


# Rolling Builds

For every commit we build and test of all of our build configurations on Windows 10 <sup>[**]</sup> with VS 2017 (Dev 15.7).

|                                           | __Debug__ | __Test__ | __Release__ |
|:-----------------------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__                         | [![x64debug][x64dbgicon]][x64dbglink] | [![x64test][x64testicon]][x64testlink] | [![x64release][x64relicon]][x64rellink] |
| __Windows (x86)__                         | [![x86debug][x86dbgicon]][x86dbglink] | [![x86test][x86testicon]][x86testlink] | [![x86release][x86relicon]][x86rellink] |
| __Windows (ARM)__                         | [![armdebug][armdbgicon]][armdbglink] | [![armtest][armtesticon]][armtestlink] | [![armrelease][armrelicon]][armrellink] |
| __Ubuntu 16.04 (x64)<sup>[a]</sup>__      | [![linux_a_debug][linux_a_dbgicon]][linux_a_dbglink] | [![linux_a_test][linux_a_testicon]][linux_a_testlink] | [![linux_a_release][linux_a_relicon]][linux_a_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s]</sup>__      | [![linux_s_debug][linux_s_dbgicon]][linux_s_dbglink] | [![linux_s_test][linux_s_testicon]][linux_s_testlink] | [![linux_s_release][linux_s_relicon]][linux_s_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s][n]</sup>__   | * | [![linux_sn_test][linux_sn_testicon]][linux_sn_testlink] | * |
| __OS X 10.9 (x64)<sup>[a]</sup>__         | [![osx_a_debug][osx_a_dbgicon]][osx_a_dbglink] | [![osx_a_test][osx_a_testicon]][osx_a_testlink] | [![osx_a_release][osx_a_relicon]][osx_a_rellink] |
| __OS X 10.9 (x64)<sup>[s][n]</sup>__      | * | [![osx_sn_test][osx_sn_testicon]][osx_sn_testlink] | * |

* <sup>[**]</sup> ARM builds are still running on Windows 8.1 due to an SDK issue on the Windows 10 CI machines.
* <sup>[a]</sup> Static (as applies to Linux / OSX)
* <sup>[s]</sup> Shared (as applies to Linux / OSX)
* <sup>[n]</sup> NoJIT: Compiled without JIT support
* \* We do not run these builds because we believe the builds we do run are sufficient for coverage.

*If you see badges reading "Build: Unknown" it is likely because a build was skipped due to changes being only in files known not to affect the health of the build.*

[x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_debug/badge/icon
[x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_debug/
[x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_test/badge/icon
[x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_test/
[x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_release/badge/icon
[x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x64_release/

[x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_debug/badge/icon
[x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_debug/
[x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_test/badge/icon
[x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_test/
[x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_release/badge/icon
[x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/x86_release/

[armdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_debug/badge/icon
[armdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_debug/
[armtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_test/badge/icon
[armtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_test/
[armrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_release/badge/icon
[armrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/arm_release/

[linux_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_debug/badge/icon
[linux_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_debug/
[linux_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_test/badge/icon
[linux_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_test/
[linux_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_release/badge/icon
[linux_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_release/

[linux_s_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_debug/badge/icon
[linux_s_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_debug/
[linux_s_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_test/badge/icon
[linux_s_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_test/
[linux_s_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_release/badge/icon
[linux_s_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_release/

[linux_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_debug/badge/icon
[linux_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_debug/
[linux_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_test/badge/icon
[linux_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_test/
[linux_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_release/badge/icon
[linux_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_release/

[osx_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_debug/badge/icon
[osx_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_debug/
[osx_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_test/badge/icon
[osx_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_test/
[osx_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_release/badge/icon
[osx_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_release/

[osx_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_debug/badge/icon
[osx_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_debug/
[osx_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_test/badge/icon
[osx_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_test/
[osx_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_release/badge/icon
[osx_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_release/

# Daily Builds

## Builds with Slow Tests

Once a day, we run all the same builds as the Rolling Builds above, but we run additional slow tests.

|                                       | __Debug__ | __Test__ | __Release__ |
|:-------------------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__                     | [![dslowx64debug][dslowx64dbgicon]][dslowx64dbglink] | [![dslowx64test][dslowx64testicon]][dslowx64testlink] | [![dslowx64release][dslowx64relicon]][dslowx64rellink] |
| __Windows (x86)__                     | [![dslowx86debug][dslowx86dbgicon]][dslowx86dbglink] | [![dslowx86test][dslowx86testicon]][dslowx86testlink] | [![dslowx86release][dslowx86relicon]][dslowx86rellink] |
| __Windows (ARM)__                     | [![dslowarmdebug][dslowarmdbgicon]][dslowarmdbglink] | [![dslowarmtest][dslowarmtesticon]][dslowarmtestlink] | [![dslowarmrelease][dslowarmrelicon]][dslowarmrellink] |
| __Ubuntu 16.04 (x64)<sup>[a]</sup>__  | [![dslow_linux_a_debug][dslow_linux_a_dbgicon]][dslow_linux_a_dbglink] | [![dslow_linux_a_test][dslow_linux_a_testicon]][dslow_linux_a_testlink] | [![dslow_linux_a_release][dslow_linux_a_relicon]][dslow_linux_a_rellink] |
| __Ubuntu 16.04 (x64)<sup>[s]</sup>__  | [![dslow_linux_s_debug][dslow_linux_s_dbgicon]][dslow_linux_s_dbglink] | [![dslow_linux_s_test][dslow_linux_s_testicon]][dslow_linux_s_testlink] | [![dslow_linux_s_release][dslow_linux_s_relicon]][dslow_linux_s_rellink] |
| __OS X 10.9 (x64)<sup>[a]</sup>__     | [![dslow_osx_a_debug][dslow_osx_a_dbgicon]][dslow_osx_a_dbglink] | [![dslow_osx_a_test][dslow_osx_a_testicon]][dslow_osx_a_testlink] | [![dslow_osx_a_release][dslow_osx_a_relicon]][dslow_osx_a_rellink] |

[dslowx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_debug/badge/icon
[dslowx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_debug/
[dslowx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_test/badge/icon
[dslowx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_test/
[dslowx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_release/badge/icon
[dslowx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x64_release/

[dslowx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_debug/badge/icon
[dslowx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_debug/
[dslowx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_test/badge/icon
[dslowx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_test/
[dslowx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_release/badge/icon
[dslowx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_x86_release/

[dslowarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_debug/badge/icon
[dslowarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_debug/
[dslowarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_test/badge/icon
[dslowarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_test/
[dslowarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_release/badge/icon
[dslowarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_slow_arm_release/

<!-- The jobs below are duplicates of the rolling build jobs, which run all of the same (slow) tests, duplicated in this table for convenience -->

[dslow_linux_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_debug/badge/icon
[dslow_linux_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_debug/
[dslow_linux_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_test/badge/icon
[dslow_linux_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_test/
[dslow_linux_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_release/badge/icon
[dslow_linux_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_ubuntu_linux_release/

[dslow_linux_s_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_debug/badge/icon
[dslow_linux_s_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_debug/
[dslow_linux_s_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_test/badge/icon
[dslow_linux_s_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_test/
[dslow_linux_s_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_release/badge/icon
[dslow_linux_s_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/shared_ubuntu_linux_release/

[dslow_osx_a_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_debug/badge/icon
[dslow_osx_a_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_debug/
[dslow_osx_a_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_test/badge/icon
[dslow_osx_a_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_test/
[dslow_osx_a_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_release/badge/icon
[dslow_osx_a_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/static_osx_osx_release/


## DisableJIT Builds

Once a day, we run all of our usual build configurations with JIT excluded from the build.

|                                           | __Debug__ | __Test__ | __Release__ |
|:-----------------------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)<sup>[n]</sup>__           | [![ddjx64debug][ddjx64dbgicon]][ddjx64dbglink] | [![ddjx64test][ddjx64testicon]][ddjx64testlink] | [![ddjx64release][ddjx64relicon]][ddjx64rellink] |
| __Windows (x86)<sup>[n]</sup>__           | [![ddjx86debug][ddjx86dbgicon]][ddjx86dbglink] | [![ddjx86test][ddjx86testicon]][ddjx86testlink] | [![ddjx86release][ddjx86relicon]][ddjx86rellink] |
| __Windows (ARM)<sup>[n]</sup>__           | [![ddjarmdebug][ddjarmdbgicon]][ddjarmdbglink] | [![ddjarmtest][ddjarmtesticon]][ddjarmtestlink] | [![ddjarmrelease][ddjarmrelicon]][ddjarmrellink] |
| __Ubuntu 16.04 (x64)<sup>[s][n]</sup>__   | * | [![dslow_linux_sn_test][dslow_linux_sn_testicon]][dslow_linux_sn_testlink] | * |
| __OS X 10.9 (x64)<sup>[s][n]</sup>__      | * | [![dslow_osx_sn_test][dslow_osx_sn_testicon]][dslow_osx_sn_testlink] | * |

[ddjx64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_debug/badge/icon
[ddjx64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_debug/
[ddjx64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_test/badge/icon
[ddjx64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_test/
[ddjx64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_release/badge/icon
[ddjx64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x64_release/

[ddjx86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_debug/badge/icon
[ddjx86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_debug/
[ddjx86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_test/badge/icon
[ddjx86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_test/
[ddjx86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_release/badge/icon
[ddjx86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_x86_release/

[ddjarmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_debug/badge/icon
[ddjarmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_debug/
[ddjarmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_test/badge/icon
[ddjarmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_test/
[ddjarmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_release/badge/icon
[ddjarmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_disablejit_arm_release/

[dslow_linux_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_debug/badge/icon
[dslow_linux_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_debug/
[dslow_linux_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_test/badge/icon
[dslow_linux_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_test/
[dslow_linux_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_release/badge/icon
[dslow_linux_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_ubuntu_linux_release/

[dslow_osx_sn_dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_debug/badge/icon
[dslow_osx_sn_dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_debug/
[dslow_osx_sn_testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_test/badge/icon
[dslow_osx_sn_testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_test/
[dslow_osx_sn_relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_release/badge/icon
[dslow_osx_sn_rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/_no_jit_shared_osx_osx_release/


## Lite Builds

Once a day, we run builds on the same machine configurations in the ChakraCore-Lite build configuration.

|                                       | __Debug__ | __Test__ | __Release__ |
|:-------------------------------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__                     | [![dlitex64debug][dlitex64dbgicon]][dlitex64dbglink] | [![dlitex64test][dlitex64testicon]][dlitex64testlink] | [![dlitex64release][dlitex64relicon]][dlitex64rellink] |
| __Windows (x86)__                     | [![dlitex86debug][dlitex86dbgicon]][dlitex86dbglink] | [![dlitex86test][dlitex86testicon]][dlitex86testlink] | [![dlitex86release][dlitex86relicon]][dlitex86rellink] |
| __Windows (ARM)__                     | [![dlitearmdebug][dlitearmdbgicon]][dlitearmdbglink] | [![dlitearmtest][dlitearmtesticon]][dlitearmtestlink] | [![dlitearmrelease][dlitearmrelicon]][dlitearmrellink] |

[dlitex64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_debug/badge/icon
[dlitex64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_debug/
[dlitex64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_test/badge/icon
[dlitex64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_test/
[dlitex64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_release/badge/icon
[dlitex64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x64_release/

[dlitex86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_debug/badge/icon
[dlitex86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_debug/
[dlitex86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_test/badge/icon
[dlitex86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_test/
[dlitex86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_release/badge/icon
[dlitex86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_x86_release/

[dlitearmdbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_debug/badge/icon
[dlitearmdbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_debug/
[dlitearmtesticon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_test/badge/icon
[dlitearmtestlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_test/
[dlitearmrelicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_release/badge/icon
[dlitearmrellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_lite_arm_release/


## Legacy Builds

### Windows 8.1 Blue with VS 2015

Once a day, we run builds of some configurations using Windows 8.1 Blue (Windows Server 2012 R2) with VS 2015 (Dev 14).

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__ | [![dlegacy8x64dbg][dlegacy8x64dbgicon]][dlegacy8x64dbglink] | [![dlegacy8x64test][dlegacy8x64testicon]][dlegacy8x64testlink] | [![dlegacy8x64release][dlegacy8x64relicon]][dlegacy8x64rellink] |
| __Windows (x86)__ | [![dlegacy8x86dbg][dlegacy8x86dbgicon]][dlegacy8x86dbglink] | [![dlegacy8x86test][dlegacy8x86testicon]][dlegacy8x86testlink] | [![dlegacy8x86release][dlegacy8x86relicon]][dlegacy8x86rellink] |

[dlegacy8x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_debug/badge/icon
[dlegacy8x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_debug/
[dlegacy8x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_test/badge/icon
[dlegacy8x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_test/
[dlegacy8x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_release/badge/icon
[dlegacy8x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x64_release/

[dlegacy8x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_debug/badge/icon
[dlegacy8x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_debug/
[dlegacy8x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_test/badge/icon
[dlegacy8x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_test/
[dlegacy8x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_release/badge/icon
[dlegacy8x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy8_x86_release/


### Windows 7 with VS 2015

Once a day, we run builds of some configurations using Windows 7 (Windows Server 2008 R2) with VS 2015 (Dev 14).

|                   | __Debug__ | __Test__ | __Release__ |
|:-----------------:|:---------:|:--------:|:-----------:|
| __Windows (x64)__ | [![dlegacy7x64dbg][dlegacy7x64dbgicon]][dlegacy7x64dbglink] | [![dlegacy7x64test][dlegacy7x64testicon]][dlegacy7x64testlink] | [![dlegacy7x64release][dlegacy7x64relicon]][dlegacy7x64rellink] |
| __Windows (x86)__ | [![dlegacy7x86dbg][dlegacy7x86dbgicon]][dlegacy7x86dbglink] | [![dlegacy7x86test][dlegacy7x86testicon]][dlegacy7x86testlink] | [![dlegacy7x86release][dlegacy7x86relicon]][dlegacy7x86rellink] |

[dlegacy7x64dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_debug/badge/icon
[dlegacy7x64dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_debug/
[dlegacy7x64testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_test/badge/icon
[dlegacy7x64testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_test/
[dlegacy7x64relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_release/badge/icon
[dlegacy7x64rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x64_release/

[dlegacy7x86dbgicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_debug/badge/icon
[dlegacy7x86dbglink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_debug/
[dlegacy7x86testicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_test/badge/icon
[dlegacy7x86testlink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_test/
[dlegacy7x86relicon]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_release/badge/icon
[dlegacy7x86rellink]: https://ci2.dot.net/job/Microsoft_ChakraCore/job/master/job/daily_legacy7_x86_release/
