*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-gif](http://github.com/sindresorhus/is-gif). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-gif`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-gif [![Build Status](https://travis-ci.org/sindresorhus/is-gif.svg?branch=master)](https://travis-ci.org/sindresorhus/is-gif)

> Check if a Buffer/Uint8Array is a [GIF](http://en.wikipedia.org/wiki/Graphics_Interchange_Format) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-gif
```

```sh
$ bower install --save is-gif
```

```sh
$ component install sindresorhus/is-gif
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isGif = require('is-gif');
var buffer = readChunk('unicorn.gif', 0, 3);

isGif(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.gif');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isGif(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isGif(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 3 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
