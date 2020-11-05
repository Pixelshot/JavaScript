# Callback Hell



## For JavaScript to know when an asynchronous operation has a result \(a result being either returned data or an error that occurred during the operation\), it points to a function that will be executed once that result is ready. This function is what we call a “callback function”.

[Full Article](https://medium.com/codebuddies/getting-to-know-asynchronous-javascript-callbacks-promises-and-async-await-17e0673281ee)

## 166 - Welcome to Callback Hell

### Refer to the setTimeout\(\) example

```javascript
setTimeout(() => {
  console.log('First function at 1 second');
  setTimeout(() => {
    console.log('Second function at 2 seconds');
    setTimeout(() => {
      console.log('Third function at 3 seconds');
    }, 1000);
  }, 1000);
}, 1000);

// This can be turned into a function

const callbackHell = (input, delay, callback) => {
  setTimeout(() => {
    console.log(console.log(`Function at ${input} second`));
    if (callback) callback();
  }, delay);
};

callbackHell('1', 1000, () => {
  callbackHell('2', 1000, () => {
    callbackHell('3', 1000, () => {
      callbackHell('4', 1000);
    });
  });
});
```

* This will get more complicated as it goes deeper
* `request()` accepts two CALLBACK functions as it's argument: **successful & failure**
* `request(successful, failure)`

