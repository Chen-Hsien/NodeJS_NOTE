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
```
## NPM node package manager
npm is the world's largest software registry.  
### package.json
* mark down which packages do project need to use and it's version
### package-lock.json
* mark down packages come from where
### nodemon
Simple monitor script for use during development of a Node.js app.  
Add it in global to use it   



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

## Build Server with Express.js   
Popular framework in all programming language.  
Easy to use. Light weight for web application.   
### Express vs Koa
* Express
1. 基於原生NodeJS API
2. 很多HTTP公用Function可以CAll
* Koa
1. 由原班 Express 開發團隊打造的新一代網頁開發框架
2. 目標打造一個更輕量且高效穩定的網頁應用程式與 API 開發工具
3. async, await 取代傳統回調，大大增加錯誤處理能力
4. Koa 沒有在其核心中捆綁任何中間件，使編寫服務器變得快速
### MiddleWare
介於客戶端發出的 HTTP 請求與回傳給客戶端的 HTTP 回應之間進行處理。  
1. 身分驗證：驗證用戶是否有權限訪問特定頁面或 API。
2. 日誌記錄：記錄每一個請求的細節，以便後續進行排錯。
3. 請求處理：解析 HTTP 請求的主體，以便在應用程式中進行處理。
4. 防止跨站請求：設置 HTTP 標頭，以防止跨站請求攻擊。
5. 緩存控制：設置 HTTP 標頭，以改善網站的效能。
```JS
// Middleware
app.use(express.json()); //解析middleware本體
app.use(express.urlencoded({ extended: true })); //解析URL
app.use(cors()); //處理跨域請求, 當AJAX進來的request處於不同網域時即為跨域請求
```
### MVC Model View Control
Model處理資料來源, Controller 處理邏輯








