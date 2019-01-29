# Deep Clone ![Build Status](https://travis-ci.org/joshghent/deepClone.svg?branch=master)

A single method library used for cloning any sort of data structure in javascript!

[![NPM](https://nodei.co/npm/clonedeep.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/clonedeep/)

## Usage
```js
// Import
const clone = require('deepClone');

let objectArray = [{ a: 0, b: 2}, { a: 3, b: 5}];

let clonedObjectArray = clone(objectArray);

objectArray[0][a] = 6;
// => [{ a: 6, b: 2}, { a: 3, b: 5}];

console.log(clonedObjectArray);
// => [{ a: 0, b: 2}, { a: 3, b: 5}]
```

## Contributing
``` bash
# Clone the project locally 
git clone git@github.com:joshghent/deepClone.git deepClone

# Change directory
cd deepClone

# Install dependancies
npm install

# Make your changes + add a test for the new feature or bug you found!
# then...
git add -A && git commit -m "Added an awwwwesome feature." && git push origin master
```
Finally submit a pull request and grab a cup of tea whilst pondering how kickass you feel to be part of the open source community!