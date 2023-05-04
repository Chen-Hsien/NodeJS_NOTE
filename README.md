# NodeJS_NOTE

## NodeJS Fundamentals
### Asynchronous Synchroneous

### Non-Blocking I/O

### Is Node.js Multi-Threaded

### EventLoop

### Callback Queues

## NodeJS Module System

### How to use require() to import module
```JS
const http = require('http')
const req = http.request('URL', (res)) => {
});
//another one
const { request } = request('URL', (res)) => {
});
```
### Why Use Modules
* Reuse existing code
* Organize code
* Expose only what will be used

### Create Modules
```JS
//https.js
const {send} = require('./request');

function request(url, data){
send(url, data);
}

//request.js
function send(url, data){
console.log('Send Sth')
}
module.exports = {
send,
}
```
