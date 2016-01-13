# Rolling Builds

For every commit we run builds of all of our build configurations on Windows 8.1 (Windows Server 2012 R2) using VS 2015.

|         | __Debug__ | __Test__ | __Release__ |
|:-------:|:---------:|:--------:|:-----------:|
| __x86__ | [![x86debug][x86dbgicon]][x86dbglink] | [![x86test][x86testicon]][x86testlink] | [![x86release][x86relicon]][x86rellink] |
| __x64__ | [![x64debug][x64dbgicon]][x64dbglink] | [![x64test][x64testicon]][x64testlink] | [![x64release][x64relicon]][x64rellink] |
| __arm__ | [![armdebug][armdbgicon]][armdbglink] | [![armtest][armtesticon]][armtestlink] | [![armrelease][armrelicon]][armrellink] |

[x86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_debug/badge/icon
[x86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_debug/
[x86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_test/badge/icon
[x86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_test/
[x86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_release/badge/icon
[x86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x86_release/

[x64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_debug/badge/icon
[x64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_debug/
[x64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_test/badge/icon
[x64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_test/
[x64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_release/badge/icon
[x64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/x64_release/

[armdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_debug/badge/icon
[armdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_debug/
[armtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_test/badge/icon
[armtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_test/
[armrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_release/badge/icon
[armrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/arm_release/

# Daily Builds

## DisableJIT Builds

Once daily we run all of our usual build configurations with JIT excluded from the build.

|         | __Debug__ | __Test__ | __Release__ |
|:-------:|:---------:|:--------:|:-----------:|
| __x86__ | [![ddjx86debug][ddjx86dbgicon]][ddjx86dbglink] | [![ddjx86test][ddjx86testicon]][ddjx86testlink] | [![ddjx86release][ddjx86relicon]][ddjx86rellink] |
| __x64__ | [![ddjx64debug][ddjx64dbgicon]][ddjx64dbglink] | [![ddjx64test][ddjx64testicon]][ddjx64testlink] | [![ddjx64release][ddjx64relicon]][ddjx64rellink] |
| __arm__ | [![ddjarmdebug][ddjarmdbgicon]][ddjarmdbglink] | [![ddjarmtest][ddjarmtesticon]][ddjarmtestlink] | [![ddjarmrelease][ddjarmrelicon]][ddjarmrellink] |

[ddjx86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_debug/badge/icon
[ddjx86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_debug/
[ddjx86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_test/badge/icon
[ddjx86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_test/
[ddjx86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_release/badge/icon
[ddjx86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x86_release/

[ddjx64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_debug/badge/icon
[ddjx64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_debug/
[ddjx64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_test/badge/icon
[ddjx64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_test/
[ddjx64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_release/badge/icon
[ddjx64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_x64_release/

[ddjarmdbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_debug/badge/icon
[ddjarmdbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_debug/
[ddjarmtesticon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_test/badge/icon
[ddjarmtestlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_test/
[ddjarmrelicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_release/badge/icon
[ddjarmrellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_disablejit_arm_release/

## Legacy Builds

Once daily we run builds of some configurations using Windows 7 and VS 2013.

|         | __Debug__ | __Test__ | __Release__ |
|:-------:|:---------------:|:--------------:|:-----------------:|
| __x86__ | [![dailyx86dbg][dailyx86dbgicon]][dailyx86dbglink] | [![dailyx86test][dailyx86testicon]][dailyx86testlink] | [![dailyx86release][dailyx86relicon]][dailyx86rellink] |
| __x64__ | [![dailyx64dbg][dailyx64dbgicon]][dailyx64dbglink] | [![dailyx64test][dailyx64testicon]][dailyx64testlink] | [![dailyx64release][dailyx64relicon]][dailyx64rellink] |

[dailyx86dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_debug_prtest/badge/icon
[dailyx86dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_debug_prtest/
[dailyx86testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_test_prtest/badge/icon
[dailyx86testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_test_prtest/
[dailyx86relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_release_prtest/badge/icon
[dailyx86rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x86_release_prtest/

[dailyx64dbgicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_debug_prtest/badge/icon
[dailyx64dbglink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_debug_prtest/
[dailyx64testicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_test_prtest/badge/icon
[dailyx64testlink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_test_prtest/
[dailyx64relicon]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_release_prtest/badge/icon
[dailyx64rellink]: http://dotnet-ci.cloudapp.net/job/Microsoft_ChakraCore/job/daily_x64_release_prtest/