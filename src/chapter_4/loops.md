# Loops

_Loops_ are a fundamental concept in programming that allow you to execute a block of code repeatedly until a certain condition is met. JavaScript provides several types of loops, but the most commonly used are the _for loop_ and the _while loop_.

## The While Loop

The `while`` loop is used when you want to repeat a block of code an unknown number of times until a specified condition is met.

Syntax:

```js
while (condition) {
  // code to be executed
}
```

Example:

```js
let i = 0;
while (i < 5) {
  console.log(i); // This will print numbers 0 through 4
  i++;
}
```

Exercise:

Q: Write a program that **keeps** on asking the user to enter a number, logs the double of the number, and the program only stops when the user enters a negative number.

A:

```js
let i = 0;
while (i > 0) {
    i = await stdinput("Enter a number: ");
    console.log(i * 2);
}
```

## The For Loop

The `for` loop is often used when you know how many times you want to loop. It has three parts: initialization, condition, and increment/decrement.

Here's the syntax:

```js
for (initialization; condition; increment/decrement) {
    // code to be executed
}
```

Example:

```js
for (let i = 0; i < 5; i++) {
  console.log(i); // This will print numbers 0 through 4
}
```

Exercise:

Q: Write a program that asks the user to enter 2 numbers (x and y), then logs the the multiplication of the numbers. You should achive that using loops and addition, multiplication is not allowed.

A:

```js
let x = await stdinput("Enter x: ");
let y = await stdinput("Enter y: ");
let sum = 0;
for (let i = 0; i < x; i++) {
    sum += y;
}
console.log(sum);
```

Exercies:

Q: Write a program that asks the user to enter 2 numbers (x and y), then logs the the divition of the numbers. Division operation is not allowed is not allowed.
