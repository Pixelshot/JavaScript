# Arrays

**Different type/style of an array**

```javascript
const numbers = [1, 2, 3, 4, 5, 78, 92];
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

// MUTATING ARRAYS

// Add on to front
numbers.unshift(125); // numbers = [125, 1, 2, 3, 4, 5];
// Take off from front
numbers.shift; // numbers = [2, 3, 4, 5];
// Add on to end
numbers.push(240); // numbers = [1, 2, 3, 4, 5, 240];
// Take off from end
numbers.pop(); // numbers = [1, 2, 3, 4];
// Splice values - take values out from the array
numbers.splice(1, 3); // returns = 2,3,4. Left parameter is starting position whilst right param equals end position.
// Reverse
numbers.reverse(); // numbers = [5, 4, 3, 2, 1];
// Concatenate array
val = numbers.concat(numbers2); // returns [1, 2, 3, 4, 5, 5, 4, 3, 2, 1];
// Sorting arrays
val = fruit.sort(); // returns ["Apple", "Banana", "Manggo", "Orange"];

// "Compare function" to sort
val = numbers.sort(function(x, y) {
  return x - y;
});

// "Compare function" to reverse sort
val = numbers.sort(function(x, y) {
  return y - x;
});

// Find
function over50(num) {
  return num > 50;
}

// val = numbers.find(over50); return [78, 92]

// console.log(numbers);
// console.log(val);
```

