# NPM and Adding Stdinput-js

## NPM

_NPM_ stands for _Node Package Manager_, its a tool for manage _packages_ (or code) written by us or people online so we don't have to reinvent the wheel.

We write our configuration inside the file named `package.json`.

Here's an example:

```json
{
  "name": "nodejs",
  "version": "1.0.0",
  "description": "Learning JavaScript",
  "main": "index.js",
  "keywords": [],
  "author": "Hamza Jadid",
  "license": "ISC",
  "dependencies": {
    "@types/node": "^18.0.6",
    "node-fetch": "^3.2.6"
  }
}
```

We are going to add the `stdinput-js` package that enables us to _read user input_.

```json hl=[11,12]
{
  "name": "nodejs",
  "version": "1.0.0",
  "description": "Learning JavaScript",
  "main": "index.js",
  "keywords": [],
  "author": "Hamza Jadid",
  "license": "ISC",
  "dependencies": {
    "@types/node": "^18.0.6",
    "node-fetch": "^3.2.6",
    "stdinput-js": "3.0.0"
  }
}
```

And now we can _`import`_ code from `stdinput-js`, an outsider code!

```js
const { stdinput } = require("stdinput-js");
```

> ⚠️ Warning: Becareful what packages you're adding, some might be Malicious.
