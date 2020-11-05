# Asynchronous

## 164 - JS is Single Threaded

* Upon going through a script, JavaScript will start to run one thing at a time

```javascript
console.log('I Happen First');
alert('Hi there!');
console.log('I Happen Second');

// Result will be:

// 1. I Happen First in console
// 2. pop up of Hi there!
// But the second console.log() will not be executed until we've removed the alert
// Once removed I Happen Second will appear in the console
```

* It's also worth noting that JavaScript **DOES NOT WAIT** for the code. Once it's passed to the browser, it doesn't care about the code anymore. it'll move on to the next line immediately.
* It's all up to the browser to return the result of the function to JavaScript.
* This is a **GOOD EXAMPLE** on why we use **callback functions**

```javascript
setTimeout(console.log('Not gonna wait for the timer'), 1000); // runs immediately ignoring the 1 second delay
setTimeout(() => console.log('Will wait for timer'), 1000); // only returns the code once the timer is up
```

### Problem with Single Threading

* Think of querying data for matching words in the database
* Waiting for the interpreter to go through line by line to match the word is very time consuming
* Multitasking is much faster

```javascript
// Same concept different result:
console.log('I Happen First');
setTimeout(function () {
  console.log('Hi there!');
}, 2000);
console.log('I Happen Second');

// Result will be:

// 1. I Happen First
// 2. I Happen Second
// 3. Hi there!
// * Reason for this is because the browser took over from Javascript and all of them are written in C++
// * C++ wroks differently than the Single Threaded JavaScript
```

### Key Concept to understand on how JavaScript interacts with the Browser

* Javascript is not the one keeping tracks on things, the BROWSER is.
* Typically the Browser is written in C++.

### Here's how it goes

1. Browsers come with web APIs that are able to handle certain tasks in the background\(like making requests or setTimeout\(\)\)
2. Javascript call stack recognises these Web API functions and passes them off to the browser to take care off
3. Once the browser finishes those tasks, they return and are pushed onto the call-stack as a callback

#### Unlike C and other compiled languages, Javascript runs in a container - a program that reads your js codes and runs them. This program must do two things:

1. Parse your code and convert it to runnable commands
2. provide some objects to javascript so that it can interact with the outside world.

   The first part is called Engine and the second is Runtime.

For example, the Chrome Browser and node.js use the same Engine - V8, but their Runtimes are different: in Chrome you have the window, DOM objects etc, while node gives you require, Buffers and processes.

> Unlike C and other compiled languages, Javascript runs in a container - a program that reads your js codes and runs them. This program must do two things
>
> * Parse your code and convert it to runnable commands
> * Provide some objects to javascript so that it can interact with the outside world.
>
> The **first** part is called **Engine** and the **second** is **Runtime**.
>
> For example, the Chrome Browser and node.js use the same Engine - V8, but their Runtimes are different: in Chrome you have the window, DOM objects etc, while node gives you require, Buffers and processes.

[The link that explains it](https://stackoverflow.com/questions/29027845/what-is-the-difference-between-javascript-engine-and-javascript-runtime-environm)

[This website is really good at SHOWING us on what is happening/what does this all mean](http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)

