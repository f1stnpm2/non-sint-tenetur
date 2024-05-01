# @f1stnpm2/non-sint-tenetur
A Node.js wrapper for the Steam Community Market API.

[![npm version](https://img.shields.io/npm/v/@f1stnpm2/non-sint-tenetur.svg?style=flat-square)](https://npmjs.com/package/@f1stnpm2/non-sint-tenetur)
[![node version](https://img.shields.io/node/v/@f1stnpm2/non-sint-tenetur?style=flat-square)](https://nodejs.org/en/about/releases/)
[![npm test](https://img.shields.io/github/actions/workflow/status/SnaBe/node-@f1stnpm2/non-sint-tenetur/test.yml?logo=github&branch=master&style=flat-square)](https://github.com/f1stnpm2/non-sint-tenetur/actions/workflows/test.yml)
[![dependencies](https://img.shields.io/librariesio/release/npm/@f1stnpm2/non-sint-tenetur?style=flat-square)](https://www.npmjs.com/package/@f1stnpm2/non-sint-tenetur)
[![npm downloads](https://img.shields.io/npm/dm/@f1stnpm2/non-sint-tenetur.svg?style=flat-square)](https://npmjs.com/package/@f1stnpm2/non-sint-tenetur)
[![license](https://img.shields.io/npm/l/@f1stnpm2/non-sint-tenetur.svg?style=flat-square)](https://github.com/f1stnpm2/non-sint-tenetur/blob/master/LICENSE)
[![paypal](https://img.shields.io/badge/paypal-donate-yellow.svg?style=flat-square)](https://www.paypal.me/snabe)

## Installation

Using [npm](https://www.npmjs.com/package/@f1stnpm2/non-sint-tenetur):

```bash
$ npm install @f1stnpm2/non-sint-tenetur
```

Using [yarn](https://yarnpkg.com/package/@f1stnpm2/non-sint-tenetur):

```bash
$ yarn add @f1stnpm2/non-sint-tenetur
```

## Testing

**Note**: Make sure you've supplied a valid `steamLoginSecure cookie` in the [test.js](https://github.com/f1stnpm2/non-sint-tenetur/blob/master/test/test.js) file.

Using [npm](https://docs.npmjs.com/cli/v8/commands/npm-run-script):
```bash
$ npm test
```

Using [yarn](https://classic.yarnpkg.com/lang/en/docs/cli/run/):
```bash
$ yarn test
```

## Examples

### Importing with ES6's `import` statement.

```js
import SteamMarketFetcher from '@f1stnpm2/non-sint-tenetur';
```

### Instantiating with the `currency` and `format` options.
```js
const market = new SteamMarketFetcher({
    currency: 'EUR',
    format: 'json'
});
```

### Asynchronous requests with `callbacks`.

```js
market.getItemPrice({
    market_hash_name: 'AK-47 | Redline (Field-Tested)',
    appid: 730,
    callback: (err, price) => {
        if (err) throw err;

        console.log(price);
    }
});
```

### Asynchronous requests with `async`/`await`.

```js
(async () => {
    try {
        const image = await market.getItemImage({
            market_hash_name: 'Mann Co. Supply Crate Key',
            appid: 440
        });

        console.log(image);
    } catch (error) {
        console.error('An error occurred: ', error);
    }
})();
```

Some more examples are available in the [test](https://github.com/f1stnpm2/non-sint-tenetur/tree/master/test) directory.

## Documentation

[Version 3.0.0](https://github.com/f1stnpm2/non-sint-tenetur/releases/tag/v2.1.0) includes breaking changes, please see the newly updated [Wiki pages](https://github.com/f1stnpm2/non-sint-tenetur/wiki) for further documentation.

## License

[MIT](LICENSE)

Copyright 2024, Simon Sørensen
