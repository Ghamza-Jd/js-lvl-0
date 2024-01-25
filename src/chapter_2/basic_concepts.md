# Basic Concepts

## Hello, World

A "Hello, World!" program is often the first written by a student of a new programming language, but such a program can also be used as a sanity check to ensure that the computer software intended run source code is correctly installed, and that its operator understands how to use it.

```js
console.log("Hello, World");
```

`console.log` takes its input and prints it or log it to the console.

As you can see we've surrounded "Hello, World" with double quotation, that because it's of type _String_.

## Datatypes

JavaScript has multiple Datatypes:

1. String
2. _Number_
3. _Boolean_
4. _Object_
5. _Undefined_

- We've encountered a string before, everything surrounded by double quotation is a string.
- Numbers are the usual numbers, they can be integers, decimals, or factions. Numbers must **NOT** be surrounded with double quotes, or it will be considered a string.
- Boolean can either be a true or false.
- Object is a composition of multiple datatypes to form a complex datatype. For example, a Point can have 2 numbers. A contact on your phone a can have a name as a string, a phone number as a number datatype, and a boolean to mark that contact as favourite.

We will encounter `undefined` in the next section.

## Variables

Variables are Containers for Storing Data

```js
let x = "Hello, World";
console.log(x);
```

Each variable has a datatype, in the previous example `x` was a string.

```js
// Numbers
let length = 16;
let weight = 7.5;

// Strings
let color = "White";
let name = "Samer";

// Booleans
let t = true;
let f = false;

// Objects
let contact = { name: "Samer", phone: 71987123, favorite: true };

// Undefined
let x;
console.log(y);
```

The `undefined` is the value of a variable if it hasn't been given one.

> 📝 Note: Anything after the double forward slash (`//`) in a line is called a _comment_.
>
> Comments are ignored when the progrom is running. Its used to explain what a block of code is doing.

## Operations

### Arithmetic Operations

| Operator | Description                  |
| -------- | ---------------------------- |
| +        | Addition                     |
| -        | Subtraction                  |
| *        | Multiplication               |
| **       | Exponentiation (ES2016)      |
| /        | Division                     |
| %        | Modulus (Division Remainder) |
| ++       | Increment                    |
| --       | Decrement                    |

```js
let x = 5;
let y = 10;

let addition = x + y; // 15
console.log("Addition:", addition);

let subtraction = x - y; // -5
console.log("Subtraction:", subtraction);

let multiplication = x * y; // 50
console.log("Multiplication:", multiplication);

let division = x / y; // 0.5
console.log("Division:", division);

let modulus = x % y; // 5
console.log("Modulus:", modulus);

let increment = ++x; // 6
console.log("Increment:", increment);

let decrement = --y; // 9
console.log("Decrement:", decrement);
``````

### Comparison Operators

| Operator | Description                       |
| -------- | --------------------------------- |
| ==       | equal to                          |
| ===      | equal value and equal type        |
| !=       | not equal                         |
| !==      | not equal value or not equal type |
| >        | greater than                      |
| <        | less than                         |
| >=       | greater than or equal to          |
| <=       | less than or equal to             |

```js
let x = 5;
let y = 10;

console.log(x == y); // false
console.log(x === y); // false
console.log(x != y); // true
console.log(x !== y); // true
console.log(x > y); // false
console.log(x < y); // true
console.log(x >= y); // false
console.log(x <= y); // true
```

> 💡 Tip: It is advisable to use `===` over `==` as its less error prune.
>
> Use `==` if you explisitly want to ignore the type comparison.

> 📝 Note: Most languages only have the `==` operation.

## Logical Operators

| Operator | Description |
| -------- | ----------- |
| &&       | logical and |
| \|\|     | logical or  |
| !        | logical not |

```js
console.log(true && true);   // true
console.log(true && false);  // false
console.log(false && true);  // false
console.log(false && false); // false


console.log(true || true);   // true
console.log(true || false);  // true
console.log(false || true);  // true
console.log(false || false); // false


console.log(!true);  // false
console.log(!false); // true
```

## Operations on Strings

```js
// Concatination
let x = "Hello";
let y = "World";
let z = x + y; // HelloWorld
console.log(x);

let a = "1";
let b = "1";
let c = a + b; // 11
console.log(c);

// Comparison
let p = 1;
let q = "1";
console.log(p == q); // true
console.log(p === 1); // false
```


