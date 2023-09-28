---
share: true
---


The [v8 doc](https://v8.dev/docs) says: V8 is Google’s open source high-performance JavaScript and WebAssembly engine, written in C++. It is used in Chrome and in Node.js, among others.

But What is an engine in this context? What does it do exactly? What is it reponsible for ? Is it just a library exposing methods with a fancy name on it?


How does it do:

- Implements ECMAScript and WebAssembly
- Compiles and executes js code
- handles memory allocation of objects
- garbage collects objects (This gargage collector is the real gem here!!! Maybe write more about its capability will help nodejs reputation compared to go lang and others?)

