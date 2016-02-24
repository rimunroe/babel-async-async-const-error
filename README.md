# Description

Using `const` within an `async` function within another `async` function results in babel complaining about the reference created by `const` being read-only. Seems to be another instance of (T2892)[https://phabricator.babeljs.io/T2892].

# Instructions

1. clone repo
2. `cd` to its directory
3. run `npm install`
4. run `node_modules/babel-cli/babel.js index.js`

# Results

```
$ node_modules/babel-cli/bin/babel.js index.js
SyntaxError: index.js: "baz" is read-only (This is an error on an internal node. Probably an internal error. Location has been estimated.)
  1 | async function foo() {
  2 |   async function bar() {
  3 |     const baz = {};
  4 |   }
  5 | }
  6 |
```
