# Call Stack

* **The Call Stack** - JS way of knowing **what** are the function, **where** they are and **which** one is currently running.
* Call stack is like the **bookmark** of a book
* Call = function calls
* Stack = data structure: stack
* A stack is like books piled on a desk: The **last** book you place at the **top** is the **first** one to be **removed** from the stack.

### How it works

1. When a script has some number of function calls: the first function call JavaScript interpreter reaches will be **added** to the call stack.
2. That function will be carried out. And if there are any other function calls within that function, **they**

   will be added to the **top** of the call stack.

3. This continues until one of the function **returns** a **value** at which point its **removed** from the stack

   For recap, either ho through lecture again or hit Colt's other video on [call stack](https://www.youtube.com/watch?v=W8AeMrVtFLY)

### ! Remember the book-stacking concept where:

* Books are piled up according to the reader.
* Everytime the reader wants to take a book out he/she will start from the top. Taking a book from anywhere else can cause a book avalance.

### When it comes to programming:

* JS interpreter will go through the functions and create a priority stack.
* Once the function returns a value, it'll be taken out from the stack.

### Workflow:

1. Starts with the function we're calling: makeRant\(\)
2. Interpreter goes through line by line starting with const = document.createElement\('h1'\);
3. Interpreter creates the h1 element
4. Interpreter sees getRantText\(phrase\) being called. It goes up to the function
5. Find phrase which belongs to another function called scream
6. Interpreter goes up to scream and completes the return statement
7. scream is now removed from the call stack
8. Interpreter goes back to getRantText\(\) with value for phrase and insert it inside of scream\(phrase\)
9. Interpreter goes back to makeRant\(\) and completes h1.innerText = getRantText\(phrase\);
10. Goes on to the next line to append\(h1\)
11. Interpreter then moves on to the next line of code\(line 67 - after makeRant\(\) is called\) to find another function\(\) call to execute

```javascript
const repeat = (str, times) => {
  let result = '';
  for (let i = 0; i < times; i++) {
    result += str;
  }
  return result;
};

const scream = str => {
  return str.toUpperCase() + '!!!';
};

const getRantText = phrase => {
  let text = scream(phrase);
  let rant = repeat(text, 8);
  return rant;
};

const makeRant = (phrase, el) => {
  const h1 = document.createElement('h1');
  h1.innerText = getRantText(phrase);
  el.appendChild(h1);
};
console.log('HELLO!');

makeRant('I hate mayonnaise', document.body); // ? break point - Nothing else works beyond this point
```

