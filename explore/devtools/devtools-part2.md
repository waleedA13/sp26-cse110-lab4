# DevTools Part 2 - Debugging

**What was the bug?**

The bug is in the `calculateSum()` function in `explore.js`. The `num1` and `num2` values are read from `document.getElementById("num1").value` and `document.getElementById("num2").value`, which returns strings. So when `result = num1 + num2` runs, it does string concatenation instead of addition. For example, entering 5 and 3 gives `"53"` instead of `8`.

**How would you fix it?**

Convert `num1` and `num2` to numbers before adding them. You can use `parseInt()`, `parseFloat()`, or `Number()`. For example, change the lines in `printSum()` to:

```js
let num1 = parseInt(document.getElementById("num1").value);
let num2 = parseInt(document.getElementById("num2").value);
```
