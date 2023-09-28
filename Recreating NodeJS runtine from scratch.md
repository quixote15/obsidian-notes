---
share: true
---

[[NodeJS]] is a javascript runtime powered by google V8 to run javascript code using JIT (Just in Time ) compilation/transpilation (see [here](https://stackoverflow.com/questions/59807938/the-confusion-with-jit-compilation-in-v8)) and libuv to run async code.

I watched [Ericks videos](https://www.youtube.com/watch?v=ynNDmp7hBdo) to get inspired and expand mu knowlege on the topic
He also mentioned this [c++ video on creating a js runtime](https://www.youtube.com/watch?v=5fWIf2A6Z_s)
### Main components

- V8
- libuv
- c++ layer with methods to help controll data flow 

Main takeaways from the tutorial:

1. Creating a Js runtime has become so popular that there is [[WinterGC - A group for JS runtime creators]] 
2. Checking nodeJS v1 branch could give me an idea of how Rayan Doll implemented the proof of concept for nodejs (2009)
3. All in all NodeJS is just a [[Proxy]] that extends V8 behavior and adds extra functionality










Questions to aswer?

1. How how it is to create a js runtime ?
2. Should I write a Js compiler?
3. [[What are the steps to recreate NodeJS?]]
4. [[What is a JS RunTimer?]]