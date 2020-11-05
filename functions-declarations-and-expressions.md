# Functions Declarations & Expressions

```javascript
// =============== FUNCTION DECLARATIONS ===============
function name(parameter(s)/argument(s)) {
  // a Function should have a max of 3 parameters/arguments. Anything more means the function is doing too much.
  // Consider breaking into smaller functions if there's more than 3 parameters,arguments.
 console.log('Hello');
 return 'Hello'; // This will not return any result in the console. In order to see this result, one must wrap the calling of the function below with console.log()[see eg 1.0].
}

name(parameter(s)/argument(s));
console.log(name(parameter));
// ======================================================================

function greet(firstName, lastName) {
  return 'Hello' + firstName + " " + lastName;
}

console.log(greet('John', 'Stewart')); // returns Hello John Stewart
// If we don't provide any variable to the argument(s), it'll return undefined.
// i.e "Hello undefined undefined"

// ======================================================================

// =============== SETTING UP DEFAULT PARAMETER(S) ===============
// =============== ES5 METHOD ===============
function greet(firstName, lastName) {
  if ( firstName === "undefined" ) { firstName = "John" }
  if ( lastName === "undefined" ) { lastName = "Stewart" }
  return 'Hello' + firstName + " " + lastName;
}

// =============== ES6 METHOD ===============
function greet(firstName = "John", lastName = "Stewart") {
  return "Hello" + firstName + " " + lastName;
}

console.log(greet());
// ======================================================================

// =============== FUNCTION EXPRESSIONS ===============
// Function expression is basically putting a function as a variable assignment.
// Usually when a function is declared as a variable, the function is considered as "anonymous function" which basically means the function has no name.
// eg.
const square = function() {
  // enter code here..
}; // Since the function is a "variable", we can provide a semicolon; to the function.
// But it's important to note that declaring a function that is not anonymous will still work as well.

const square = function(x = 3) {
  return x * x;
}

console.log(square()); // returns 9. 3 has been set as the default number.
console.log(square(8)) // returns 64.


// =============== IMMEDIATELY INVOKE FUNCTION EXPRESSIONS(IIFE) ===============
// An Immediately-invoked Function Expression is a way to execute functions immediately, as soon as they are created.
// Declare and run at the same time.
// Expression is created when it is inside a (parantheses).

// Syntax for an IIFE is as follows:
(function(){
 console.log('This is an IIFE Function/Expression');
})();

// With Parameter(s)
(function(name){
  console.log('Hello' + name);
})('Kal-El'); // the argument is provided in the second (parentheses)
// returns 'Hello Kal-El'

// PROPERTY METHODS
// When a function is put inside an Object, it's called a Method.
const todo = {
  add: function add() {
    console.log('Add something to the list...');
  },
  edit: function edit(id) {
    console.log(`Edit item number ${id}`);
  }
}

// We can also define the function outside of the todo scope:

todo.delete = function delete() {
  console.log('Delete this todoList...');
}

// Way to call the functions
todo.add(); // Add something to the list...
todo.edit(8); // returns 'Edit item number 8'
todo.delete(); // returns Delete this todoList...
```

