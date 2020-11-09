---
description: Async Functions
---

# Async



## 181 - A Quick Overview of Async Functions

#### Async is JavaScript's way of letting us treat our code as though they are Synchronous

## 182 - The Async Keyword

#### Async is used in front of a function

* **Function Declaration**

```javascript
async function() {
  console.log('hey')
}
```

* **Function Expression**

```javascript
async const sayHi = () => console.log('hi');
```

* **Async functions behave differently. They always return a promise**

```javascript
// How a normal function behaves
function sayHi() {
  return 'Hi!';
}

> Hi!
```

```javascript
// How an async function works
async function sayHi() {
  return 'Hi!'
}

> Promise{<resolved>: "Hi!"}
```

**Note:**

* **Since it returns a promies, we then have access to `.then()` & `.catch()`**
* **For async functions, we don't use resolve and reject.**
* **Instead we handle them with return and throw**
  * **Promise will be resolved regardless of the outcome but if we want to include error handling then we use** `throw`
* **If the functions return a value, the promise will be resolved with that value**

```javascript
async function sayHi() {
  return 'Hi!'; // whatever we return becomes a value
}

sayHi().then((value) => console.log('Promise Resolved: ', value));
```

* **If the function throws an exception, the promise will be rejected**

```javascript
async function add(x, y) {
  const sum = x + y;
  typeof sum !== 'number' ? reject('sum must be number') : resolve(sum);
}

add().then((response) => console.log('Promise resolved with: ', response));
```

