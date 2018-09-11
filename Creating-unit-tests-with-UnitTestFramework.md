To add a new unit test for your change, create `yourtest.js` file in the directory `test/<feature>/`,
where `<feature>` is whichever test directory most closely matches the feature area you are patching.
Give your test a descriptive name so that if the test breaks due to a future change,
it will be easier to tell what the problem is by looking at the test output.

Copy the following template into your test file, and edit it to add your test case.

```js
//-------------------------------------------------------------------------------------------------------
// Copyright (C) Microsoft. All rights reserved.
// Licensed under the MIT license. See LICENSE.txt file in the project root for full license information.
//-------------------------------------------------------------------------------------------------------

WScript.LoadScriptFile("../UnitTestFramework/UnitTestFramework.js");

const tests = [
    {
        name: "TODO: Enter a descriptive name for your first test",
        body: function () {
            // TODO implement your test case here, for example:
            // assert.areEqual(expression1, expression2, "explanation of what this assertion was testing");
            // NOTE: See comments in test/UnitTestFramework/UnitTestFramework.js for more info about what assertions you can use
        }
    },
    // insert as many test cases as you need
    {
        name: "TODO: Enter a descriptive name for your second test",
        body: function () {
            // TODO implement your test case here
        }
    }
];

// The test runner will pass "-args summary -endargs" to ch, so that "summary" appears as argument [0[] to the script,
// and the following line will then ensure that the test will only display summary output (i.e. "PASS").
testRunner.runTests(tests, { verbose: WScript.Arguments[0] != "summary" });
```

Then go to the `rlexe.xml` file in that subdirectory and add an entry for the test based on the following template:

```xml
  <test>
    <default>
      <files>yourtest.js</files>
      <compile-flags>-args summary -endargs</compile-flags>
    </default>
  </test>
```

NOTE: The test runner will treat your test case as passing if the test simply prints `PASS`.
If you use the UnitTestFramework (without adding any additional print statements) and all of your tests pass,
the framework will print `PASS` for you at the end and the test will pass.
If you require additional output as part of telling whether your test was successful, you will need to add a `.baseline` file
containing the expected output of the test, and add that to the XML test entry.

You can configure a test to use a baseline output file, add test tags (useful for excluding a test from certain configurations
where it might be expected to fail for some reason), and additional [ch host](https://github.com/Microsoft/ChakraCore/wiki/ch-cli)
test flags as follows, for example:

```xml
  <test>
    <default>
      <files>yourtest.js</files>
      <baseline>yourtest.baseline</baseline>
      <compile-flags>-args summary -endargs -mic:1 -off:simplejit -ExtendedErrorStackForTestHost-</compile-flags>
      <tags>exclude_test,Slow</tags>
    </default>
  </test>
```