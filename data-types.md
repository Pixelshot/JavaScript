# Data Types

## Primitive Data Types

#### String

`const name = "Bruce Wayne"`

#### Number

`const age = 42`

#### Boolean

`const isBatman = true`

#### Null

* **Intentionally absence of any value**
* **Must be assigned**
* **We don't come across `null`a lot. At least not as often as `undefined`**

```javascript
// No one is logged in yet...
const loggedInUser = null; //value is explicitly nothing

// A user logs in...
loggedInUser = 'Ricky Bobby';
```

#### Undefined

* **Variables that do not have an assigned value are `undefined`**
* **Think of it as JavaScript's way of saying "I don't know what's going on"**
* **`const`must always be defined** therefore we'll use **`let`**to show **`undefined`**

`let siblings;`

#### Symbols\(ES6\)

`const sym = Symbol();`

### Reference Types - Objects

#### Array

`const hobbies = ["coding", "golf"]`

#### Object Literal

`const address = { city: 'Gotham City', state: 'N/A' }` `const today = new Date();`

#### use typeof method to check data types

`console.log(typeof siblings);` `console.log(today);`

