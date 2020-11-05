# Object Literals

```javascript
const person = {
  firstName: "Steve",
  lastName: "Rogers",
  age: 34,
  email: "SteveRogers@aol.com",
  hobbies: ["music", "sports"],
  address: {
    city: "New York",
    state: "NY"
  },
  getBirthYear: () => {
    return 1918;
  }

  getBirthYearByAge: () => {
    return 2019 - this.age; // to access other parts in the object, we must include "this" keyword.
  }
};

let val;

val = person;
// Get specific value
val = person.firstName; // returns "Steve" - note: this is the preferred method
val = person[firstName]; // returns "Steve"
val = person.age; // returns 34
val = person.email; // return "SteverRogers@aol.com"
val = person.hobbies; // returns ["music", "sports"]
val = person.hobbies[1]; // returns "sports"
val = person.address; // returns {city: "New York", state: "NY"}
val = person.address.city; // returns "New York"
val = person.address[state]; // returns "NY"
val = person.getBirthYear(); // returns 1918. Need to have (parenthesis) since it's a function
val = person.getBirthYearByAge(); // returns 1985
console.log(val);

// Array of Objects
const people = [
  { name: "John", age: 30 },
  { name: "Mike", age: 23 },
  { name: "Nancy", age: 40 }
];

for (let i = 0; i < people.length;) {
  console.log(people[i].name);
  // returns "John", "Mike", "Nancy"
}
```

