# Factory Functions



## 190 - Factory Functions

### Factory functions are useful especially when we want to enter the same value into different functions

Both functions returns the **same color** only in **different format**

```javascript
function hex(r, g, b) {
  return '#' + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
}

function rgb(r, g, b) {
  return `rgb(${r}, ${g}, ${b})`;
}

hex(255, 100, 25);
rgb(255, 100, 25);
```

But it's time consuming and troublesome having to call the functions everytime we want a new color

### This is where a Factory Function will be useful

#### Factory Function

* An **Object** that not only would **automatically call** both **methods**, it also **stores property values** of those functions on the **Object**

**Observation**: Function `makeColor()` acts as a **wrapper** for the Object color

```javascript
function makeColor(r, g, b) {
  const color = {};

  color.r = r;
  color.g = g;
  color.b = b;
  color.rgb = function () {
    const { r, g, b } = this;
    return `${r}, ${g}, ${b}`;
  };

  color.hex = function () {
    const { r, g, b } = this;
    return '#' + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
  };
  return color;
}
```

* By Storing a **factory function** as **variable**, we can directly **manipulate** its **object values**

```javascript
const firstColor = makeColor(155, 80, 30);

firstColor.r = 255;
< 255

firstColor.rgb()
< "rgb(255, 80, 30)"
```

#### The downside of factory function

* Everytime we declare a new constant for `makeColor()`:

```javascript
const secondColor = makeColor(321, 32, 54);
```

* Instead of being referenced\(like `__proto__`\), those two functions inside of the color Object are considered as a newly created ones.
* We can prove this by comparing same function on two different constants:

```javascript
> firstColor.rgb === secondColor.rgb
< false
```

## 191 - Constructor Functions

* A function that **starts with Capital Letter** indicates that it's a **Constructor** `function()`

```javascript
function Car(type, model, color) {
  this.type = type;
  this.model = model;
  this.color = color;
}
```

* When defining a **Constructor** `function()`, `this` is referenced to the `Window Object`. But **why** would we want to do that?
* Because of the `new` **Operator**
* When we call `new` **before** `function()`, the **behaviour changes**:

  ```javascript
  new Car(SUV, Ford, Blue);
  ```

* `new` returns an **Object**\(based of the function's name\) containing **properties** we've assigned using `this`
* `new` basically does the **first and last step** of **factory function**
* The **difference** is `new` creates a `__proto__` property that sets the **constructor** to the `function()` itself
* This will then **allow** us to set **methods** to the `prototype` **instead** of Objects individually
* But creating a function inside of the main function works differently.

```javascript
function Car(type, model, color) {
  this.type = type;
  this.model = model;
  this.color = color;
  this.carDetails = function () {
    return `Car type: ${type}, model: ${model}, color: ${color}`;
  };
}

// This will not work.
// carDetails function would still be added on each object
```

The workaround for this is to **create** the `function()` **outside** and **link** it with `.prototype`

```javascript
Car.prototype.carDetails = function () {
  return `Car type: ${type}, model: ${model}, color: ${color}`;
};
```

* This will **insert** `carDetails` into `__proto__` instead of the **Object** itself

So now if you make a comparison between two constants like we did with factory function, we'll see a **different result**

```javascript
const firstCar = new Car(SUV, Ford, Blue)
const secondCar = new Car(Sedan, Kia, Red)

> firstCar.carDetails === secondCar.carDetails;
< true
```

