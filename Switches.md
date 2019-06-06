**Switches**
**Switch is preferred compared to if/else statement when we have a lot of different cases**

```javascript
const color = "green";

switch (color) {
  case "red":
    console.log("Color is red");
    break;
  case "green":
    console.log("Color is green");
    break;
  case "blue":
    console.log("Color is blue");
    break;
  default:
    console.log("Color is neither red, green or blue");
};

// ================================================================================

switch(new Date.().getDay()) {
  // getDay() method will return the day of the week in number form starting with 0 for Sunday.
  let day;

  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
    break;
}

console.log(`Today is ${day}`);
```
