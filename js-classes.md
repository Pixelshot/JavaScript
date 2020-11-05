# JS-Classes



## 192 - JS Classes - Syntactical Sugar

Some of the benefit of using `class` instead:

1. We don't have to add methods to the `prototype` manually
2. We don't have to **break up constructor** `function()` and then **separately** add methods

```javascript
function Car(a, b, c) {
  this.a = a;
  this.b = b;
  this.c = c;
}

// In order to add a function in __proto__ we have to define the function outside of the constructor using .prototype
Car.prototype.carDetails = function () {
  return `Car name ${a}, color ${b}, maker ${c}`;
};
```

`class` also defines its Object starting with **Capital letter**. It is a **pattern** for some sort of **Object**.

```javascript
class Color {}
```

A **constructor** `function()` is **always defined** anytime we **create a class**. Its **purpose** is to **execute** anything inside its block **immediately** everytime its class is **called upon**.

```javascript
class Color {
  constructor() {}
}
```

Rewriting `Car function()` above as a `class`:

```javascript
class Car {
  // Remember: Everything that's in the constructor code block will fire everytime we call on its class
  constructor(a, b, c, description) {
    this.a = a;
    this.b = b;
    this.c = c;
    this.description = description;

    // if console.log/return is not a function, then they would fire immediately once the class is called
    // Therefore, usually this would be written in a function() but for the sake of current example we're just going to console.log()
    console.log(
      `Car name ${a}, color ${b}, maker ${c}, description:${description}`
    );
  }
}
```

To **call** a `class`, we use the **same syntax** we've been using with the `new` operator:

```javascript
new Car('X70', 'Red', 'Proton', 'It is a family SUV');
```

#### Methods: The real benefit of creating a `class`

**Memory refresher - Declaring methods in an Object:**

```javascript
class Car {
  constructor(a, b, c, description) {
    this.a = a;
    this.b = b;
    this.c = c;
    this.description = description;
  }

  // Normal syntax:
  // Key = name of function
  // value = function()
  carDetails = function () {
    const { a, b, c, description } = this;
    return `Car name ${a}, color ${b}, maker ${c}, description:${description}`;
  };
}

// ====================================================================================

class Car {
  constructor(a, b, c, description) {
    this.a = a;
    this.b = b;
    this.c = c;
    this.description = description;
  }

  // Shorthand syntax:
  carDetails() {
    const { a, b, c, description } = this;
    return `Car name ${a}, color ${b}, maker ${c}, description:${description}`;
  }
}
```

* `CarDetails()` will be inserted into `__proto__` instead of the Objects individually

#### In a `class`, `this` is referred to the instance of the `class`

**It's referred to each created Object**

```javascript
const car1 = new Car(...);
const car2 = new Car(...);
```

1. `this` is defined in the `constructor()`
2. Everytime we create a **constant** and call on the `new` operator, it then becomes an **Object**
3. `this` inside of the `constructor()` will be **bounded** to that individual **constant**
4. So `this` is then **bounded** to `car1` and `car2` **separately**

#### For methods to interact with each other, we need to call 'this' on the method we want to call inside our current function

```javascript
class Car {
  constructor(a, b, c, description) {
    this.a = a;
    this.b = b;
    this.c = c;
    this.d = d;
    this.description = description;
  }

  carDetails() {
    const { a, b, c, description } = this;
    return `Car name ${a}, color ${b}, maker ${c}, description:${description}`;
  }

  carYear() {
    const { d } = this;
    return `Year: ${d}`;
  }

  carLog() {
    this.carDetails() + this.carYear();
  }
}
```

## 193 - A Bit More Practice with Classes

How to call a `function()` that is **outside** of the **constructor** from the **inside**

```javascript
class Car {
  constructor(a, b, c, description) {
    this.a = a;
    this.b = b;
    this.c = c;
    this.d = d;
    this.description = description;

    // We just use 'this' to call the function()
    this.carDetails()
  }

  carDetails() {
    const { a, b, c, description } = this;
    return `Car name ${a}, color ${b}, maker ${c}, description:${description}`;
  }
```

Using this concept, we can declare **new variables outside** of the `constructor()` and build from there

! All we need to **remember** is that we need to make use of the `function()` **inside** of the `constructor()` to build upon

### Observe! Example below shows how we can turn a SINGLE declaration keyword\(const, let, var\) into a MULTI-LINE variable assignment denoted by commas\(','\)

```javascript
class HSL {
  constructor(r, g, b) {
    // Make r,g,b fractions of 1
    this.r = r;
    this.g = g;
    this.b = b;

    this.callHSL();
  }

  callHSL() {
    const { r, g, b } = this;

    // MULTI-LINE VARIABLE ASSIGNMENT
    const h = 'hello',
      s = 'sup',
      l = 'lel';
    // =================================

    console.log(`${h} ${r}`);

    this.h = h;
    this.s = s;
    this.l = l;
  }

  printHSL() {
    const { r, g, b } = this;
    const { h, s, l } = this;

    console.log(`${h} ${r}`);
  }
}

const parrot = new HSL('Rainbow', 'Gold', 'Blue');
```

## 194 - Extends, Super & Subclasses

#### If we don't **declare** a `constructor()` in **current** `function()`, JS will **use** the `constructor()` from the **extended** `function()`

```javascript
class Pet {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  eat() {
    return `${this.name} is eating!`;
  }
}

class Cat extends Pet {
  meow() {
    return `MEOWWWW!`;
  }
}

> const grumpus = new Cat('Grumpus', 5)
> grumpus
< Cat {name: "Grumpus", age: 5}
```

#### If the interpreter doesn't find the `function()` we're calling in the current `class`, it'll look for it in the extend class

```javascript
class Pet {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  eat() {
    return `${this.name} is eating!`;
  }
}

class Cat extends Pet {
  meow() {
    return `MEOWWWW!`;
  }
}

class Dog extends Pet {
  eat() {
    return `${this.name} is no longer eating`;
  }
}


> const lessie = new Dog('Lessie', 15)
< undefined
> lessie.eat()
< "Lessie is no longer eating"
```

#### super\(\) is going to reference the Class that we're extending from

```javascript
class Pet {
  constructor(name, age) {
    console.log('IN PET CONSTRUCTOR!');
    this.name = name;
    this.age = age;
  }
  eat() {
    return `${this.name} is eating!`;
  }
}

class Cat extends Pet {
  constructor(name, age, livesLeft = 9) {
    console.log('IN CAT CONSTRUCTOR!');
    super(name, age);
    this.livesLeft = livesLeft;
  }
  meow() {
    return `MEOWWWW!`;
  }
}

class Dog extends Pet {
  eat() {
    return `${this.name} is no longer eating`;
  }
}

> const ace = new Cat('ace', 4)
 IN CAT CONSTRUCTOR!
 IN PET CONSTRUCTOR!
```

