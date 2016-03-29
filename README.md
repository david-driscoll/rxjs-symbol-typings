# Rxjs Symbol Shim
The type definition for the rxjs-symbol-shim, this doesn't add anything to the code, it simply gives the compiler the smallest possible set of interfaces to support `Iterable<T>` and `Observablesque<T>`.  

This lets you use the TypeScript compiler, to target `es5` and use the `rxjs` version 5 library.  The key difference here is today, with the `es5` target `Symbol` is not available.  This makes it difficult for the `rxjs` typings to properly define what input types are supported, for example `Iterable<T>`, `ArrayLike<T>`, `Array<T>`, `Promise<T>`, `Observable<T>` and `Observablesque<T>`.

In this scenario both `Iterable<T>` and `Observablesque<T>` use `Symbol` to define their presence, which is the future of ECMAScript.  The future might not be today, but the future is available with tools like [`babel`](babeljs.io).  The goal of this small typing set is to shim in `Symbol` to the typings system, so that TypeScript becomes aware of it's presence.  `Symbol` itself may very well not be useable in your code, but this will let `rxjs` keep up with the future of ECMAScript.

## LICENSE
MIT
