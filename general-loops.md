# General Loops

```javascript
// =============== FOR LOOP ===============
// Takes in 3 parameters:
//  1. Declaration of a variable using let/var(usually using i or x). Can't use const because the variable keeps changing.
//  2. Condition of the loop.
//  3. An increment of the variable in order to keep looping through.
for (let i = 0; i < 10; i++) {
  console.log(i); // returns 0, 1, 2, 3, 4, 5, 6, 7, 8, 9

  // Some examples of what we can do we any type of loop
  // Concatenate:
  console.log("And the number is " + i);
  // If statement
  if (i === 2) {
    console.log("2 is my favorite number");
    continue;
    // When #2 hits, provide the statement from console.log and move on.
    // Without continue, both #2 and the statement will be printed out.
  }

  if (i === 5) {
    // We can do stuff before the break statement below such as console.log().
    console.log("This loop will break when it reaches #5");
    break;
    // Break will stop the loop once it meets the condition which in this case stops at 5.
  }
}
// ==================================================

// =============== WHILE LOOP ===============
// Set the variable outside of the loop.
let i = 0;

// Begin with condition
while (i < 10) {
  // Provide instructions on what we want to do here. Eg:
  console.log("Current number : " + i); // returns 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
  // Increment i(else it'll be an infinite loop)
  i++;
}

// ==================================================

// =============== DO WHILE LOOP ===============
// The difference with DO WHILE compared to WHILE is do while will always run at least once.
let i = 100;

do {
  console.log("Number: " + i);
  i++;
} while (i < 10); // Even though i is NOT less than 10, the loop still runs and returns "Number: 100".

// ==================================================

// =============== LOOPING THROUGH ARRAYS ===============
// Arrays have their own methods to loop through and they're usually the preferred way of looping instead of the ones above here.

const cars = ["Ford", "Honda", "Proton", "Renault"];

// =============== FOR LOOP ===============
for (let i = 0; i < cars.length; i++) {
  console.log(i); // returns Ford Honda Proton Renault
}
// ==================================================

// =============== FOREACH FUNCTION ===============
// This function takes a callback function(which is an anonymous function).
// There are 3 things the anonymous function takes as its parameter.
//  1. The iterator(in the example below the iterator would be 'car').
//  2. The index.
//  3. The entire array itself.

cars.forEach((car, index) => {
  console.log(`${index} : ${car}`); // returns 0: "Ford" | 1: "Honda" | 2: "Proton" | 3: "Renault"
  console.log(array); // returns ["Ford", "Honda", "Proton", "Renault"]
});

// ==================================================

// =============== MAP FUNCTION ===============
// Usually used to return a MANIPULATED array.

const users = [
  { id: 1, name: "John" },
  { id: 2, name: "Martha" },
  { id: 3, name: "Stewart" }
];

// Like forEach(), .map() takes a function as an argument as well.
const ids = users.map(user => {
  return user.id;
});

console.log(ids); // returns [1, 2, 3];

// ==================================================

// =============== FOR IN LOOPS ===============
// Often used for Objects.

const user = {
  firstName: "John",
  lastName: "Doe",
  age: 34
};

for (let x in user) {
  console.log(x); // returns the keys of the object. firstName | lastName | age
  console.log(`${x} : ${user[x]}`); // returns key : value. firstName : John | lastName: Doe | age: 40
}
```

