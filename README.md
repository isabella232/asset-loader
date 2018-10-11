# asset-loader

## Installation

```sh
npm install --save @braintree/asset-loader
```

## Usage

```js
var loadScript = require('@braintree/asset-loader/load-script');

loadScript({
  src: 'https://example.com/some-js-file.js',
  container: domNodeToAddScriptTagTo, // optional, defaults to document.head
  id: 'id-to-give-script-tag', // optional
  dataAttribtues: { // optional
    foo: 'value' // adds data-foo="value" to script tag
  }
}).then(function (script) {
  script; // a reference to the dom node
}).catch(function (err) {
  // occurs when script fails to load or is aborted
});
```

```js
var loadStylesheet = require('@braintree/asset-loader/load-stylesheet');

loadStylesheet({
  href: 'https://example.com/some-css-file.css',
  container: domNodeToAddScriptTagTo, // optional, defaults to document.head and always puts it at the top of the container
  id: 'id-to-give-to-stylesheet-element' // optional
}).then(function (stylesheet) {
  stylesheet; // a reference to the dom node
});
```

Both methods will resolve immediately if the `script` or `link` element is already on the page.

## Development

Run tests:

```sh
npm test
```
