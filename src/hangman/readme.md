# Hangman

In this chapter we will created a hangman and cover most of the things we've learned in this workshop.

## Load words

The first step in this game is to load the words for our game, we're going to create a function to load the words, so that when we want to change the behaviour of the word loading, like read from a file, from the internet, or even introduce cateogries, we only change this function.

```js
let words = [];

function loadWords(category) {
    // Write code
    if (category == "fruits") {
        words.unshift("apple");
        words.unshift("banana");
        words.unshift("orange");
        words.unshift("grapes");
        words.unshift("cherries");
        words.unshift("Strawberry");
    } else if (category == "pets") {
        words.unshift("cat");
        words.unshift("dog");
    }
}
```

## Get Random Word

Now after loading the words, we should get a random word our of the list, to do that we're going to use the `random` function from the `Math` library.

> NOTE: The random function returns a number from 0 to 1. To change the range we can multiply that with the upper bound of our new range, for example if we want to have a random number between 0 and 12, we multiple the result of the random function with 12. So 0 \* 12 = 0, 1 \* 12 = 12, and 0.5 \* 12 = 6. Then we can round the number to get a nature number instead of a decimal one. (using `Math.round`)

```js
let words = [];
let selectedWord;

function loadWords(category) {
    // Write code
    if (category == "fruits") {
        words.unshift("apple");
        words.unshift("banana");
        words.unshift("orange");
        words.unshift("grapes");
        words.unshift("cherries");
        words.unshift("Strawberry");
    } else if (category == "pets") {
        words.unshift("cat");
        words.unshift("dog");
    }
}

function getRandomWord() {
    const randomNumber = Math.random();
    const randomIndex = randomNumber * (words.length - 1);
    const index = Math.round(randomIndex);
    selectedWord = words[index];
}
```

## Mask The Selected Word

Now we want to replace each character in the word with a mask symbol. `_`, `-`, `*`, or `$`. Anything will work. We're going to use the underscore symbol.

```js
let words = [];
let selectedWord;
let masked;

function loadWords(category) {
    // Write code
    if (category == "fruits") {
        words.unshift("apple");
        words.unshift("banana");
        words.unshift("orange");
        words.unshift("grapes");
        words.unshift("cherries");
        words.unshift("Strawberry");
    } else if (category == "pets") {
        words.unshift("cat");
        words.unshift("dog");
    }
}

function getRandomWord() {
    const randomNumber = Math.random();
    const randomIndex = randomNumber * (words.length - 1);
    const index = Math.round(randomIndex);
    selectedWord = words[index];
}

function maskSelectedWord() {
    let m = "";
    for (let i = 0; i < selectedWord.length; i++) {
        m += "_";
    }
    maskSelectedWord = m;
}
```
