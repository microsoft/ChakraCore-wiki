Sometimes you might find an issue in a product which embeds ChakraCore like Edge or Node. Sometimes, the issue will really be a problem with ChakraCore, but other times, the issue will actually be more applicable to the product itself. Here's how to file issues related to External projects that embed ChakraCore.

# Edge Issues

If we invite you to reopen your issue as an Edge issue, please open your issue at the following link:

https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/

Most likely you will need to categorize your issue as HTML/DOM.

Please note that some Javascript functions and methods are actually defined by the host (in this case Edge). Objects like `window`, `document`, and `console` and all of their methods are actually defined by the host. So even though you encountered the issue in Javascript code, it doesn't necessarily mean that there is any action to take in ChakraCore.

## But the Edge Issue Tracker sent me here!

If you try to file an issue categorized as JavaScript at the link above, you will see a message like the following:

"For JavaScript Language / Chakra issues, please use Chakra's GitHub."

In fact, that may have been how you were directed to ChakraCore's issue tracker in the first place. If we direct you back there, most likely there is another category that will fit better. In most cases, the issue will fit into HTML/DOM.

# Node-ChakraCore Issues

If we invite you to reopen your issue as a Node-ChakraCore issue, please open your issue at the following link:

https://github.com/nodejs/node-chakracore/issues
