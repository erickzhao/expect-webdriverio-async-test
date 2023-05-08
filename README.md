# expect-webdriverio-async-test

This repo demonstrates the need for [webdriverio/expect-webdriverio#962](https://github.com/webdriverio/expect-webdriverio/pull/962) for
the latest version of WebDriver.IO 7.

## Issue

### Actual behaviour

When viewing `example.e2e.ts` in VSCode, lines 9-10 have the following error hint:

```
'await' has no effect on the type of this expression.ts(80007)
```

### Expected behaviour

In `example.e2e.ts`, matchers from `expect-webdriverio` should be asynchronous and `ts(80007)` should
not occur.

## Testing the fix

The code change from [webdriverio/expect-webdriverio#962](https://github.com/webdriverio/expect-webdriverio/pull/962)
can be easily applied with `patch-package`. To apply the new types in VSCode:

1. Run the `fixme` script via `yarn fixme` to modify your `node_modules` code.
1. Reload your workspace with the `Developer: Reload Window` command in the VSCode command palette.
   This command will restart your editor's TypeScript language service.
