---
share: true
---

Lemon is simple set of methods that enables us to start developing our own JS runtime

repo: https://github.com/nordin-johan/lemon

What I think is the way the author designed lemon:

In the engine folder he declared the Lemon class and methods which a developer can use to create a JS runtime:

```
/engine
	lib/
	Lemon.cpp
	Lemon.hpp
```


Inside the lib folder he fetched the c++ source files from V8 to be used by Lemon.hpp as dependency.

And in the App folder we can create our JS runtime by using functionality exported by Lemon class.