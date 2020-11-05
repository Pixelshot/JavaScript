# If Statements & Comparison Operators

```javascript
// if (something) {
  // do something
// } else {
  // do something
// }

// "==" only tests value
// "==="  tests value & type
const id = "100";

// EQUAL TO VALUE
if (id == 100) {
  console.log('CORRECT'); // returns this statement
} else {
  console.log('INCORRECT');
};

// EQUAL TO VALUE AND TYPE
if (id === 100) {
  console.log('CORRECT');
} else {
  console.log('INCORRECT)'; // returns this statement
};

// NOT EQUAL TO VALUE
if(id != 101) {
  console.log('CORRECT'); // returns this statement
} else {
  console.log('INCORRECT');
};

// NOT EQUAL TO VALUE AND TYPE
if(id !== 101) {
  console.log('CORRECT'); // returns this statements
} else {
  console.log('INCORRECT');
};

// HOW TO TEST IF SOMETHING IS UNDEFINED
if(id !== 'undefined') {
  console.log(`the ID is ${id}`);
} else {
  console.log('NO ID');
};

// GREATER THAN OR EQUAL TO
if(id >= 101) {
  console.log('CORRECT');
} else {
  console.log('INCORRECT');
};

// LESS THAN OR EQUAL TO
if(id <= 101) {
  console.log('CORRECT');
} else {
  console.log('INCORRECT');
};

// IF ELSE STATEMENT
const color = 'yellow';

if(color === 'red') {
  console.log('color is red');
} else if(color === 'blue') {
  console.log('color is blue');
} else {
  console.log('color can\'t be found');
};

// LOGICAL OPERATORS
const name = "Steve";
const age = 20;

//  && EQUALS TO AND
// BOTH CONDITIONS MUST RETURN TRUE

if(age > 0 && age < 12) {
  console.log(`${name} is a child`);
} else if(age >= 13 && age <= 19) {
  console.log(`${name} is a teenager`);
} else {
  console.log(`${name} is an adult`);
};

//  || EQUALS TO OR
// ONLY ONE CONDITION NEEDED TO RETURN TRUE

if(age < 16 || age > 65) {
  console.log(`${name} cannot run in race`);
} else {
  console.log(`${name} is able to race`);
};

// WIHTOUT BRACERS(THEY ARE OPTIONAL IN JAVASCRIPT) - note that this method is NOT SUGGESTED.
if(id === 100)
  console.log('CORRECT');
  else
  console.log('INCORRECT');

// TERNARY OPERATOR
console.log(id === 100 ? 'CORRECT' : 'INCORRECT');
```

