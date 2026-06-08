Here are the concepts explained in **simple language with easy examples**.


-----------

These are very common JavaScript interview topics. For a 10-year PHP developer, understanding them conceptually is more important than memorizing syntax.

---

Why do we use async/await?

Async/await is used to handle asynchronous operations such as API calls, file uploads, and database requests in a cleaner and more readable way. It is built on top of Promises and helps avoid complex .then() chains while making asynchronous code look like synchronous code.


fetch() returns a Promise
await waits for the Promise
async allows us to use await

What is Polling?

Polling is a technique where the client repeatedly sends requests to the server at fixed intervals to check whether new data or a status update is available.


# 1. Promise

A **Promise** represents a value that will be available **now, later, or never**.

Think of ordering food online:

* Order placed → Pending
* Food delivered → Resolved
* Restaurant cancels → Rejected

### Example

```javascript
const myPromise = new Promise((resolve, reject) => {

    let success = true;

    if(success){
        resolve("Payment Successful");
    }else{
        reject("Payment Failed");
    }

});

myPromise
.then(result => console.log(result))
.catch(error => console.log(error));
```

### Output

```text
Payment Successful
```

### States

```text
Pending
Resolved (Success)
Rejected (Failed)
```

---

# 2. Async

`async` makes a function return a Promise automatically.

### Example

```javascript
async function greet() {
    return "Hello";
}

greet().then(data => console.log(data));
```

### Output

```text
Hello
```

### Simple Definition

```text
async = This function can handle asynchronous work.
```

---

# 3. Await

`await` waits for a Promise to finish.

It can only be used inside an `async` function.

### Example

```javascript
function getData() {

    return new Promise(resolve => {

        setTimeout(() => {
            resolve("User Data");
        }, 2000);

    });

}

async function showData() {

    let result = await getData();

    console.log(result);

}

showData();
```

### Output (after 2 seconds)

```text
User Data
```

### Simple Definition

```text
await = Wait here until Promise finishes.
```

---

# 4. Promise vs Async/Await

### Promise Style

```javascript
fetch('/api/user')
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.log(error));
```

### Async/Await Style

```javascript
async function getUser() {

    try {

        const response = await fetch('/api/user');

        const data = await response.json();

        console.log(data);

    } catch(error) {

        console.log(error);

    }

}
```

### Interview Answer

```text
Async/Await is just a cleaner way to write Promise-based code.
```

---

# 5. Fetch API

Used to call APIs and get data from a server.

### Example

```javascript
fetch('/api/user')
.then(response => response.json())
.then(data => console.log(data));
```

### Example Response

```json
{
    "name":"Chandan",
    "age":30
}
```

### Output

```text
Chandan
```

### Simple Definition

```text
Fetch is a modern way to make HTTP requests.
```

---

# Fetch Using Async/Await

```javascript
async function getUser() {

    const response = await fetch('/api/user');

    const data = await response.json();

    console.log(data);

}

getUser();
```

---

# 6. map()

`map()` creates a **new array** by modifying each item.

### Example

```javascript
let prices = [100, 200, 300];

let discounted = prices.map(price => price - 10);

console.log(discounted);
```

### Output

```text
[90, 190, 290]
```

### Original Array

```javascript
[100,200,300]
```

### New Array

```javascript
[90,190,290]
```

### Simple Definition

```text
map() = Take every item, modify it, return a new array.
```

---

# Real Interview Example

### API Response

```javascript
const users = [
    {name:'John'},
    {name:'Mike'},
    {name:'David'}
];
```

### Extract Names

```javascript
const names = users.map(user => user.name);

console.log(names);
```

### Output

```text
["John","Mike","David"]
```

---

# map() vs forEach()

### map()

Returns new array.

```javascript
let result = [1,2,3].map(x => x * 2);
```

Output

```javascript
[2,4,6]
```

---

### forEach()

Returns nothing.

```javascript
[1,2,3].forEach(x => {
    console.log(x);
});
```

Output

```text
1
2
3
```

---

# Real-World Example (PHP Developer)

### Before AJAX

```text
Submit Form
Page Refresh
Server Response
```

---

### AJAX / Fetch

```text
Submit Form
No Refresh
Background Request
Update Page
```

---

### Example Login Flow

```javascript
async function login() {

    const response = await fetch('/login.php', {
        method: 'POST'
    });

    const result = await response.json();

    console.log(result);

}
```

### What Happens?

```text
1. fetch() sends request
2. Server processes login
3. Promise returned
4. await waits
5. Result received
6. UI updated
```

---

# One-Line Interview Definitions

### Promise

```text
An object representing a future result of an asynchronous operation.
```

### Async

```text
Marks a function as asynchronous and automatically returns a Promise.
```

### Await

```text
Pauses execution until a Promise is resolved or rejected.
```

### Fetch

```text
A modern JavaScript API used to make HTTP requests.
```

### map()

```text
Creates a new array by transforming each element of an existing array.
```

### Common Interview Chain

```text
fetch() → returns Promise
async → allows await usage
await → waits for Promise
map() → transforms API data
```

A practical example:

```javascript
async function loadUsers() {

    const response = await fetch('/users.php');

    const users = await response.json();

    const names = users.map(user => user.name);

    console.log(names);

}
```

This single example demonstrates **fetch + Promise + async + await + map**, which interviewers often ask together.


Polling means:

The client (browser) repeatedly asks the server for updates at regular intervals.


-----------

# 1. IIFE (Immediately Invoked Function Expression)

A function that runs immediately after it is created.

### Example

```javascript
(function() {
    console.log("Hello");
})();
```

### Output

```
Hello
```

### Use Case

* Avoid creating global variables.
* Execute code only once during page load.

---

# 2. Arrow Function (`=>`)

Shorter way to write functions.

### Example

```javascript
const greet = () => {
    console.log("Hello");
};

greet();
```

### Output

```
Hello
```

### Use Case

* Cleaner and shorter code.
* Commonly used in callbacks.

---

# 3. Template Literals

Used to insert variables inside strings.

### Example

```javascript
let name = "Chandan";

console.log(`Hello ${name}`);
```

### Output

```
Hello Chandan
```

### Use Case

* Dynamic messages.
* Building HTML.

---

# 4. Destructuring

Extract values from objects or arrays easily.

### Example

```javascript
const user = {
    name: "Chandan",
    age: 30
};

const { name, age } = user;

console.log(name);
```

### Output

```
Chandan
```

### Use Case

* Cleaner code.
* Access object values quickly.

---

# 5. Optional Chaining (`?.`)

Prevents errors if a property doesn't exist.

### Example

```javascript
const user = {};

console.log(user.address?.city);
```

### Output

```
undefined
```

Without `?.`, JavaScript throws an error.

### Use Case

* API response handling.
* Nested objects.

---

# 6. Ternary Operator (`? :`)

Short form of if-else.

### Example

```javascript
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

### Output

```
Adult
```

### Use Case

* Quick conditions.

---

# 7. map()

Creates a new array by modifying each element.

### Example

```javascript
let nums = [1,2,3];

let doubled = nums.map(num => num * 2);

console.log(doubled);
```

### Output

```
[2,4,6]
```

### Use Case

* Transform data.

---

# 8. forEach()

Loops through an array.

### Example

```javascript
let nums = [1,2,3];

nums.forEach(num => {
    console.log(num);
});
```

### Output

```
1
2
3
```

### Use Case

* Display data.
* Loop through arrays.

### Difference

```javascript
map()      => Returns new array
forEach()  => Returns nothing
```

---

# 9. Event Delegation

Handle events for dynamic elements.

### Example

```javascript
$(document).on("click", ".btn", function() {
    alert("Clicked");
});
```

### Use Case

If buttons are added later using AJAX, click still works.

Very common interview question.

---

# 10. DOM Manipulation

Changing webpage content dynamically.

### Example

```javascript
$("#title").text("New Title");
```

### Before

```html
<h1 id="title">Old Title</h1>
```

### After

```html
<h1 id="title">New Title</h1>
```

### Use Case

* Update UI without page refresh.

---

# 11. Async/Await

Handle asynchronous operations cleanly.

### Example

```javascript
async function getData() {
    let response = await fetch('/api/user');
    let data = await response.json();

    console.log(data);
}
```

### Use Case

* API calls.
* AJAX requests.

---

# 12. Fetch API

Modern way to call APIs.

### Example

```javascript
fetch('/api/user')
    .then(response => response.json())
    .then(data => console.log(data));
```

### Use Case

* Get data from server.

---

# 13. AJAX

Send request without page refresh.

### Example

```javascript
$.ajax({
    url: "user.php",
    type: "POST",
    data: {id:1},
    success: function(response){
        console.log(response);
    }
});
```

### Use Case

* Login
* Registration
* Checkout forms

---

# 14. FormData

Send files/images through AJAX.

### Example

```javascript
let formData = new FormData();

formData.append("image", file);
```

### AJAX Upload

```javascript
$.ajax({
    url: "upload.php",
    type: "POST",
    data: formData,
    processData: false,
    contentType: false
});
```

### Use Case

* Image upload
* File upload

---

# 15. LocalStorage

Store data in browser permanently.

### Save

```javascript
localStorage.setItem("name", "Chandan");
```

### Read

```javascript
let name = localStorage.getItem("name");
```

### Use Case

* Save user preferences.
* Cart data.

---

# 16. Cookies

Store small data in browser.

### Create

```javascript
document.cookie = "username=Chandan";
```

### Use Case

* Login session.
* User tracking.

---

# 17. setInterval()

Runs repeatedly after a fixed time.

### Example

```javascript
setInterval(() => {
    console.log("Running");
}, 1000);
```

### Output

Every second:

```
Running
```

### Use Case

* Live updates.
* Countdown timer.

---

# 18. Polling

Repeatedly checking server status.

### Example

```javascript
setInterval(() => {

    $.get("status.php", function(data){
        console.log(data);
    });

}, 5000);
```

### Use Case

* Order status.
* AI image generation status.
* Payment status.

---

# 19. Dynamic HTML Creation

Create HTML using JavaScript.

### Example

```javascript
let html = `
<div>
   <h2>Product</h2>
</div>
`;

$("#container").append(html);
```

### Use Case

* Product listing.
* API response rendering.

---

# 20. jQuery Selectors

Select HTML elements.

### Examples

```javascript
$("#id")
```

Select by ID

```javascript
$(".class")
```

Select by class

```javascript
$("p")
```

Select all paragraphs

---

# 21. closest()

Find nearest parent element.

### HTML

```html
<div class="card">
    <button class="btn">Buy</button>
</div>
```

### jQuery

```javascript
$(".btn").click(function() {

    let card = $(this).closest(".card");

    console.log(card);

});
```

### Use Case

Very common in checkout and cart pages.

Get the parent product card of clicked button.

---

# 22. Data Attributes

Store custom data in HTML.

### HTML

```html
<button
    data-id="101"
    data-price="999">
    Buy
</button>
```

### jQuery

```javascript
let id = $(this).data("id");
let price = $(this).data("price");
```

### Use Case

* Product ID
* Variant ID
* Price

---

# 23. JSON (JavaScript Object Notation)

Data format used between frontend and backend.

### Example

```javascript
{
   "name":"Chandan",
   "age":30
}
```

### Convert Object to JSON

```javascript
JSON.stringify(user);
```

### Convert JSON to Object

```javascript
JSON.parse(jsonData);
```

### Use Case

* API response.
* AJAX communication.

---

For a **10-year PHP/jQuery developer**, interviewers usually don't ask only syntax. They focus on **real-world usage, performance, debugging, and architecture**.

# 1. What is the difference between `$(document).ready()` and `window.onload`?

### Answer

`$(document).ready()`

* Executes when HTML DOM is loaded.
* Doesn't wait for images.

```javascript
$(document).ready(function () {
    console.log("DOM Ready");
});
```

`window.onload`

* Waits for complete page loading.
* Includes images, CSS, videos.

```javascript
window.onload = function () {
    console.log("Page Loaded");
};
```

---

# 2. What is Event Delegation?

### Answer

Instead of attaching events to every element, attach to parent.

```javascript
$(document).on("click", ".btn", function () {
    alert("Clicked");
});
```

### Why?

Works for dynamically added elements.

---

# 3. Difference between `.prop()` and `.attr()`?

### Answer

`.attr()`
Gets original HTML attribute.

```html
<input type="checkbox" checked>
```

```javascript
$('input').attr('checked');
```

Returns:

```text
checked
```

`.prop()`
Gets current state.

```javascript
$('input').prop('checked');
```

Returns:

```text
true
```

### Use

```javascript
$('#checkbox').prop('checked', true);
```

---

# 4. Difference between `.html()`, `.text()`, and `.val()`?

### Answer

```javascript
$('#msg').html('<b>Hello</b>');
```

Output:

```html
Hello (bold)
```

---

```javascript
$('#msg').text('<b>Hello</b>');
```

Output:

```text
<b>Hello</b>
```

---

```javascript
$('#name').val();
```

Gets input value.

---

# 5. Difference between `append()` and `prepend()`?

### append()

Adds at end.

```javascript
$('#list').append('<li>New</li>');
```

### prepend()

Adds at beginning.

```javascript
$('#list').prepend('<li>New</li>');
```

---

# 6. What is Chaining?

### Answer

Multiple methods in one statement.

```javascript
$('#box')
.addClass('active')
.show()
.css('color', 'red');
```

### Benefit

Cleaner code.

---

# 7. Difference between `find()` and `closest()`?

### HTML

```html
<div class="card">
    <button class="btn">Buy</button>
</div>
```

### find()

Search child elements.

```javascript
$('.card').find('.btn');
```

### closest()

Search parent elements.

```javascript
$('.btn').closest('.card');
```

---

# 8. What is `this` in jQuery?

### Answer

Current element that triggered event.

```javascript
$('.btn').click(function () {

    $(this).hide();

});
```

Only clicked button hides.

---

# 9. Difference between `hide()` and `remove()`?

### hide()

```javascript
$('#box').hide();
```

Element exists but hidden.

---

### remove()

```javascript
$('#box').remove();
```

Element completely deleted.

---

# 10. What is AJAX?

### Answer

Asynchronous JavaScript And XML.

Allows server communication without page refresh.

```javascript
$.ajax({
    url: 'save.php',
    type: 'POST',
    success: function(response){
        console.log(response);
    }
});
```

---

# 11. Difference between GET and POST in AJAX?

### GET

```javascript
$.get('user.php?id=1');
```

* Data in URL
* Limited length
* Less secure

---

### POST

```javascript
$.post('user.php',{id:1});
```

* Data in request body
* Better for forms

---

# 12. How to send files using AJAX?

### Answer

Use FormData.

```javascript
let fd = new FormData();

fd.append('image', file);
```

```javascript
$.ajax({
    url:'upload.php',
    type:'POST',
    data:fd,
    processData:false,
    contentType:false
});
```

---

# 13. Why use `processData:false`?

### Answer

Prevents jQuery from converting FormData into query string.

Required for file uploads.

---

# 14. Why use `contentType:false`?

### Answer

Allows browser to set multipart/form-data automatically.

---

# 15. Difference between `empty()` and `remove()`?

### empty()

```javascript
$('#box').empty();
```

Removes child content.

---

### remove()

```javascript
$('#box').remove();
```

Removes entire element.

---

# 16. How to prevent form submission?

```javascript
$('#form').submit(function(e){

    e.preventDefault();

});
```

### Use

AJAX form submission.

---

# 17. What is Debouncing?

### Answer

Delay execution until user stops typing.

```javascript
let timer;

$('#search').keyup(function(){

    clearTimeout(timer);

    timer = setTimeout(function(){

        console.log('API Call');

    },500);

});
```

### Use

Search autocomplete.

---

# 18. What is Throttling?

### Answer

Limit execution frequency.

Example:

* Scroll event
* Resize event

Run once every second.

---

# 19. What are Data Attributes?

### HTML

```html
<button
data-id="10"
data-price="999">
Buy
</button>
```

### jQuery

```javascript
let id = $(this).data('id');
```

---

# 20. How do you store data in browser?

### LocalStorage

```javascript
localStorage.setItem('name','John');
```

Persists after browser close.

---

### SessionStorage

```javascript
sessionStorage.setItem('name','John');
```

Removed when tab closes.

---

# 21. Difference between LocalStorage and SessionStorage?

| LocalStorage             | SessionStorage       |
| ------------------------ | -------------------- |
| Permanent                | Tab-based            |
| Survives browser restart | Deleted on tab close |

---

# 22. How do you check if an element exists?

```javascript
if($('.box').length){
    console.log('Found');
}
```

---

# 23. How to disable a button?

```javascript
$('#btn').prop('disabled', true);
```

Enable:

```javascript
$('#btn').prop('disabled', false);
```

---

# 24. What is Polling?

### Answer

Repeatedly checking server.

```javascript
setInterval(function(){

    $.get('status.php');

},5000);
```

### Use

* Payment status
* Order status
* AI image generation

---

# 25. What jQuery performance issues have you faced?

### Good Answer

* Too many DOM queries.
* Multiple AJAX calls.
* Unnecessary event bindings.
* Large HTML rendering.

### Optimization

```javascript
let button = $('#btn');
```

Instead of

```javascript
$('#btn').hide();
$('#btn').show();
$('#btn').text('Save');
```

Use cached selector.

---
