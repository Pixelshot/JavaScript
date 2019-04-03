**Different type/style of an array**

```javascript
const numbers = [1, 2, 3, 4, 5];
const number2 = new Array(5, 4, 3, 2, 1);
const fruit = ["Apple", "Orange", "Mango", "Banana"];
const mixed = [8, "Hello!", true, undefined, null, { a: 1, b: 1 }, new Date()];
// console.log(mixed);

let val;
// initialize val to mutate the variable in order to show different outcomes.

// To know how many items are in the array
val = numbers.length;

// Check if is an Array;
val = Array.isArray(numbers); // returns true
val = Array.isArray("Hello"); // returns false
// Checking to see if a string is an array will return false.

// Get single value
val = numbers[3]; // returns 4. Index begins with 0
val = numbers[0]; // returns 1

// Insert into array
numbers[2] = 100; // numbers = [1, 2, 100, 3, 4, 5];

// Find index of value
val = numbers.indexOf(4); // return 3
// console.log(val);
```
