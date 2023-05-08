# expect-webdriverio-async-test

This repo demonstrates the need for [webdriverio/expect-webdriverio#962](https://github.com/webdriverio/expect-webdriverio/pull/962) for
the latest version of WebDriver.IO 7.

## Actual behaviour

When viewing `example.e2e.ts` in VSCode, lines 9-10 have the following error hint:

```
'await' has no effect on the type of this expression.ts(80007)
```

## Expected behaviour

In `example.e2e.ts`, matchers from `expect-webdriverio` should be asynchronous and `ts(80007)` should
not occur.
