# jQuery Evergreen

Small & fast DOM and event library for modern browsers.
Having the same familiar API as jQuery (but without the extra "weight" of modules like `$.ajax`, `$.animate`, and `$.Deferred`), it works great stand-alone or paired up with e.g. Backbone.
The full version is only 7KB minified (2KB gzip), but it's easy to create a custom build to exclude parts you don't need.

The [source](https://github.com/webpro/jquery-evergreen) is written in the ES6 Modules format, and transpiled to an AMD and a CommonJS version using the [ES6 Module Transpiler](http://square.github.io/es6-module-transpiler/). Browserify is used to create a [UMD](https://github.com/umdjs/umd) bundle (supporting AMD, CommonJS, and fallback to browser global).

## Quicklinks

* [Docs](http://webpro.github.io/jquery-evergreen/doc/) (annotated source)
* [Run tests](http://webpro.github.io/jquery-evergreen/test/)
* [Run benchmarks](http://webpro.github.io/jquery-evergreen/benchmark/) (results: [class](http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnIRCxIEVGVzdBiAgICkvo7WCQw?v=3&layout=simple), [constructor](http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnIRCxIEVGVzdBiAgICkyo2ECQw?v=3&layout=simple), [DOM](http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnIRCxIEVGVzdBiAgIDk0Jv_Cgw?v=3&layout=simple), [selector](http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnIRCxIEVGVzdBiAgICkzLXNCAw?v=3&layout=simple))
* [Coverage report](http://webpro.github.io/jquery-evergreen/coverage/dist/jquery-evergreen.js.html)
* [Complexity report](http://webpro.github.io/jquery-evergreen/complexity/)

[![Build Status](https://travis-ci.org/webpro/jquery-evergreen.png?branch=master)](https://travis-ci.org/webpro/jquery-evergreen)
[![Coverage Status](https://coveralls.io/repos/webpro/jquery-evergreen/badge.png?branch=master)](https://coveralls.io/r/webpro/jquery-evergreen?branch=master)
[![Selenium Test Status](https://saucelabs.com/buildstatus/webpro)](https://saucelabs.com/u/webpro)

## Quickstart

### AMD

    # Install
	bower install jquery-evergreen

	# Configure
	paths: {
		'jquery-evergreen': 'lib/jquery-evergreen/dist/jquery-evergreen'
	}

	# Use
	define(['jquery-evergreen'], function($) {
		$('.earth').addClass('evergreen').on('sunrise', '.people', awake);
	});

### Browser Global

    # Install
	bower/npm install jquery-evergreen

	# Configure
	<script src="dist/jquery-evergreen.js"></script>

	# Use
	$('.planet').addClass('evergreen').on('sunrise', '.grass', grow);

## API

### [Array](http://webpro.github.io/jquery-evergreen/doc/array.html)

    each
    every
    filter
    map
    reverse
    some

### [Attr](http://webpro.github.io/jquery-evergreen/doc/attr.html)

	attr

### [Class](http://webpro.github.io/jquery-evergreen/doc/class.html)

	addClass
	removeClass
	toggleClass
	hasClass

### [DOM](http://webpro.github.io/jquery-evergreen/doc/dom.html)

	after
	append
	before

### [Event](http://webpro.github.io/jquery-evergreen/doc/event.html)

	on
	off
	delegate
	undelegate
	trigger

### [HTML](http://webpro.github.io/jquery-evergreen/doc/html.html)

	html

### [NoConflict](http://webpro.github.io/jquery-evergreen/doc/noconflict.html)

	noConflict

### [Selector](http://webpro.github.io/jquery-evergreen/doc/selector.html)

	$
	find


## API (custom builds)

The pre-built "bare" package does not include the `attr` and `html` modules.
The pre-built "full" package also includes the following modules:

### [DOM (extra)](http://webpro.github.io/jquery-evergreen/doc/dom_extra.html)

	appendTo
    remove
    replaceWith

### [Mode](http://webpro.github.io/jquery-evergreen/doc/mode.html)

	isNative
	native

### [Selector (extra)](http://webpro.github.io/jquery-evergreen/doc/selector_extra.html)

	children
	eq
	get
	slice

## But it doesn't even have ...!

As mentioned in the introduction, jQuery Evergreen doesn't have methods for your Ajax, Animation and Deferred needs. Please find your own libraries to fill in the gaps as needed. Here are just some examples:

* Ajax: [microjs#ajax](http://microjs.com/#ajax), [rest.js](https://github.com/cujojs/rest)
* Animation: [microjs#animation](http://microjs.com/#animation), [Move.js](http://visionmedia.github.io/move.js/), [Animate.css](https://daneden.me/animate/)
* Deferred (aka promises): [when.js](https://github.com/cujojs/when), [RSVP.js](https://github.com/tildeio/rsvp.js)

However, feel free to [open an issue](https://github.com/webpro/jquery-evergreen/issues) if you feel an important method is missing.

## Browser Support

[![Selenium Test Status](https://saucelabs.com/browser-matrix/webpro.svg)](https://saucelabs.com/u/webpro)

Latest versions of Chrome, Firefox, Safari, Opera, Chrome Mobile iOS, and Mobile Safari. IE10 and IE11. IE9 only needs a polyfill for `classList` to make these tests pass.

## Performance

Run the [benchmark suite](http://webpro.github.io/jquery-evergreen/benchmark/) to compare the performance of various methods of jQuery, Zepto and jQuery Evergreen.

## Native Mode

You can [opt-in](http://webpro.github.io/jquery-evergreen/doc/mode.html) to work directly with `Node` and live `NodeList` objects, as opposed to the default, wrapped `$` object.

## Custom Build

	npm install jquery-evergreen
	cd jquery-evergreen
	npm install
	gulp --exclude=attr,mode,html

And find the AMD, CommonJS and browserified versions in the `/dist` folder.

## Test

Run the [test suite](http://webpro.github.io/jquery-evergreen/test/). You can also get it from Github or npm, and find the `/test` folder.

## Credits

Many thanks to these sources of inspiration:

* [remy/min.js](https://github.com/remy/min.js)
* [Knockout](https://github.com/knockout/knockout/blob/master/src/utils.js)
* [inkling/Backbone.Native](https://github.com/inkling/backbone.native/blob/master/backbone.native.js)
* [madrobby/zepto](https://github.com/madrobby/zepto/)

## License

[MIT licensed](http://webpro.mit-license.org)

![Analytics](https://ga-beacon.appspot.com/UA-17415234-3/jquery-evergreen/readme?pixel)
