# Hangman

In this chapter we will created a hangman and cover most of the things we've learned in this workshop.

```js
const { stdinput } = require("stdinput-js");

// Uncomment the next line to print more verbos messages
// const debug = console.log;
const debug = () => { };

// Our words pool, we're going to select a random one of this array
let words = [];
// The randomly selected word
let selectedWord;
// The masked version of the selected word
// e.g: if the selected was "apple" the masked will be "_____"
let masked;
// Number of allowed mistakes
let health = 5;
// The used characters, to prevent the user of entering the same character twice.
let usedCharacters = [];

// Run the main function
main();

// The Hangman game entry point
async function main() {
    console.log("Welcome to Hangman!");
    // step 1: Load all words
    loadWords("fruits");
    // step 2: Select a random word
    getRandomWord();
    // step 3: Mask the selected word
    maskSelectedWord();
    // step 4: Start the game loop, a loop that repeats until the player either win or lose
    await gameLoop();
}

// The main logic
async function gameLoop() {
    // Repeat steps 1, 2, and 3. As long as the game is not over.
    while (!isGameOver()) {
        // step 1: print the current masked word state
        console.log(prettify(masked));
        // step 2: Ask the user for a letter
        const guess = await stdinput("Enter a letter: ");
        // step 3: Verify the guess
        verifyGuess(guess);
        debug(selectedWord);
    }
    // Print win or lose
    if (isWinner()) {
        console.log("You win!");
    } else {
        console.log("You lose!");
    }
    // Print the word anyway
    console.log("The word was: " + selectedWord);
}

// Load into the words array, this can be done as follows or reading from a file
// or get from words over the internet
function loadWords(category) {
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

// Get a random word from the words pool
function getRandomWord() {
    const randomNumber = Math.random();
    const randomIndex = randomNumber * (words.length - 1);
    const index = Math.round(randomIndex);
    selectedWord = words[index];
}

// Mask the selected word, e.g: if the selected was "apple" the masked will be "_____"
function maskSelectedWord() {
    let m = [];
    for (let i = 0; i < selectedWord.length; i++) {
        m.unshift("_");
    }
    masked = m;
}

// Unmask all matched letters
// e.g:
// - Selected word: banana
// - Masked: ______
// - Letter: a
// - Masked: _a_a_a
function unmaskLetters(letter) {
    debug("Entered the loop");
    for (let i = 0; i < selectedWord.length; i++) {
        debug("Iteration: " + i);
        if (selectedWord[i] == letter) {
            debug("condition passed");
            masked[i] = letter;
            debug(letter);
            debug(masked[i]);
        }
    }
    debug("Exited the loop");
}

// Verifies a guess.
// - Skip if a guess was used before.
// - If a guess is correct, unmask the guess
// - If a guess is wrong, subtract 1 from the health
function verifyGuess(letter) {
    const l = letter.toLowerCase();

    // check if a character was used before
    if (usedCharacters.includes(l)) {
        console.log("Already used try another letter");
        return;
    }
    usedCharacters.push(l);

    // check if the provided letter is a correct guess
    if (selectedWord.includes(l) && l.length == 1) {
        unmaskLetters(letter);
    } else {
        health--;
        console.log("Wrong, current health is: " + health);
    }
}

// Checks if winner, by checking if the masked no longer contains any underscores
function isWinner() {
    return !masked.includes("_");
}

// a function to make the output pretty
// it takes an array and returns a more appealing version of it
// e.g:
// - Input: ['a', 'p', 'p', 'l', 'e']
// - Output: apple
function prettify(arr) {
    return arr.join("");
}

// Checks if a game is over, by either the healt is less than or equal to zero
// or the masked word doesn't contains underscores anymore
function isGameOver() {
    if (!masked.includes("_") || health <= 0) {
        return true;
    } else {
        return false;
    }
}
```
