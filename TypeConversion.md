# You can convert almost anything to a string.

`let val;`

##### Number to String

**When** `val = 5;`

```javascript
//Output
console.log(val); // 5`
console.log(typeof val); // number`
console.log(val.length); // undefined -> because .length method only works on a string`
```

**When** `val = String(5);`

```javascript
//Output
console.log(val); // 5`
console.log(typeof val); // string`
console.log(val.length); // 1`
```

##### Boolean to String

`val = String(true);`

```javascript
//Output
console.log(val); // true`
console.log(typeof val); // string`
console.log(val.length); // 4 -> t r u e = 4`
```

### Other examples of string conversion:

**Date to String**
`val = String(new Date());`

**Array to String**
`val = String([1, 2, 3, 4, 5]);`

### Alternate way to convert a string

**toString() method**

```javascript
val = (5).toString();
val = true.toString();
```

---

#### Number to String

```javascript
val = Number("5"); // 5`;
val = Number(true); // 1`
val = Number(false); // 0`
val = Number(null); // 0`
val = Number("hello"); // NaN`
val = Number([1, 2, 3, 4, 5]); // NaN`
```

### Alternate way

```javascript
val = parseInt("100.30"); // 100 -> rounds up to the nearest number`
val = parseFloat("100.30"); // 100.3 -> returns the number to one decimal`
```

**can use toFixed(n) to determine how many decimals we want to return**
`console.log(val.toFixed(2)); // 100.30`

## Type Coercion is when we mix different data types to produce an output

```javascript
const val1 = String(5);
const val2 = 6;

console.log(sum); // 56
console.log(typeof sum); //string -> by default, javascript will convert the other data type into a string.

// We can use any of the string to number methods to convert the result into a number instead.
const sum = Number(val1 + val2); // 11
```
