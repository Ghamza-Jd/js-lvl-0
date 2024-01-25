# If and If-Else Statements

## If Statement

The `if` statement is used to conditionally execute a block of code. It's syntax is:

```js
if (/* Condition */) { // if beginning

    // Code

} // if ending
```

> 📝 Note: The `/* */` is also a form of comments, the computer is going to ignore whatever
> between `/*` and `*/`
>
> ```js
> /* Will be ignored */
> console.log("Not ignored");
> ```

### Example, if

Problems: Write a program that asks the user to input a number and prints "Even" if the number is even and "Odd" if the number is odd.

Solution:

```js
const { stdinput } = require("stdinput-js");

async function main() {
    const n = await stdinput("Enter a number: ");

    if (n % 2 == 0) {
        console.log("Even");
    }

    if (n % 2 != 0) {
        console.log("Odd");
    }
}

main();
```

## If-Else Statement

We can write the same program in a better way by using `else`. It's syntax is:

```js
if (/* Condition */) {
    // Code
} else {
    // Another Code
}
```

### Example, if-else

Problems: Write a program that asks the user to input a number and prints "Even" if the number is even and "Odd" otherwise.

Solution:

```js
const { stdinput } = require("stdinput-js");

async function main() {
    const n = await stdinput("Enter a number: ");

    if (n % 2 == 0) {
        console.log("Even");
    } else {
        console.log("Odd");
    }
}

main();
```

## Chain If-Else

We could also chain `if`s and `else`s. Syntax:

```js
if (/* Condition 1 */) {
    // Code
} else if (/* Condition 2 */) {
    // Code
} else if (/* Condition 3 */) {
    // Code
} else {
    // Code
}
```

### Example, chain if-else

Problems: Write a program that asks the user to input a number and prints "Zero" if the number is 0, "Positive" if the number is greater than zero, and Negative otherwise.

Solution:

```js
const { stdinput } = require("stdinput-js");

async function main() {
    const n = await stdinput("Enter a number: ");

    if (n == 0) {
        console.log("Zero");
    } else if (n > 0) {
        console.log("Positive");
    } else {
        console.log("Negative");
    }
}

main();
```

## Grades Problem

Problem:

a. Write a program that asks the user to input a number and prints to the user the corresponding grade letter:

| Number      | Grade |
| ----------- | ----- |
| `[90, 100]` | A+    |
| `[80, 90[`  | A     |
| `[70, 80[`  | B     |
| `[60, 70[`  | C     |
| `[50, 60[`  | D     |
| `[0, 50[`   | F     |

b. Check the upper and lower bounds, the input should not be less than 0 or greater than 100.
