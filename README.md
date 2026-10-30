<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# rffti

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return an initialized one-dimensional workspace [ndarray][@stdlib/ndarray/ctor] for computing a real-valued discrete Fourier transform.

<section class="installation">

## Installation

```bash
npm install @stdlib/fft-fftpack-rffti
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var rffti = require( '@stdlib/fft-fftpack-rffti' );
```

#### rffti( n\[, options] )

Returns an initialized one-dimensional workspace [ndarray][@stdlib/ndarray/ctor] for computing a real-valued discrete Fourier transform.

```javascript
var getDType = require( '@stdlib/ndarray-dtype' );
var getShape = require( '@stdlib/ndarray-shape' );

var ws = rffti( 4 );
// returns <ndarray>

var dt = String( getDType( ws ) );
// returns 'float64'

var sh = getShape( ws );
// returns [ 42 ]
```

The function has the following parameters:

-   **n**: sequence length.
-   **options**: function options (_optional_).

The function accepts the following options:

-   **dtype**: workspace [data type][@stdlib/ndarray/dtypes]. Must be a real-valued floating-point [data type][@stdlib/ndarray/dtypes]. Default: `'float64'`.

To specify the workspace [data type][@stdlib/ndarray/dtypes], provide a `dtype` option.

```javascript
var getDType = require( '@stdlib/ndarray-dtype' );

var ws = rffti( 4, {
    'dtype': 'float32'
});
// returns <ndarray>

var dt = String( getDType( ws ) );
// returns 'float32'
```

#### rffti.assign( workspace, n )

Initializes a provided one-dimensional workspace [ndarray][@stdlib/ndarray/ctor] for computing a real-valued discrete Fourier transform.

```javascript
var zeros = require( '@stdlib/ndarray-zeros' );

var ws = zeros( [ 42 ], {
    'dtype': 'float64'
});
// returns <ndarray>

var out = rffti.assign( ws, 4 );
// returns <ndarray>

var bool = ( ws === out );
// returns true
```

The function has the following parameters:

-   **workspace**: workspace [ndarray][@stdlib/ndarray/ctor]. Must have a real-valued floating-point [data type][@stdlib/ndarray/dtypes].
-   **n**: sequence length.

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The returned workspace [ndarray][@stdlib/ndarray/ctor] has a length of `(2*n) + 34`.
-   The workspace contains precomputed twiddle factors and factorization data used by the FFTPACK forward and backward real-valued FFT routines.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var getDType = require( '@stdlib/ndarray-dtype' );
var getShape = require( '@stdlib/ndarray-shape' );
var rffti = require( '@stdlib/fft-fftpack-rffti' );

// Initialize a workspace for a sequence of length 8:
var ws = rffti( 8 );
console.log( 'dtype: %s', getDType( ws ) );
console.log( 'shape: [%s]', getShape( ws ).join( ', ' ) );

// Initialize a single-precision workspace:
var ws32 = rffti( 8, {
    'dtype': 'float32'
});
console.log( 'dtype: %s', getDType( ws32 ) );
console.log( 'shape: [%s]', getShape( ws32 ).join( ', ' ) );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/fft-fftpack-rffti.svg
[npm-url]: https://npmjs.org/package/@stdlib/fft-fftpack-rffti

[test-image]: https://github.com/stdlib-js/fft-fftpack-rffti/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/fft-fftpack-rffti/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/fft-fftpack-rffti/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/fft-fftpack-rffti?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/fft-fftpack-rffti.svg
[dependencies-url]: https://david-dm.org/stdlib-js/fft-fftpack-rffti/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/fft-fftpack-rffti/tree/deno
[deno-readme]: https://github.com/stdlib-js/fft-fftpack-rffti/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/fft-fftpack-rffti/tree/umd
[umd-readme]: https://github.com/stdlib-js/fft-fftpack-rffti/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/fft-fftpack-rffti/tree/esm
[esm-readme]: https://github.com/stdlib-js/fft-fftpack-rffti/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/fft-fftpack-rffti/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/fft-fftpack-rffti/main/LICENSE

[@stdlib/ndarray/ctor]: https://github.com/stdlib-js/ndarray-ctor

[@stdlib/ndarray/dtypes]: https://github.com/stdlib-js/ndarray-dtypes

</section>

<!-- /.links -->
