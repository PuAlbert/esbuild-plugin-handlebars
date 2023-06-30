# esbuild-handlebars

## fix Cannot read properties of undefined (reading 'call') issue
(Compatible with injection of custom methods for multi-layer nesting, [the original github project](https://github.com/inqnuam/esbuild-plugin-handlebars))

> an [esbuild](https://github.com/PuAlbert/esbuild-plugin-handlebars) plugin to handle ... handlebars!

## Installation

```bash
yarn add -D esbuild-handlebars
# or
npm install -D esbuild-handlebars
```

## Usage

```js
const hbsPlugin = require('esbuild-handlebars');
const path = require('path');

module.exports = [
    hbsPlugin({
		filter: /\.(hbs|handlebars)$/i,
        additionalHelpers: {
            equal: path.join(__dirname, '/helper/template/equal'),
        },
        precompileOptions: {}
    })
];

```

You can also set additionalHelpers and precompileOptions:

```js
const hbsOptions = {
        additionalHelpers: {},
        additionalPartials: {},
        precompileOptions: {}
      }

// usual esbuild config
{
 ...
 plugins: [handlebarsPlugin(hbsOptions)],
 ...
}

```
