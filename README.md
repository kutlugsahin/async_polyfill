# async_polyfill
es6 async await polyfill

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

var fn = function*(url){
  var user = yield fetch(url);
  console.log(user);
}

async(fn)(someUrl);
```
