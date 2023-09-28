---
share: true
---

V8 is a [[Javascript runtime]] - it reads javascript strings and compiles into bytecode to execute

Plus, V8 turns javascript code into C++ object instancies.  Actually The way V8 creates those objects can lead to memory leaks and free-after-use issues and thats why there is a proposal for [Usage of Oilpan / V8 C++ Garbage Collector nodejs/node#40786](https://github.com/nodejs/node/issues/40786)) 

One thing that was dimy in my mind was [[How to build and install v8 as a dependency]] becasuse in nodejs this task is as simple as running npm install.


I am thinking of [[Writing an article on V8 explained]]