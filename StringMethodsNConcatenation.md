```javascript
const firstName = "Bruce";
const lastName = "Wayne";
const age = 43;
const str = "Hello, my name is Optimus Prime";

let val;

val = firstName + lastName; // 'BruceWayne' -> notice there is no space in between the names

// This is where concatenation comes in

val = firstName + " " + lastName; // 'Bruce Wayne'

// Append

val = "Clark ";
val += "Kent";

val = "Hello, my name is " + firstName + " and I am " + age + " years old.";

// Escaping
val = "That's awesome, I can't wait!";
// OR 'That\'s awesome, I can\'t wait!';

// Length
val = firstName.length; // notice there is no () next to length. This is because () is only for methods. length is considered as 'property'.

// Concat Method
val = firstName.concat(" ", lastName);

// Change Case
val = firstName.toUpperCase(); // BRUCE
val = firstName.toLowerCase(); // bruce

// indeOf()
val = firstName.indexOf("c"); // 3
val = firstName.lastIndexOf("c"); // 1 -> because it's counting from right to left.

val = firstName.indexOf("l"); // -1 -> returns -1 by default if it can't find the letter in the word.

// charAt()
val = firstName.charAt("2"); // u

// Get last char
val = firstName.charAt(firstName.length - 1); // e

// substring()
val = firstName.substring(0, 3); // Bruc

// slice()
val = firstName.slice(0, 3); // Bruc

// Difference between substring() & slice() is slice() is able to take in -ve numbers
val = firstName.slice(-2); // uce

// split()
val = str.split(" "); // splits the words into an array separated by a single white space.

// replace()
val = str.split("Optimus", "Sentinel"); // "Hello there, my name is Sentinel Prime".

// includes()
val = str.includes("Hello"); // true -> returns a boolean(true/false).
```
