# Dates & Times

**Dates & Times**

```javascript
let val;

const today = new Date(); // returns current date and time

// 3 ways of expressing specific time
let birthday = new Date("9-10-1981 11:25:00"); // returns "Thu Sep 10 1981 11:25:00 GMT+ (Local Time)"
birthday = new Date("Sepember 10 1981"); // returns "Thu Sep 10 1981 00:00:00 GMT+ (Local Time)"
birthday = new Date("9/10/1981"); // returns "Thu Sep 10 1981 00:00:00 GMT+ (Local Time)"

val = today;
val = birthday;
val = birthday;
val = today.getMonth(); // returns the current month. It's 0 based therefore January is 0, February is 1 and so forth
val = today.getDate(); // returns the current date
val = today.getDay(); // returns numerical representation of the current day. Wednesday returns 4 as it's the fourth day of the week(week begins with Sunday)
val = today.getFullYear(); // returns the current year. Eg. "2019"
val = today.getHours(); // returns the current hour. Eg. 11:20 a.m returns "11"
val = today.getMinutes(); // returns the current minute. Eg. 11:20 a.m returns "20"
val = today.getSeconds(); // returns the current seconds. Eg. 11:20:32 a.m returns "32"
val = today.getMilliseconds(); // returns the current millisecond
val = today.getTime(); // returns the current timestamps

console.log(val);

// Setting up time

birthday.setMonth(2); // returns March
birthday.setDate(12); // returns March 12
birthday.setFullYear(1985); //returns March 12 1985
birthday.setHours(3); // returns March 12 1985 3:00:00
birthday.setMinutes(30); // returns March 12 1985 3:30:00
birthday.setMinutes(25); // returns March 12 1985 3:30:25

console.log(birthday);
```

