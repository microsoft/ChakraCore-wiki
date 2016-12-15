Sometimes you might find an issue in a product which embeds ChakraCore like Edge or Node. Sometimes, the issue will really be a problem with ChakraCore, but other times, the issue will actually be more applicable to the product itself. Here's how to file issues related to External projects that embed ChakraCore.

So that we can more easily track external issues and close ChakraCore issues in a timely manner, when you've opened the issue on another issue tracker, please post the link to your new bug report on the GitHub issue you opened.

# Edge Issues

If we identify your issue as an Edge issue, we invite you to open your issue at the following link:

https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/

Most likely you will need to categorize your issue as **HTML/DOM**.

Please note that some JavaScript functions and methods (e.g. `window`, `document`, and `console`) are actually defined by the host (in this case Edge). So even though you encountered the issue in JavaScript code, it doesn't necessarily mean that there is any action to take in ChakraCore.

## But the Edge Issue Tracker sent me here!

If you tried to file an issue categorized as JavaScript at the link above, you will see a message like the following:

"For JavaScript Language / Chakra issues, please use Chakra's GitHub."

In fact, this may have been how you were directed to ChakraCore's issue tracker in the first place. If we direct you back there, most likely there is a category for this issue besides JavaScript that will fit better. In most cases, the issue will fit into HTML/DOM.

# Node-ChakraCore Issues

If we invite you to reopen your issue as a Node-ChakraCore issue, please open your issue at the following link:

https://github.com/nodejs/node-chakracore/issues
