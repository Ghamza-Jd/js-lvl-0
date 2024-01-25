# Read from Standard Input

Now that we've added `stdinput-js` package, we can start using it to read from the user.

## Async/Await

### Await

_Await_ is the operation used to wait for a _Promise_ and get its fulfillment value. It can only be used inside an _async function_.

> 📝 Note: Or at the top level of a module. But it's out of our scope.

Let's see what this means in practice:

```js
const name = await stdinput("What's your name?");
```

- `const name` is a constant declaration.
- `await` is waiting for a promise.
- `stdinput` promised us to get an input from the user.
- `"What's your name?"` prompt for the user.

So the above statement means, `stdinput` promised `name` to get the user's input, and `name` is waiting...

### Async

_Async_ function is required to use the `await` keyword, to mark the function as a promise. A function should be a promise if at least one instruction inside of it is a promise.

### A Simple Boilerplate

In other langauges we have a _function_ called `main`.

Functions are callable units, similar to what we've saw in `console.log` and `stdinput`. Another callable example:

```js
console.log(Math.round(10.7));
console.log(Math.round(10.4));
```

We will create an `async function` called main, then call it directly:

```js
async function main() {
}

main();
```

Now we add the `stdinput-js` package and use it.

```js hl=[1,3,4]
const { stdinput } = require("stdinput-js");

async function main() {
    const name = stdinput("Enter your name: ");
    console.log("Hello " + name);
}

main();
```
