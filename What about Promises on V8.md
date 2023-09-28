---
share: true
---

They are not actually async functions, they are just wrappers that creates objects with properties where we can check weather the code was executed or had some error. After that, we check the object is fullfiled we  then invoke a callback


Since promises are part of ECMASCRIPT specification they are supported by V8 and we can pass javascript promises and they'll be handle by [[V8 MICROTASK SYSTEM]]

Example:

In the end everything is a callback and  a promise is just a wrapper object that gets marked as fullfiled when the callback is called by the c++ layer.
```
// creating Promise object  
var myPromise = new Promise(function(resolve, reject) {  
    const number1 = 2;  
    const number2 = 2;  
    // comparing two numbers  
    if(number1 === number2) {  
      // Operation successful  
      resolve();  
    } else {  
      // Error occurred  
      reject();  
    }  
});
```