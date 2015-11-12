#Sequential promise executor for ES2015

Module for executing promises in sequense.

```javascript
var promiseq = require('promoseq');

function one() {
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve('1');
        },1000);
    });
}

function two() {
    return new Promise(function(resolve, reject) {
        setTimeout(function() {
            resolve('2');
        },1000);
    });
}

promoseq([one, two]).then(function(result) {
    console.log(result[0]) // '1'
    console.log(result[1]) // '2'
});
```