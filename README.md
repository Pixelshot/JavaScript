# Await



## 183 - The Await Keyword

* We can **only use** the `await` keyword **inside** of functions declared with `async`
* With a normal Promise function we use .then\(\) to extract the response: `.then((response))`
* With **async await** we can replace `.then()` with `await` and store the value into a variable

```javascript
const res = await axios.get('https://pokeapi.co/api/v2/pokemon/ditto/');
console.log(res); // returns the same value as we get from .then((response))
```

* `await` will **pause** the execution of the function, waiting for a **promise** to be **resolved**
* If we combine `async` & `await` then there is **no need** to use `.then()` because `await` will make JavaScript wait at the code line. It will **not move on** until the **promise** is **resolved**

```javascript
async function getURL() {
  const data = await axios.get('https://pokeapi.co/api/v2/pokemon/ditto/');
  console.log('data:', data);
  return data;
}

getURL();
```

## 184 - Error Handling in Async Functions

* For error handling we could use `.catch()` on the function but there's a better way of doing it
* `try{}` & `catch{}` block

```javascript
const getURL = async () => {
  try {
    const response = await axios.get(
      'https://pokeapi.co/api/v2/pokemon/ditto/'
    );
    console.log(response);
  } catch (error) {
    console.log('Something went wrong.', error);
  }
};

getURL();
```

