# Part 2

**Question 1.** Line 12 prints: `3`

`i` is declared with `var` in the `for` loop, and since `var` is function-scoped, `i` still exists after the loop ends. The loop runs for `i = 0, 1, 2` (3 elements in the array), and then `i` becomes `3` which fails the condition `i < prices.length`, so the loop stops. Line 12 logs `i`, which is `3` at that point.

**Question 2.** Line 13 prints: `150`

`discountedPrice` is declared with `var` inside the loop, so it's function-scoped and still accessible after the loop. On the last iteration (`i = 2`), `discountedPrice = 300 * (1 - 0.5) = 150`. That's the value it holds when line 13 logs it.

**Question 3.** Line 14 prints: `150`

`finalPrice` is declared with `var` at the top of the function, so it's definitely accessible on line 14. Inside the loop, it gets updated each iteration. On the last one (`i = 2`), `finalPrice = Math.round(150 * 100) / 100 = 150`. So that's what gets logged.

**Question 4.** The function returns `[50, 100, 150]`.

The loop goes through each price in `[100, 200, 300]`, multiplies it by `(1 - 0.5)` to get the discounted price, rounds it, and pushes it into the `discounted` array. So you get `100*0.5=50`, `200*0.5=100`, `300*0.5=150`.

**Question 5.** Line 12 throws an error: `ReferenceError: i is not defined`

Now everything is declared with `let` instead of `var`. `i` is declared with `let` in the `for` loop, so it's block-scoped to the loop. Line 12 is outside the loop, so `i` doesn't exist there and you get a ReferenceError.

**Question 6.** Line 13 throws an error: `ReferenceError: discountedPrice is not defined`

Same deal. `discountedPrice` is declared with `let` inside the `for` loop, so it's block-scoped to that loop. Line 13 is outside the loop, so `discountedPrice` doesn't exist there.

**Question 7.** Line 14 prints: `150`

`finalPrice` is declared with `let` on line 4, which is at the function level (not inside the loop). So it's scoped to the whole function and is accessible on line 14. It gets updated each loop iteration, and after the last one it's `150`.

**Question 8.** The function returns `[50, 100, 150]`.

Same result as question 4. The `let` vs `var` difference doesn't matter here since the loop logic is the same. Each price gets halved and pushed into `discounted`. The console.log lines are all commented out so nothing interferes.

**Question 9.** Line 11 throws an error: `ReferenceError: i is not defined`

`i` is declared with `let` in the `for` loop, so it's block-scoped to the loop. Line 11 is outside the loop, so `i` doesn't exist there.

**Question 10.** Line 12 prints: `3`

`length` is declared with `const` on line 4 at the function level, so it's accessible anywhere in the function. It's set to `prices.length` which is `3` (since the array has 3 elements), and since it's never reassigned, it just stays `3`.

**Question 11.** The function returns `[50, 100, 150]`.

All the console.log lines are commented out so nothing errors. The loop still works the same. `discounted` is `const` but that's fine because we're pushing to the array, not reassigning it. `const` only prevents reassignment, not mutation. So each discounted price gets pushed in and we get `[50, 100, 150]`.

**Question 12.**
A. Accessing name: `student.name`
B. Accessing Grad Year: `student['Grad Year']`
C. Calling greeting: `student.greeting()`
D. Accessing Favorite Teacher's name: `student['Favorite Teacher'].name`
E. Accessing index zero of courseLoad: `student.courseLoad[0]`

**Question 13.** Arithmetic
A. `'3' + 2` -> `'32'` - `+` with a string does concatenation, so `2` gets converted to `'2'` and stuck onto `'3'`.
B. `'3' - 2` -> `1` - `-` only works with numbers, so `'3'` gets converted to `3`. Then `3 - 2 = 1`.
C. `3 + null` -> `3` - `null` converts to `0` in math, so `3 + 0 = 3`.
D. `'3' + null` -> `'3null'` - `+` with a string concatenates, so `null` becomes the string `'null'`.
E. `true + 3` -> `4` - `true` converts to `1`, so `1 + 3 = 4`.
F. `false + null` -> `0` - `false` is `0` and `null` is `0`, so `0 + 0 = 0`.
G. `'3' + undefined` -> `'3undefined'` - `+` with a string concatenates, so `undefined` becomes the string `'undefined'`.
H. `'3' - undefined` -> `NaN` - `-` converts both to numbers. `'3'` becomes `3` but `undefined` becomes `NaN`, and anything minus `NaN` is `NaN`.

**Question 14.** Comparison
A. `'2' > 1` -> `true` - `'2'` gets converted to `2`, and `2 > 1` is `true`.
B. `'2' < '12'` -> `false` - Both are strings so it compares character by character. `'2'` vs `'1'` (first char of `'12'`), and `'2'` is greater than `'1'`, so it's `false`.
C. `2 == '2'` -> `true` - `==` does type coercion, so `'2'` becomes `2`, and `2 == 2` is `true`.
D. `2 === '2'` -> `false` - `===` is strict equality with no type coercion. A number and a string are different types, so it's `false`.
E. `true == 2` -> `false` - `true` converts to `1`, and `1 == 2` is `false`.
F. `true === Boolean(2)` -> `true` - `Boolean(2)` is `true` since any non-zero number is truthy. `true === true` is `true`.

**Question 15.** `==` checks if two values are equal after converting them to the same type (type coercion). `===` checks if two values are equal without any type conversion. Both the value and the type have to match. For example, `2 == '2'` is `true` because `'2'` gets converted to `2`, but `2 === '2'` is `false` because one is a number and the other is a string.

**Question 17.** The result is `[2, 4, 6]`.

`modifyArray` loops through each element in `[1, 2, 3]` and calls the callback (`doSomething`) on each one. `doSomething` just multiplies the number by 2. So it goes: `1*2=2`, `2*2=4`, `3*2=6`, and each result gets pushed into `newArr`. The function returns `[2, 4, 6]`.

**Question 19.** The output is:
```
1
4
3
2
```

`1` prints first since it's just a regular `console.log`. Then the two `setTimeout` calls get scheduled but don't run yet. They get put in the event queue. `4` prints next since it's also a regular `console.log`. After that, `3` prints because even though its timeout is `0ms`, it still had to wait for the main code to finish before running. Finally, `2` prints after 1000ms since it had a 1 second delay.