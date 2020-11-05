# Promise Chaining



### We can only extract ONE THING per request

* One `.then()` = 1 round of request
* To go into a nested data have to make another round of `.then()`
* Same concept goes for `.catch()`
* Each `.then()` will run only if the **PREVIOUS** one is **resolved**

```javascript
const fakeRequest = (url) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const pages = {
        '/users': [
          { id: 1, username: 'Bilbo' },
          { id: 5, username: 'Esmeralda' },
        ],
        '/users/1': {
          id: 1,
          username: 'Bilbo',
          upvotes: 360,
          city: 'Lisbon',
          topPostId: 454321,
        },
        '/users/5': {
          id: 5,
          username: 'Esmeralda',
          upvotes: 571,
          city: 'Honolulu',
        },
        '/posts/45321': {
          id: 45321,
          title: 'Ladies & Gentlemen, may I introduce my pet pig, Hamlet',
        },
        '/about': 'This is the about page',
      };
})
```

### Resolve and Reject is basically the PERMISSION area FROM PROMISE maker to the CONSUMER

#### PERMISSION AREA

```javascript
// Create a variable to check if the URL argument matches any of the ones in pages
const data = pages[url];
// if it is, then resolve else reject
// ! Remember we need to execute resolve & reject. Not just reference them

if (data) {
  resolve({ status: 200, data });
} else {
  reject({ status: 404 });
}
```

#### CONSUMING AREA

```javascript
fakeRequest('/users').then((res) => {
  const id = res.pages[0].id;
  return fakeRequest(`/users/${id}`)
    .then((res) => {
      const postId = res.data.topPostId;
      return fakeRequest(`/posts/${postId}`)
        .then((res) => {
          console.log(res);
        })
        .catch((err) => {
          console.log(`error: ${err}`);
        })
        .catch((err) => {
          console.log(`error: ${err}`);
        });
    })
    .catch((err) => {
      console.log(`error: ${err}`);
    });
});
```

### But there is a work around to it

* We can **keep chaining** `.then()` at the **same level** as long as **current** `.then()` returns a **promise**
* With this method we only need to use `.catch()` **once** since they are all at the **same level**

#### Chaining Method

```javascript
fakeRequest('/users')
  .then((response) => {
    const id = response.data[0].id;
    return fakeRequest(`/users/${id}`);
  })
  .then((response) => {
    const topPostId = response.data.topPostId;
    return fakeRequest(`/posts/${topPostId}`);
  })
  .then((response) => {
    console.log(response.data.title);
  })
  .catch((error) => {
    console.log(`Error: ${error}`);
  });
```

