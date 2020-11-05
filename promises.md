# Promises

## 167 - Introducing Promises!

### Promise is an Object representing the finished value of an asynchronous operation. Be it successful or failure

#### A couple of things we need to understand when working with promises:

1. When **Creating:** **Once code is done, the creator calls on `resolve` if successful or `reject` if failed**
2. When **Interacting:** `.then()` **to communicate with `resolve` \| `.catch()` with `reject`**
3. For `.catch()` to appear, we need to `throw new Error` inside of `resolve()`
4. This is because `.fetch()` **always returns Resolve no matter the result**
5. **Reject** only happens if **there was an interruption in the connection** or **there is no connection**

#### Remember Colt's story of being promised to get a dog should he gets good grades

* To **create** a **Promise\(\)** we attach **Two Callback functions: resolve & reject** to the Object

`new Promise(resolve, reject);`

* If we don't pass in anything, result of the promise will be **Pending**.

```javascript
const emptyPromise = new Promise((resolve, reject) => {
  // nothing
});
```

* Typing in `emptyPromise` into the `console` will return:

`> Promise {<pending>}`

```javascript
// CREATING A PROMISE
const promiseMade = new Promise((resolve, reject) => {
  const rand = Math.random();

  if (rand < 0.5) {
    // need to execute the function. Not just reference it
    resolve();
  } else {
    reject();
  }
});
```

* To **interact** with a **Promise\(\)** we attach **Two Methods that returns a callback function**: **.then\(\)** **.catch\(\)**
* `resolve` = `.then()` \| `reject` = `.catch()`

```javascript
// INTERACTING WITH A PROMISE

// IF RESOLVED
promiseMade.then(() => {
  console.log('Yay it worked!');
});

// IF REJECTED
promiseMade.catch(() => {
  console.log('An error was found');
});

// Conventional way of writing is to chain them together
promiseMade
  .then(() => {
    console.log('Yay it worked!');
  })
  .catch(() => {
    console.log('An error was found');
  });
```

#### `Promise()` as a Variable

```javascript
const willGetYouADog = new Promise((resolve, reject) => {
  const rand = Math.random();

  if (rand < 0.5) {
    resolve();
  } else {
    reject();
  }
});

// Interacting with the variable

willGetYouADog
  .then(() => {
    console.log('Yes you are getting a dog');
  })
  .catch(() => {
    console.log('No you are not getting a dog');
  });
```



#### `function()` that returns a `Promise()`

```javascript
const makeDog = () => {
  return new Promise((resolve, reject) => {
    const rand = Math.random();

    if (rand < 0.5) {
      resolve();
    } else {
      reject();
    }
  });
};

// Interacting with the function()

makeDog()
  .then(() => {
    console.log('Your lucky day');
  })
  .catch(() => {
    console.log('Not getting anything');
  });
```

