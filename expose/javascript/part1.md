# Part 1

**Question 1.** Line 9 prints: `values added:  20`

`add` is `true` so we go into the `if` block. `result` starts at `0`, then gets set to `10 + 10 = 20`. So it prints `20`.

**Question 2.** Line 13 prints: `final result:  20`

Even though `result` was made inside the `if` block, `var` doesn't care about blocks. It's scoped to the whole function. So `result` is still accessible on line 13 and it's still `20`.

**Question 3.** `var` is function-scoped instead of block-scoped, which means variables declared with it can leak outside of blocks like `if` statements and loops. This can cause confusing bugs. `let` and `const` are block-scoped so they stay contained where you declare them, which is way safer and easier to follow.

**Question 4.** Line 9 prints: `values added:  20`

Same idea as question 1. `add` is `true`, so the `if` block runs, `result` becomes `20`, and line 9 prints it. `let` works fine here since we're still inside the block where it was declared.

**Question 5.** Line 13 throws an error: `ReferenceError: result is not defined`

`let` is block-scoped, so `result` only exists inside the `if` block. Line 13 is outside that block, so it has no idea what `result` is and throws an error.

**Question 6.** Line 9 throws an error: `TypeError: Assignment to constant variable.`

`const` means the variable can't be reassigned after it's set. `result` is set to `0` on line 5, and then line 7 tries to change it to `num1 + num2`. That's not allowed with `const`, so it errors out before line 9 even runs.

**Question 7.** Line 13 never runs either. The code already crashed on line 7 because of the `const` reassignment error. But even if it didn't, `const` is block-scoped just like `let`, so `result` wouldn't be accessible outside the `if` block anyway.
