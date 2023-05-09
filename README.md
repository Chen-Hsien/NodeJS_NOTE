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

}
```
### ES6
* require -> import
* module.exports = {} -> export {}
```JS
import {send} = from './request.mjs';
export{ send,};
```
### Using index.js to export module
But seldom need to use this.   
create a dir internals/index.js and put request.js into internals.   
```JS
//index.js
module.exports ={
...require('./request')
}
//https.js
const internals = require('./internals')
function makeRequest(url, data){
internals.request.send(url, data)
}
## NPM node package manager
npm is the world's largest software registry.  
### package.json
* mark down which packages do project need to use and it's version
### package-lock.json
* mark down packages come from where
### nodemon
Simple monitor script for use during development of a Node.js app.  
Add it in global to use it   

## Build Server with Express.js

## NodeJS Package Management
NPM Node Packagee Manager   
### Semantic Version
MAJOR version when you make incompatible API changes.  
MINOR version when you add functionality in a backward compatible manner.  
PATCH version when you make backward compatible bug fixes.  
Example: 1.0.0 < 2.0.0 < 2.1.0 < 2.1.1.  
### Package-lock.json and Versioning
內紀錄更詳細的套件來源, 版本, 相依套件等資訊   
而版本部分採用Semantic Version紀錄













