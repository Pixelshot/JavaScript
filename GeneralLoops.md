**General Loops**

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
```
