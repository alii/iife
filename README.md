# Simple function helpers like IIFE

This package Includes 3 tiny function helpers:
 - iife
 - tryor
 - tryorLog

## Usage

### 1. iife
```js
const { iife } = require('iife')

// Do this:
const obj = {
  prop: iife(() => {
    return // ...body...
  }),
}

// Instead of this:
const obj = {
  prop: (function() {
    return // ...body...
  })(),
}
```

### 2. tryor

Try to invoke function (first argument) and returns result. 
If function throws exception - returns second argument.

Based on https://www.npmjs.com/package/tryor package.

```js
const { tryor } = require('iife')

// Do this:
const config = tryor(() => JSON.parse(someJson), {})

// Instead of:
let config;
try {
  config = JSON.parse(someJson)
} catch (e) {
  config = {}
}
```

### 3. tryorLog

Works as 'tryor' function above, but also log error to console via console.error(). 

```js
const { tryorLog } = require('iife')

const config = tryorLog(() => JSON.parse(someJson), {})

```

## License

MIT
