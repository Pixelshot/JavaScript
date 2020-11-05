# Object Prototypes

## 188 - What on Earth are Prototypes ?

#### Remember: Arrays are Objects in JavaScript

* **Prototype** is a **Template Object**
* It contains **built-int methods** for that **particular Object**
* Entering `Object.prototype` will return the **available prototype** for that particular **Object**
* `__proto__` is the **reference** of the Object

```javascript
> Array.prototype

< [ constructor: f, concat: f, copyWithin: f, fill: f, find: f, ... ]
```

* To include our own methods in `__proto__`:
  1. Call `prototype` on the targeted **Object**
  2. **Attach** our **function name** next to the **prototype**
  3. **Define** the function

```javascript
String.prototype.sayMeow = () => console.log('Meow!');
```

* Now everytime we call on a string, we can call on `sayMeow` on it

```javascript
const cat = 'asdawd'; // random string

cat.sayMeow()

< Meow!
```

* Since it's an Object, we can make use of `this` keyword

```javascript
String.prototype.yell = function () {
  console.log(this.toUpperCase());
};

const tiger = 'roar!!';

tiger.yell();

< ROAR!!
```

* We can use the same concept to override any built-in methods but this is not suggested

