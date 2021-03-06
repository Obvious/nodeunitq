nodeunitq
=========

[![Build Status](https://travis-ci.org/Medium/nodeunitq.svg?branch=master)](https://travis-ci.org/Medium/nodeunitq)

Simple utilities for nodeunit (like test builders and assertions),
particularly around Q promises.

In normal nodeunit, you add a test like this:

```js
exports.testFunction = function (test) {
  promise.run()
    .fail(failureHandler)
    .fin(test.done.bind(test))
}
```

In nodeunitq, you write a test like this:

```js
var Q = require('Q')
var nodeunitq = require('nodeunitq')
var builder = new nodeunitq.Builder(exports)

builder.add(function testPromise(test) {
  return Q.fcall(function () { return 1 })
})
```

And nodeunitq will take care of the failure handling for you.

License
-------

[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
