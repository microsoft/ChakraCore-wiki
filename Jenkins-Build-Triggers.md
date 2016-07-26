You can trigger individual Jenkins builds on a PR by writing a comment with the following pattern:

```
@dotnet-bot test [build-name] please
```

Where `[build-name]` is the name of the check as it appears at the bottom of a PR.
The specific comments needed to trigger the builds are listed below.

# Default Jenkins Builds

This is the set of builds that should be triggered by default on a pull request. (Linux builds will
only be triggered for branches that support Linux builds.)

To re-run the full set of builds:

```
@dotnet-bot test this please
```

To re-run individual builds:

```
@dotnet-bot test Copyright Check please
@dotnet-bot test EOL Check please

@dotnet-bot test Windows x64_debug please
@dotnet-bot test Windows x64_release please
@dotnet-bot test Windows x64_test please
@dotnet-bot test Windows x86_debug please
@dotnet-bot test Windows x86_release please
@dotnet-bot test Windows x86_test please
@dotnet-bot test Windows arm_debug please
@dotnet-bot test Windows arm_release please
@dotnet-bot test Windows arm_test please

@dotnet-bot test Ubuntu ubuntu_linux_debug please
@dotnet-bot test Ubuntu ubuntu_linux_debug_static please
@dotnet-bot test Ubuntu ubuntu_linux_release please
@dotnet-bot test Ubuntu ubuntu_linux_release_static please
@dotnet-bot test Ubuntu ubuntu_linux_test please
@dotnet-bot test Ubuntu ubuntu_linux_test_static please
```

# Daily Builds

The following are commands which can be used to run daily build configurations on a PR,
which can be useful for validating fixes.

## Builds with Slow Tests

Run the full set:

```
@dotnet-bot test slow tests please
```

Run individual builds:

```
@dotnet-bot test Windows daily_slow_x64_debug please
@dotnet-bot test Windows daily_slow_x64_release please
@dotnet-bot test Windows daily_slow_x64_test please
@dotnet-bot test Windows daily_slow_x86_debug please
@dotnet-bot test Windows daily_slow_x86_release please
@dotnet-bot test Windows daily_slow_x86_test please
@dotnet-bot test Windows daily_slow_arm_debug please
@dotnet-bot test Windows daily_slow_arm_release please
@dotnet-bot test Windows daily_slow_arm_test please
```

## Linux Builds

Run the full set:

```
@dotnet-bot test linux tests please
```

Run individual builds:

```
@dotnet-bot test Ubuntu daily_ubuntu_linux_debug please
@dotnet-bot test Ubuntu daily_ubuntu_linux_debug_static please
@dotnet-bot test Ubuntu daily_ubuntu_linux_release please
@dotnet-bot test Ubuntu daily_ubuntu_linux_release_static please
@dotnet-bot test Ubuntu daily_ubuntu_linux_test please
@dotnet-bot test Ubuntu daily_ubuntu_linux_test_static please
```

## DisableJIT Builds

Run the full set (use either one of the following):

```
@dotnet-bot test nojit tests please
@dotnet-bot test disablejit tests please
```

Run individual builds:

```
@dotnet-bot test Windows daily_disablejit_x64_debug please
@dotnet-bot test Windows daily_disablejit_x64_release please
@dotnet-bot test Windows daily_disablejit_x64_test please
@dotnet-bot test Windows daily_disablejit_x86_debug please
@dotnet-bot test Windows daily_disablejit_x86_release please
@dotnet-bot test Windows daily_disablejit_x86_test please
@dotnet-bot test Windows daily_disablejit_arm_debug please
@dotnet-bot test Windows daily_disablejit_arm_release please
@dotnet-bot test Windows daily_disablejit_arm_test please
```

## Legacy Builds

Run the full set (use either one of the following):

```
@dotnet-bot test dev12 tests please
@dotnet-bot test legacy tests please
```

Run individual builds:

```
@dotnet-bot test Windows 7 daily_dev12_x64_debug please
@dotnet-bot test Windows 7 daily_dev12_x64_release please
@dotnet-bot test Windows 7 daily_dev12_x64_test please
@dotnet-bot test Windows 7 daily_dev12_x86_debug please
@dotnet-bot test Windows 7 daily_dev12_x86_release please
@dotnet-bot test Windows 7 daily_dev12_x86_test please
```

# Test Jenkins CI Script Changes

## Locally

It is also a good idea to validate the changes locally.

You can run the following script to generate XML files to validate changes:
[Local-Job-Gen.ps1](https://github.com/dotnet/dotnet-ci/blob/master/tools/Local-Job-Gen.ps1) 

* Download https://github.com/dotnet/dotnet-ci/blob/master/tools/Local-Job-Gen.ps1
* Run `Local-Job-Gen.ps1` with the old version of the `.groovy` script to create a baseline:

`powershell .\Local-Job-Gen.ps1 -CIFile "C:\dev\ChakraCore\netci.groovy" -CIOutputDir "C:\debugging\netci\master-baseline" -Branch master`

* Run `Local-Job-Gen.ps1` with the changes to the `.groovy` script and output to a different folder:

`powershell .\Local-Job-Gen.ps1 -CIFile "C:\dev\ChakraCore\netci.groovy" -CIOutputDir "C:\debugging\netci\master" -Branch master`

* Do a directory diff to make sure the changes to the XML files are what you expected.

Note: one XML file is created per job generated.

## With Jenkins (on PRs)

When making changes to `*.groovy` scripts related to the Jenkins CI checks, you can request the following
to validate the changes.

```
@dotnet-bot test ci please
```

This will tell you whether the Groovy script compiles.
You will also be able to examine the generated jobs to make sure the changes are what you expected.

It is easier to validate changes locally so that's usually the best place to start.
