[![npm](https://img.shields.io/npm/l/use-vue.svg?style=flat-square)](https://www.npmjs.org/package/use-vue)
[![npm](https://img.shields.io/npm/v/use-vue.svg?style=flat-square)](https://www.npmjs.org/package/use-vue)
[![npm](https://img.shields.io/npm/dm/use-vue.svg?style=flat-square)](https://www.npmjs.org/package/use-vue)
[![Travis CI](https://img.shields.io/travis/lixinliang/use-vue.svg?style=flat-square)](https://travis-ci.org/lixinliang/muse-vue)
[![bitHound Code](https://www.bithound.io/github/lixinliang/use-vue/badges/code.svg)](https://www.bithound.io/github/lixinliang/use-vue)

# use-vue
> Declare `use vue` in Atom as `use babel`.

## Getting started
```
$ npm install --save use-vue
```

## Usage

```js
import 'use-vue';
import Vue from 'vue/dist/vue';
import app from './app.vue';
import { allowUnsafeNewFunction } from 'loophole';

allowUnsafeNewFunction(() => {
    new Vue(app).$mount('app');
});
```

## CSP

`CSP` is `Content Security Policy`. In `Atom`, it would occur.

```js
new Vue(app).$mount('app'); // CSP Error
```

Use [loophole](https://www.npmjs.com/package/loophole) to avoid this problem.

```js
import { allowUnsafeNewFunction } from 'loophole';

allowUnsafeNewFunction(() => {
    new Vue(app).$mount('app');
});
```

## License

MIT
