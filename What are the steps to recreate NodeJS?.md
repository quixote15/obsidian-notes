---
share: true
---

1. Execute a C++ program and send a JS file as an argument
2. In the c++ program read the JS code and get content as string
3. Send JS string to V8 engine and transform JS CODE into C++ objects
4. Then Call the C++ object on a libuv loop and wait for events - timers, processes and others to be completed
5. Libuv finishes the task and calls back to the given c++ custom function
6. from the custom c++ function invoke the JS method passed as callback to the V8 API


THATS ALL FOLKS!


[[What about Promises on V8]] ?


