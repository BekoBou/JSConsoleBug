# JavaScript Console Bug

This little project shows one bug in browsers. You can check your browser — just [run the tests](https://bekobou.github.io/JSConsoleBug/).

Microsoft Edge [Issue #14495220](https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/14495220/)

```js
// This code should not throw an exception when F12 DevTools are closed
const testBug = function () {
  let log = function () {};
  if (window.console && window.console.log) {
    log = window.console.log;
  }

  log('Bug not found!');
}

try {
    testBug();
} catch (e) {
    alert(e.toString());
}
```
