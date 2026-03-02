/* extract day, hour, minute, second */

```
let dateInMillisecs = Date.now();

// Rounding the value to prevent inconsistencies
// due to floating points
let dateInSecs = Math.round(dateInMillisecs / 1000);
let dateInWords = new Date(dateInMillisecs);

console.log(dateInMillisecs);
console.log(dateInSecs);
console.log(dateInWords);
```

or,

```
let dateInMillisecs = new Date().getTime();

// Rounding the value to prevent inconsistencies
// due to floating points
let dateInSecs = Math.round(dateInMillisecs / 1000);
let dateInWords = new Date(dateInMillisecs);

console.log(dateInMillisecs);
console.log(dateInSecs);
console.log(dateInWords);
```

```
1772422055755
1772422056
Sun Mar 01 2026 19:27:35 GMT-0800 (Pacific Standard Time)
```
