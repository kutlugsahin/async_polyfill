# async_polyfill
es6 async await polyfill

converts function generators into async/await block and returns a Promise

promises should be yielded to syncronize the execution block

# installation
```javascript
npm install --save async_polyfill
```

# usage 
```javascript
var async = require('async_polyfill');

//call generator function without parameters
async(function*(){
  var user = yield fetch('http://example.com/users/1');
  console.log(user);
})();

// call generator functions with parameters
var someUrl = "http://example.com/users/1";

var getUser = function*(url){
  var user = yield fetch(url);
  return user;
}

async(fn)(someUrl).then(user => console.log(user));
```
