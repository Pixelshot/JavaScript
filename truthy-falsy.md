# Truthy / Falsy

#### There are 6 `falsy` values

* false
* undefined
* Zero 0
* Empty string " "
* null
* NaN

```javascript
console.log(Boolean(0)); // -> false
console.log(Boolean(undefined)); // -> false
console.log(Boolean('Hello there')); // -> true
console.log(Boolean({})); // -> true
```

#### Example of truthy/falsy in if else statement:

```javascript
const money = 0;

// JavaScript will do type coersion on anything that is in the parenthesis
if(money) {
    console.log("Don't spend it all at once!")
} else {
    console.log("Get a job!");
}
// -> Get a job!
```

```javascript
let height;
if (height) {
    console.log('YAY! Hegiht is defined');
} else {
    console.log('Height is UNDEFINED!');
}
// > Height is UNDEFINED!
// height is declared but never defined therefore it's considered as undefined
```
