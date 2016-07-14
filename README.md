## Purpose

This repo was created to demonstrate a bug/weird behavior of Backbone.Router#navigate.

### Test case

```js
var Backbone = require('backbone');

var router = new Backbone.Router();
Backbone.history.start();

router.navigate('space%20space');
```

#### Expected result

Url looks something like `http://localhost:3000/space%20space`

#### Actual result

Url looks like `http://localhost:3000/space space`

### Why this is a problem

This breaks URLs when copy pasting them, etc, and in general is inconsistent behavior, because none of the other URLencoded chars get decoded.