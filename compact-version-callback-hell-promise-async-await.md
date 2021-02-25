---
description: >-
  A compact version of these topics. Uncomment segment of your choosing to see
  what they do
---

# Compact version - Callback Hell/Promise/Async Await

```javascript
// let greeting = (name) => console.log(`Hello ${name}!`);

// const userInfo = (firstName, lastName, callback) => {
//   const fullName = `${firstName} ${lastName}`;
//   callback(fullName);
// };

// userInfo('John', 'Doe', greeting);
// ==================================================================

// Example of a callback hell
// doSomething(function (result) {
//   doSomethingElse(
//     result,
//     function (newResult) {
//       doThirdThing(
//         (newResult,
//         function (finalResult) {
//           console.log(`Got the final result ${finalResult}`);
//         },
//         failureCallback)
//       );
//     },
//     failureCallback
//   );
// }, failureCallback);
// ==================================================================

// Example of a Promise
// const hasMeeting = false;
// const meeting = new Promise((resolve, reject) => {
//   if (!hasMeeting) {
//     const meetingDetails = {
//       name: 'Marketing Meeting',
//       location: 'Skype',
//       time: '1:00 PM',
//     };
//     resolve(meetingDetails);
//   } else {
//     reject(new Error('Meeting already scheduled'));
//   }
// });

// Promise Chaining
// const addToCalendar = (meetingDetails) => {
//   return new Promise((resolve, reject) => {
// const calendar = `${meetingDetails.name} is scheduled at ${meetingDetails.time} on ${meetingDetails.location}`;
//     resolve(calendar);
//   });
// };

// If we're only going to resolve, we can shorten our code with Promise.resolve
// const addToCalendar = (meetingDetails) => {
//   const calendar = `${meetingDetails.name} is scheduled at ${meetingDetails.time} on ${meetingDetails.location}`;
//   return Promise.resolve(calendar);
// };

// meeting
//   .then(addToCalendar)
//   .then((res) => {
//     console.log('Meeting Scheduled');
//     console.log(res);
//   })
//   .catch((err) => console.log(err.message));
// ==================================================================

// Example of Promise.all - Return ALL Promises at once
// const promise1 = Promise.resolve('Promise 1 complete');
// const promise2 = new Promise((res, rej) => {
//   setTimeout(() => {
//     res('Promise 2 complete');
//   }, 2000);
// });

// promise1.then((res) => console.log(res));
// promise2.then((res) => console.log(res));
// Promise.all([promise1, promise2]).then((res) => console.log(res));
// ==================================================================

// Promise.raise - ONLY returns the FIRST Promise and DISREGARDS the rest
// Promise.race([promise1, promise2]).then((res) => console.log(res));

// Generator Function - a function that pauses but is not in the event loop. Denoted by the use of *
// function* generatorFunc() {
//   let data = getData();
//   yield data; // This line lets the function pause until getData() comes back
//   console.log(data); // This line only runs after yield above is uplifted
// }
// ==================================================================

// Example of async await

// const hasMeeting = true;
// const meeting = new Promise((resolve, reject) => {
//   if (!hasMeeting) {
//     const meetingDetails = {
//       name: 'Marketing Meeting',
//       location: 'Skype',
//       time: '1:00 PM',
//     };
//     resolve(meetingDetails);
//   } else {
//     reject(new Error('Meeting already scheduled'));
//   }
// });

// const addToCalendar = (meetingDetails) => {
//   const calendar = `${meetingDetails.name} is scheduled at ${meetingDetails.time} on ${meetingDetails.location}`;
//   return Promise.resolve(calendar);
// };

// async function myMeeting() {
//   const meetingDetails = await meeting; // The await keyword pauses the function until meeting comes back.
//   const message = await addToCalendar(meetingDetails); // This constant needs the one above to complete first before running.
//   console.log(message);
// }

// // For error handling, use try & catch blocks
// async function myMeeting() {
//   try {
//     const meetingDetails = await meeting;
//     const message = await addToCalendar(meetingDetails);
//     console.log(message);
//   } catch (err) {
//     console.log(err.message);
//   }
// }
// myMeeting();


```

