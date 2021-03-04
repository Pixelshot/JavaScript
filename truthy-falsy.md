# Truthy / Falsy

#### There are 5 `falsy` values

* false
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
