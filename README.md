`deepest` is [`deeper`'s](https://github.com/othiym23/node-deeper) devious
little brother. It doesn't care about encapsulation or data-hiding -- it finds
all the properties on your objects and makes sure that any two objects are
exactly the same by examining their property descriptors directly. Arguably
useful for comparing objects that have been created using `defineProperty`
magic, and can correctly test some objects that would lead to stack explosions
when used with `deeper` or other more straightforward deep equality testers.
I'd love to know about any situations where this module turns out to be
necessary.

`deepest`, like `deeper`, also comes with shims for use with my three favorite
assertion libraries:

* [Chai](http://chaijs.com/)
* [node-tap](https://github.com/isaacs/node-tap)
* Node's own [assert](http://nodejs.org/api/assert.html)

See the usage instructions for details on how to enable the shims.

## installation

```
npm install deepest
```

## usage

```javascript
// vanilla
var deepEqual = require('deepest')

if (!deepEqual(obj1, obj2)) console.log("yay! diversity!");

// to install the shim against require('assert').deepEqual
require('deepest').patchAssert();

// to patch Chai's eql / deep.equal / et al
require('deepest').patchChai();

// to patch node-tap's ridiculous array of synonyms for deepEqual
require('deepest').patchTap();
```

## caveats

All of `deeper`'s caveats apply here as well. Also, I'm not sure this module is
a good idea.

## license

BSD.
