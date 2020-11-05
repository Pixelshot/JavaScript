# Form

## 160 - Form Events & PreventDefault\(\)

* A form is made to take data that we get from an _input_ and submit/send it somewhere.
* Usually to a **URL** - Eg: `/signup`
* `/signup` would be an endpoint on our own **server**.
* Once received, **server side** would do something like create a **new user** in the **database** and then respond with a new page that would load to the client as a **user**.
* But with the rise of **single page apps** and libraries like **React**, **Vue**, **Angular** or even **vanilla js**, forms are being worked in a _different_ way.
* Nowadays we would actually **stop** the **data** from **being sent back** to the **server**. **Intercepting** them before being sent. Reason for this is because we can **capture the event** so we can **trigger some javascript** code. Be it to display the information back to the user, or send it back to the server but we won't refresh the page. Everything will be done on the **same page**
* To prevent the default behaviour, we use `preventDefault()`.

```javascript
form.addEventListener('submit', function(e) {
  e.preventDefault();
});
```

## 161 - Input and Change Events

```javascript
const form = document.querySelector('form');

const creditCardInput = document.getElementById('credit-card');
const termsCheckbox = document.getElementById('terms');
const veggieSelect = document.getElementById('veggie');

form.addEventListener('input', e => {
  console.dir(this);
  console.dir(e);
});
```

* Normal Function: _this_ returns an object with available **key:value** pair for **form**
* ES6 Arrow Function: _this_ returns **Window** object with available **key:value** pair
* **e** returns an object with available **key:value** pair for the event parameter inside of the callback function of `addEventListener()`\[Refer to Events note if confused\]

#### In order to listen to multiple events:

1. We create an **OBJECT** to store our data as **key value** pair.
2. Attach them with **event type: input**.
3. We can also use **event type: change** but know that change works **differently**.
4. 'change' event: value is only stored once you press _Enter_ or focus _away_ from that particular _input_.

#### DYNAMIC APPROACH

```javascript
// 1. Assign a name for each input we want to track in HTML
// 2. Loop through the inputs
for (let input of [creditCardInput, termsCheckbox, veggieSelect]) {
  // Since target is the only key we're interested from event, we can use destructure to shorten it.
  // Instead of (e) => console.log(e.target) it's ({ target }) => console.log(target);
  input.addEventListener('input', ({ target }) => {
    // console.log('target:', target);
    // Once again we can use destructure to unpack/extract data from target
    const { name, type, value, checked } = target;

    type === 'checkbox' ? (formData[name] = checked) : (formData[name] = value);
  });
}
```

#### 'HARDCODING' APPROACH

```javascript
const formData = {};

creditCardInput.addEventListener('input', (e) => {
  console.log(e.target.value);
  // this will log every key we type into the input element
  // then save them in our newly created object
  // Refresher on how to add new key value pair to an object:
  // Object['key name(can be anything we want)'] = value
  formData['cc'] = e.target.value
})

termsCheckbox.addEventListener('input', e => {
  // For checkbox, instead of value, we use checked
  // checked returns a boolean value(true or false)
  console.log('Checkbox', e.target.checked);
  formData['agreeToTerms'] = e.target.checked;
});


veggieSelect.addEventListener('input', (e) => {
  console.log(e.target.value);
  // this will log every key we type into the input element
  // then save them in our newly created object
  // Refresher on how to add new key value pair to an object:
  // Object['key name(can be anything we want)'] = value
  formData['veggie'] = e.target.value
})



// To test if it works we can call our object in the console
// Say we log 1234 as our credit card input, ticked checkbox and chosen carrot as our preffered vegetable.
> formData
{cc: "1234", agreeToTerms: true, veggie: "carrot" }
```

