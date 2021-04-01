

# Generate Password TS
[![npm version](https://badge.fury.io/js/generate-password-ts.svg)](https://badge.fury.io/js/generate-password-ts)
[![CircleCI](https://circleci.com/gh/junkurihara/generate-password.svg?style=svg)](https://circleci.com/gh/junkurihara/generate-password)
[![Dependencies](https://david-dm.org/junkurihara/generate-password.svg)](https://david-dm.org/junkurihara/generate-password)
[![codecov](https://codecov.io/gh/junkurihara/generate-password/branch/develop/graph/badge.svg)](https://codecov.io/gh/junkurihara/generate-password)

> This library `generate-password-ts` was forked from the original Node.js version `generate-password`:
> [https://github.com/brendanashworth/generate-password](https://github.com/brendanashworth/generate-password).
> This forked version was totally re-written in TypeScript from the original JS version and supports not only Node.js but also browsers without need of `crypto-browserify`.

> Generate Password is a (relatively) extensive library for generating random and unique passwords.

## Install

```bash
$ npm install generate-password-ts --save
```

or

```bash
$ yarn add generate-password-ts
```

## Usage

#### `generate([options])`

Generate one password with the given options. Returns a string.

```javascript
var generator = require('generate-password');

var password = generator.generate({
	length: 10,
	numbers: true
});

// 'uEyMTw32v9'
console.log(password);
```

#### `generateMultiple(amount[, options])`

Bulk generate multiple passwords at once, with the same options for all. Returns an array.

```javascript
var generator = require('generate-password');

var passwords = generator.generateMultiple(3, {
	length: 10,
	uppercase: false
});

// [ 'hnwulsekqn', 'qlioullgew', 'kosxwabgjv' ]
console.log(passwords);
```

### Available options
Any of these can be passed into the options object for each function.

| Name                     | Description                                                           | Default Value |
|--------------------------|-----------------------------------------------------------------------|---------------|
| length                   | Integer, length of password.                                          | 10            |
| numbers*                 | Boolean, put numbers in password.                                     | false         |
| symbols*                 | Boolean or String, put symbols in password.                           | false         |
| lowercase*               | Boolean, put lowercase in password                                    | true          |
| uppercase*               | Boolean, use uppercase letters in password.                           | true          |
| excludeSimilarCharacters | Boolean, exclude similar chars, like 'i' and 'l'.                     | false         |
| exclude                  | String, characters to be excluded from password.                      | ''            |
| strict                   | Boolean, password must include at least one character from each pool. | false         |

*At least one should be true.
