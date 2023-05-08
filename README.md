# expect-webdriverio-async-test

This repo demonstrates the need for [webdriverio/expect-webdriverio#962](https://github.com/webdriverio/expect-webdriverio/pull/962) for
the latest version of WebDriver.IO 7.

## Repro environment

This repository was bootstrapped using `@wdio/cli` with TypeScript enabled and with the default sample tests.
A few dependencies were changed manually to resolve all necessary peer dependencies.

This was tested on VSCode 1.78.0 and macOS Ventura 13.3.1, with the following npm dependencies:

* expect-webdriverio v4.2.3
* Node.js v16.14.2
* TypeScript v5.0.2
* WebDriver.IO v7.31.1 (or latest v7 version, depending on the package)

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
