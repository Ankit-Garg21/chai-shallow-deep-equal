# chai-shallow-deep-equal

Will shallowly perform a deep equal assertion. In other terms is consist of checking that an object, or objects graph, is contained within another one (see examples bellow).

[![NPM version](https://badge.fury.io/js/chai-shallow-deep-equal.png)](http://badge.fury.io/js/chai-shallow-deep-equal)
[![Build Status](https://travis-ci.org/michelsalib/chai-shallow-deep-equal.png?branch=master)](https://travis-ci.org/michelsalib/chai-shallow-deep-equal)

## Usage

### Browser

```html
<script src="chai.js"></script>
<script src="chai-shallow-deep-equal.js"></script>
```

### Node

```javascript
var chai = require('chai');
chai.use(require('chai-shallow-deep-equal'));
```

## Assertions

ShallowDeepEqual is available for all chai assertion styles:

```javascript
var a = {name: 'Michel', language: 'javascript'};
var b = {name: 'Michel'};

a.should.shallowDeepEqual(b);
expect(a).to.shallowDeepEqual(b);
assert.shallowDeepEqual(a, b);
```

## Example

```javascript
assert.shallowDeepEqual({name: 'Michel'}, {name: 'Michel', language: 'javascript'}); // true

assert.shallowDeepEqual({
  name: 'Michel',
  tags: [
    'developer'
  ]},
  {
  name: 'Michel',
  language: 'javascript',
  tags: [
    'developer',
    'gamer'
  ]}); // true

assert.shallowDeepEqual({
  length: 2,
  0: {color: 'red'},
  1: {brand: 'samsung'},
  },
  [
    {brand: 'apple', color: 'red'},
    {brand: 'samsung', color: 'blue'},
  ]); // true

assert.shallowDeepEqual({
  name: 'Michel',
  age: 37
  },
  {
  name: 'Michel',
  age: null
}); // false (age should not be defined)
```
