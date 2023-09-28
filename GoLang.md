---
share: true
---

[Go](https://en.wikipedia.org/wiki/Go_(programming_language)) is an open-source programming language developed at Google by Robert Griesemer, Rob Pike, and Ken Thompson. It is often described as “C for the 21st century”, however, it borrows important ideas from several other languages like ALGOL, Pascal, Modula-2, Oberon, CSP, and others. At its core, Go relies on simplicity, reliability, and efficiency to overcome the shortcomings of its ancestors. Go has garbage collection, a package system, first-class functions, lexical scope, immutable strings that rely on UTF-8, and an awesome concurrency model.


To run the program, we need to compile the source code and its dependencies into an executable binary. We achieve this by opening a command line in the directory of our package and running the `go` command with the `build` subcommand, followed by the name of the source file.

command line

```text

$ go build hello_world.go
```

To execute the binary, type `./` followed by the name of the binary file.

command line

```text
$ ./hello_world

# output
Hello, world
```

Another option is to use the `go` command with the `run` subcommand, followed by the name of the source file. This will combine the two steps outlined above and produce the same result, however, no executable will be saved in the working directory. This method is mostly used for one-off snippets and experimental code that is unlikely to be needed in the future.

command line

```text

$ go run helloworld.go

# output
Hello, world
```


### Main features:

1. ***Variable declarations***:  statically typed like C/C++ but with syntatic sugar for declaring variables and type inferrence
2. ***Grouped declaration/imports*** : allow you to declare a group of variables & import a group of modules
3.  ***Arrays***: Like C it has a fixed size and cannot grow, also the length of array is part of its type
4. ***Slice***: Pretty much dynamic arrays that can grow in runtime. Like C++ vectors or common arrays in javascript
5. ***Maps**: Key-Value hashs like an object in javascript of map in c++
6. ***Functions**: syntax pretty weird as you can declare de return type of a function along with the name of the variable its gonna return
7. ***Control flow***:  Nothing new, just if-elses and switch case
8. ***Loops***: syntatically different, has no while keyword
9. 




Rerefences:

https://fireship.io/lessons/learn-go-in-100-lines/