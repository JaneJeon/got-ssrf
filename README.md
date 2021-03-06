<h1 align="center">Welcome to got-ssrf 👋</h1>

[![CircleCI](https://circleci.com/gh/JaneJeon/got-ssrf/tree/master.svg?style=shield)](https://circleci.com/gh/JaneJeon/got-ssrf/tree/master)
[![codecov](https://codecov.io/gh/JaneJeon/got-ssrf/branch/master/graph/badge.svg)](https://codecov.io/gh/JaneJeon/got-ssrf)
[![Version](https://img.shields.io/npm/v/got-ssrf)](https://www.npmjs.com/package/got-ssrf)
[![Downloads](https://img.shields.io/npm/dt/got-ssrf)](https://www.npmjs.com/package/got-ssrf)

> Protect Got requests from SSRF

### 🏠 [Homepage](https://github.com/JaneJeon/got-ssrf)

## Why does this matter?

SSRF is the evil sibling to CSRF that essentially allows RCE against your backends: https://portswigger.net/web-security/ssrf.

This module automatically rejects all suchs requests so you can safely use got without even thinking about it.

## Install

```sh
npm i got-ssrf
```

## Usage

Note that this package is ESM-only; see https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c for what to do if you're using CJS (i.e. `require()`).

```js
import { gotSsrf } from 'got-ssrf'

await gotSsrf(url) // automatically filters requests for safety
```

If you have any other plugins you want to "mix" got-ssrf with, see https://github.com/sindresorhus/got/blob/main/documentation/examples/advanced-creation.js for how to do so. Example:

```js
import got from 'got'
import { gotSsrf } from 'got-ssrf'
import { gotInstance } from 'some-other-got-plugin'

const merged = got.extend(gotSsrf, gotInstance)
```

## Run tests

```sh
npm test
```

## Author

👤 **Jane Jeon <me@janejeon.dev>**

- Website: janejeon.dev
- Github: [@JaneJeon](https://github.com/JaneJeon)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/JaneJeon/got-csrf/issues).

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2022 [Jane Jeon <me@janejeon.dev>](https://github.com/JaneJeon).<br />
This project is [LGPL-3.0](https://github.com/JaneJeon/got-csrf/blob/master/LICENSE) licensed.

TL;DR: you are free to import and use this library "as-is" in your code, without needing to make your code source-available or to license it under the same license as this library; however, if you do change this library and you distribute it (directly or as part of your code consuming this library), please do contribute back any improvements for this library and this library alone.
