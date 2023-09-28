---
share: true
---

Workers are useful for performing CPU-intensive JavaScript operations; do not use them for I/O, since Node.js’s built-in mechanisms for performing operations asynchronously already treat it more efficiently than Worker threads can.