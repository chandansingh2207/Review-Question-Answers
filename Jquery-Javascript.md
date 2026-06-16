Jquery,javascript is Synchronous perform one task at a time.

Synchronous (Sync): Code executes one task at a time, in order. The next line waits until the current line finishes.


Asynchronous (Async): A task that takes time (like fetching data from a server) can start, and the program can continue doing other work instead of waiting for it to finish.

Hoisting → Hoisting means use a variable or function before it is defined in the code.


Microtask Queue → High-priority async tasks like Promises.

Macrotask Queue → Lower-priority tasks like setTimeout.

Closure → Function remembers outer variables.


Event Bubbling is the process where an event starts from the target element and then propagates upward through its parent elements.

Ex:
<div id="parent">
  <button id="child">Click Me</button>
</div>

document.getElementById("child").addEventListener("click", () => {
  console.log("Button clicked");
});

document.getElementById("parent").addEventListener("click", () => {
  console.log("Div clicked");
});

When you click the button, the output is:

Button clicked

Div clicked

Event Delegation → Parent handles child events.

AJAX → Load data without page refresh.

Promise → Future result of an async operation.

Event Loop → Handles async tasks.

Debounce → Run after user stops.

Throttle → Limit how often a function runs.


| Concept     | Simple Definition                      |
| ----------- | -------------------------------------- |
| Promise     | Future result of an async operation    |
| Async       | Makes a function return a Promise      |
| Await       | Waits for a Promise to complete        |
| Async/Await | Cleaner way to handle Promises         |
| Polling     | Repeatedly checks server for updates   |
| AJAX        | Load data without page refresh         |
| Fetch API   | Modern way to call APIs                |
| Callback    | Function passed to another function    |
| Event Loop  | Handles async tasks in JavaScript      |
| setTimeout  | Runs code once after a delay           |
| setInterval | Runs code repeatedly after an interval |


JavaScript & jQuery Interview One-Liner Answers
===============================================
JavaScript Basics

What is JavaScript?
JavaScript is a programming language used to make web pages interactive.

What is jQuery?
jQuery is a JavaScript library that simplifies DOM manipulation, events, and AJAX.

What is DOM?
DOM (Document Object Model) is the HTML structure that JavaScript can access and modify.

What is BOM?
BOM (Browser Object Model) provides browser-related objects like window, history, and navigator.

Common BOM Objects:

window
history
location
navigator
screen

Scope
==========

Global Scope
Variable accessible from anywhere in the program.

Function Scope
Variable accessible only inside a function.

Block Scope
Variable accessible only inside a block {}.

Functions
============

Function Declaration
A normal named function defined using the function keyword.

Function Expression
A function stored in a variable.

Arrow Function
Shorter syntax for writing functions.

Callback Function
A function passed as an argument to another function.

IIFE
A function that runs immediately after it is defined.

Core Concepts
================
Closure
A function remembers variables from its outer scope.

Hoisting
JavaScript moves declarations to the top before execution.

Execution Context
The environment where JavaScript code executes.

Call Stack
A stack that tracks function execution order.

Event Loop
Handles asynchronous tasks and moves them to execution when the stack is empty.

Single Threaded
JavaScript executes one task at a time.


Quick Interview Favorites
===========================
What is Closure?
Function remembers outer variables.

What is Hoisting?
Declarations move to the top before execution.

What is Promise?
Future result of an asynchronous operation.

What is Async/Await?
Cleaner syntax for handling Promises.

What is Event Loop?
Manages asynchronous task execution.

What is AJAX?
Loads data without page refresh.

What is Event Delegation?
Parent handles child events.

What is Debounce?
Execute after user stops triggering events.

What is Throttle?
Limit function execution frequency.

What is CORS?
Cross-domain request permission mechanism.

What is Prototype?
JavaScript's inheritance mechanism.

What is Polling?
Repeatedly asking server for updates.

What is Fetch API?
Modern API for HTTP requests.

What is localStorage?
Permanent browser storage.

What is sessionStorage?
Temporary browser storage for one session.

Callback
=========
Callback Hell in jQuery (or JavaScript in general) happens when you have many asynchronous operations nested inside one another, creating deeply indented and hard-to-read code.

Example of Callback Hell
$.get("/user", function(user) {
    $.get("/orders/" + user.id, function(orders) {
        $.get("/payment/" + orders[0].id, function(payment) {
            console.log(payment);
        });
    });
});

The code starts looking like a pyramid:

task1(function() {
    task2(function() {
        task3(function() {
            task4(function() {
                // ...
            });
        });
    });
});

| Keyword | Can Reassign? | Scope          | Hoisted?                               |
| ------- | ------------- | -------------- | -------------------------------------- |
| `var`   | ✅ Yes         | Function scope | Yes                                    |
| `let`   | ✅ Yes         | Block scope    | Yes (but can't use before declaration) |
| `const` | ❌ No          | Block scope    | Yes (but can't use before declaration) |


Frequently Asked 10-Year Experience Questions
==============================================
closure:
=========
A closure is a function that can remember and use variables from outside itself, even after that outer function is done.

Even simpler:

👉 It’s a function with memory.

Example idea:
function outer() {
  let x = 10;

  function inner() {
    console.log(x); // still remembers x
  }

  return inner;
}

Even after outer() finishes, inner() still remembers x = 10.

Lexical scope means:
====================
👉 A function can access variables based on where it is written in the code, not where it is called.

Simple Example
function outer() {
    let x = 10;

    function inner() {
        console.log(x); // can access x
    }

    inner();
}

outer();


Spread Operator (...) — Simple
=================================
The spread operator in JavaScript (...) is used to expand (spread out) elements of an array or object.
Spread operator = open the box and lay all chocolates out individually.

1. For Arrays

Copy an array

let arr1 = [1, 2, 3];
let arr2 = [...arr1];

console.log(arr2); // [1, 2, 3]

👉 It spreads all values from arr1 into arr2.

Copy an array
let arr1 = [1, 2, 3];
let arr2 = [...arr1];

console.log(arr2); // [1, 2, 3]

Combine arrays
let a = [1, 2];
let b = [3, 4];

let c = [...a, ...b];

console.log(c); // [1, 2, 3, 4]




1. Using fetch with async/await
================================
you can absolutely use async/await for API calls in JavaScript. In fact, it’s the most readable way.

async function getUsers() {
  try {
    const response = await fetch("https://api.example.com/users");
    const data = await response.json();

    console.log(data);
  } catch (error) {
    console.log("Error:", error);
  }
}

getUsers();


Destructuring in JavaScript (Simple)
====================================
👉 Taking values from an array or object and putting them into variables easily.

1. Array Destructuring
let arr = [10, 20, 30];

let [a, b, c] = arr;

console.log(a); // 10
console.log(b); // 20
console.log(c); // 30


2.Object Destructuring
let user = {
  name: "John",
  age: 25
};

let { name, age } = user;

console.log(name); // John
console.log(age);  // 25



Hoisting → JavaScript moves declarations to the top.

Promise → Object representing future success or failure.

Async/Await → Simplifies Promise handling.

Event Loop → Manages asynchronous operations.

Debounce → Delay execution until activity stops.

Throttle → Limit execution frequency.

Event Delegation → Parent handles events for child elements.

Callback Hell → Deeply nested callbacks that are hard to maintain.

Memory Leak → Memory that is allocated but never released.

Microtask Queue → High-priority async tasks like Promises.

Macrotask Queue → Lower-priority tasks like setTimeout.

Synchronous → Code executes line by line.

Asynchronous → Code executes without blocking other operations.

Single Threaded → One task executes at a time.

Concurrency → Multiple tasks progress without running simultaneously.

These short definitions are often enough for the first round of JavaScript/jQuery interviews.


IIFE → Function runs immediately after it is created.

Callback → Function passed to another function and executed later.

Async/Await → Write asynchronous code in a synchronous style.

Fetch API → Modern way to make HTTP requests.

Arrow Function → Shorter syntax for writing functions.

Template Literal → Create strings using backticks and ${}.

Destructuring → Extract values from objects or arrays easily.

Spread Operator (...) → Copy or merge arrays and objects.

Rest Parameter (...) → Collect multiple arguments into an array.

Optional Chaining (?.) → Safely access nested properties.

Ternary Operator → Short form of if-else.

map() → Create a new array by transforming items.

forEach() → Loop through array items.

filter() → Return matching items from an array.

find() → Return the first matching item.

reduce() → Convert an array into a single value.

setTimeout() → Run code after a delay.

setInterval() → Run code repeatedly at intervals.

Local Storage → Store data permanently in browser.

Session Storage → Store data until browser tab closes.

JSON → Standard format for data exchange.

parseInt() → Convert string to integer.

parseFloat() → Convert string to decimal number.

typeof → Check the data type of a variable.

NaN → Represents an invalid number.

Truthy/Falsy → Values treated as true or false in conditions.

Scope → Area where a variable is accessible.

Global Scope → Variable available everywhere.

Local Scope → Variable available only inside a function/block.

let → Block-scoped variable declaration.

const → Block-scoped variable whose reference cannot change.

var → Function-scoped variable declaration.

DOM → Representation of HTML as objects.

DOM Manipulation → Change HTML elements dynamically.

Event Listener → Waits for a user action.

preventDefault() → Stops default browser behavior.

stopPropagation() → Stops event bubbling.

Event Target → Element that triggered the event.

this Keyword → Refers to the current object/context.

Prototype → Mechanism for sharing methods between objects.

Class → Blueprint for creating objects.

Constructor → Special method called when an object is created.

Inheritance → One class acquires properties of another.

Encapsulation → Hide internal details and expose only needed functionality.

Polymorphism → Same method behaves differently in different classes.

Module → Reusable piece of code in a separate file.

Import → Bring code from another module.

Export → Make code available to other modules.

Memoization → Cache function results for faster execution.

Recursion → Function calling itself.

Shallow Copy → Copies only top-level properties.

Deep Copy → Copies all nested properties.

Currying → Convert a function with multiple arguments into nested functions.

Higher Order Function → Function that accepts or returns another function.

Pure Function → Same input always gives same output.

Garbage Collection → Automatic memory cleanup.

Polling → Repeatedly check server for updates.

WebSocket → Real-time two-way communication.

API → Interface for communication between applications.

CORS → Controls cross-domain requests.

Cookie → Small data stored in browser.

JWT Token → Secure token used for authentication.

Authentication → Verify user identity.

Authorization → Check user permissions.


🧠 JavaScript Basics
Scope → Where a variable can be accessed
Block Scope → Variables inside { } like let and const
Function Scope → Variables inside a function (like var)
Global Scope → Variables accessible everywhere


⚙️ Functions
Function Declaration → A named function that is hoisted
Function Expression → Function stored in a variable
Arrow Function → Short syntax for writing functions
Callback → Function passed into another function

🔄 Async Concepts
Synchronous → Code runs one after another
Asynchronous → Code runs without waiting
Microtask → High Priority task, Runs immediately after current code (Promise)
Macrotask → Low priority tasks, Runs later (setTimeout)

🧩 Data Handling
Primitive Type → Simple values like number, string, boolean
Reference Type → Objects and arrays stored by reference
Shallow Copy → Copies only first level of object
Deep Copy → Copies full object including nested data

🧠 Memory & Execution
Call Stack → Keeps track of function execution
Heap → Memory where objects are stored
Garbage Collection → Removes unused memory automatically

🔁 Arrays & Objects
Map → Creates new array by transforming values
Filter → Creates new array with matching values
Reduce → Converts array into a single value
ForEach → Loops through array (no return)

🌐 DOM & jQuery
DOM → Browser representation of HTML as objects
jQuery → Library to simplify JavaScript tasks
Selector → Method to find elements ($("#id"))
DOM Manipulation → Changing HTML using JavaScript/jQuery

🎯 Events
Event → Action like click, scroll, keypress
Event Listener → Function waiting for an event
Event Target → Element that triggered the event

🔐 JavaScript Concepts
this keyword → Refers to the current object
Strict Mode → Safer JavaScript mode ("use strict")
Type Coercion → Automatic type conversion
Falsy Values → false, 0, "", null, undefined, NaN


What is the difference between microtask and macrotask?.
==========================================================
One-line memory trick

Microtask = "run ASAP after current code".
Macrotask = "run later in the next event loop turn".


| Microtask                     | Macrotask                     |
| ----------------------------- | ----------------------------- |
| Higher priority               | Lower priority                |
| Runs right after current code | Runs in next event loop cycle |
| `Promise.then()`              | `setTimeout()`                |
| Executed first                | Executed after all microtasks |

JavaScript:
============
JavaScript is synchronous by default, but it supports asynchronous operations through the event loop, callbacks, Promises, and async/await. 

jQuery is a JavaScript library and can perform both synchronous operations (DOM manipulation) and asynchronous operations (AJAX).

Hoisting
===========
Hoisting means  use a variable or function before it is defined in the code.

Example with var:

console.log(name); // undefined

var name = "John";

But be careful: not all variables can be used before their declaration.

console.log(age); // ReferenceError

let age = 25;







Simple Difference Between Synchronous and Asynchronous
========================================================
🟢 Synchronous (Sync)

Tasks run one after another. The next task waits until the current task finishes.

🔵 Asynchronous (Async)

A task can start, and JavaScript can continue with other work without waiting for it to finish.

| Synchronous         | Asynchronous                                         |
| ------------------- | ---------------------------------------------------- |
| Waits for each task | Doesn't wait for long-running tasks                  |
| Blocking            | Non-blocking                                         |
| Executes in order   | Can continue other work                              |
| Simple code flow    | Better for network requests, timers, file operations |


🟢 Debouncing
=================
Run the function only after the user stops triggering the event for a certain time.

Example:
Search box:

User types: h
then he
then hel
then hell
then hello

Without debouncing → 5 API calls

With debouncing (500ms) → wait until the user stops typing, then make 1 API call

Memory trick:

Debounce = "Wait until things become quiet."

🔵 Throttling
================
Run the function at most once every X milliseconds.

Example:
User scrolls a page.

Without throttling:

Function may run hundreds of times per second.

With throttling (1 second):

Function runs only once every second while scrolling.

Memory trick:

Throttle = "Limit the speed."

| Debouncing                 | Throttling              |
| -------------------------- | ----------------------- |
| Waits until activity stops | Runs at fixed intervals |
| Good for search input      | Good for scroll/resize  |
| Reduces unnecessary calls  | Limits call frequency   |

🟢 Fastest Selector

ID selector (#id) is the fastest

Example:
$("#header")

Why fast?
ID is unique
Browser can directly find it (no searching needed)

🔵 Slower selectors
1. Class selector
$(".menu")

Slower than ID
Can match multiple elements


⚡ Speed order (fast → slow)
ID (#id)
  ↓
Class (.class)
  ↓
Tag (div, p)
  ↓
Nested/complex selectors

----------

Why do we use async/await?

Simple Definition
async → Makes a function asynchronous and returns a Promise.
await → Waits for a Promise to finish before moving to the next line.

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


### Output

text
Payment Successful


### States

text
Pending
Resolved (Success)
Rejected (Failed)


---

# 2. Async

`async` makes a function return a Promise automatically.

### Example


async function greet() {
    return "Hello";
}

greet().then(data => console.log(data));


### Output

text
Hello


### Simple Definition

text
async = This function can handle asynchronous work.


---

# 3. Await

`await` waits for a Promise to finish.

It can only be used inside an `async` function.

### Example


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


### Output (after 2 seconds)

text
User Data


### Simple Definition

text
await = Wait here until Promise finishes.


---

# 4. Promise vs Async/Await

### Promise Style
A Promise represents a value that may be available now, later, or never.

fetch('/api/user')
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.log(error));


### Async/Await Style
async/await is just a cleaner way to work with Promises.

async function getUser() {

    try {

        const response = await fetch('/api/user');

        const data = await response.json();

        console.log(data);

    } catch(error) {

        console.log(error);

    }

}


### Interview Answer

text
Async/Await is just a cleaner way to write Promise-based code.


---

# 5. Fetch API

Used to call APIs and get data from a server.

### Example


fetch('/api/user')
.then(response => response.json())
.then(data => console.log(data));


### Example Response

json
{
    "name":"Chandan",
    "age":30
}


### Output

text
Chandan


### Simple Definition

text
Fetch is a modern way to make HTTP requests.


---

# Fetch Using Async/Await


async function getUser() {

    const response = await fetch('/api/user');

    const data = await response.json();

    console.log(data);

}

getUser();


---

# 6. map()

`map()` creates a **new array** by modifying each item.

### Example


let prices = [100, 200, 300];

let discounted = prices.map(price => price - 10);

console.log(discounted);


### Output

text
[90, 190, 290]


### Original Array


[100,200,300]


### New Array


[90,190,290]


### Simple Definition

text
map() = Take every item, modify it, return a new array.


---

# Real Interview Example

### API Response


const users = [
    {name:'John'},
    {name:'Mike'},
    {name:'David'}
];


### Extract Names


const names = users.map(user => user.name);

console.log(names);


### Output

text
["John","Mike","David"]


---

# map() vs forEach()

### map()

Returns new array.


let result = [1,2,3].map(x => x * 2);


Output


[2,4,6]


---

### forEach()

Returns nothing.


[1,2,3].forEach(x => {
    console.log(x);
});


Output

text
1
2
3


---

# Real-World Example (PHP Developer)

### Before AJAX

text
Submit Form
Page Refresh
Server Response


---

### AJAX / Fetch

text
Submit Form
No Refresh
Background Request
Update Page


---

### Example Login Flow


async function login() {

    const response = await fetch('/login.php', {
        method: 'POST'
    });

    const result = await response.json();

    console.log(result);

}


### What Happens?

text
1. fetch() sends request
2. Server processes login
3. Promise returned
4. await waits
5. Result received
6. UI updated


---

# One-Line Interview Definitions

### Promise

text
An object representing a future result of an asynchronous operation.


### Async

text
Marks a function as asynchronous and automatically returns a Promise.


### Await

text
Pauses execution until a Promise is resolved or rejected.


### Fetch

text
A modern JavaScript API used to make HTTP requests.


### map()

text
Creates a new array by transforming each element of an existing array.


### Common Interview Chain

text
fetch() → returns Promise
async → allows await usage
await → waits for Promise
map() → transforms API data


A practical example:


async function loadUsers() {

    const response = await fetch('/users.php');

    const users = await response.json();

    const names = users.map(user => user.name);

    console.log(names);

}


This single example demonstrates **fetch + Promise + async + await + map**, which interviewers often ask together.


Polling means:

The client (browser) repeatedly asks the server for updates at regular intervals.


-----------

# 1. IIFE (Immediately Invoked Function Expression)

A function that runs immediately after it is created.

### Example


(function() {
    console.log("Hello");
})();


### Output


Hello


### Use Case

* Avoid creating global variables.
* Execute code only once during page load.

---

# 2. Arrow Function (`=>`)

Shorter way to write functions.

### Example


const greet = () => {
    console.log("Hello");
};

greet();


### Output


Hello


### Use Case

* Cleaner and shorter code.
* Commonly used in callbacks.

---

# 3. Template Literals

Used to insert variables inside strings.

### Example


let name = "Chandan";

console.log(`Hello ${name}`);


### Output


Hello Chandan


### Use Case

* Dynamic messages.
* Building HTML.

---

# 4. Destructuring

Extract values from objects or arrays easily.

### Example


const user = {
    name: "Chandan",
    age: 30
};

const { name, age } = user;

console.log(name);


### Output


Chandan


### Use Case

* Cleaner code.
* Access object values quickly.

---

# 5. Optional Chaining (`?.`)

Prevents errors if a property doesn't exist.

### Example


const user = {};

console.log(user.address?.city);


### Output


undefined


Without `?.`, JavaScript throws an error.

### Use Case

* API response handling.
* Nested objects.

---

# 6. Ternary Operator (`? :`)

Short form of if-else.

### Example


let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);


### Output


Adult


### Use Case

* Quick conditions.

---

# 7. map()

Creates a new array by modifying each element.

### Example


let nums = [1,2,3];

let doubled = nums.map(num => num * 2);

console.log(doubled);


### Output


[2,4,6]


### Use Case

* Transform data.

---

# 8. forEach()

Loops through an array.

### Example


let nums = [1,2,3];

nums.forEach(num => {
    console.log(num);
});


### Output


1
2
3


### Use Case

* Display data.
* Loop through arrays.

### Difference


map()      => Returns new array
forEach()  => Returns nothing


---

# 9. Event Delegation

Handle events for dynamic elements.

### Example


$(document).on("click", ".btn", function() {
    alert("Clicked");
});


### Use Case

If buttons are added later using AJAX, click still works.

Very common interview question.

---

# 10. DOM Manipulation

Changing webpage content dynamically.

### Example


$("#title").text("New Title");


### Before

html
<h1 id="title">Old Title</h1>


### After

html
<h1 id="title">New Title</h1>


### Use Case

* Update UI without page refresh.

---

# 11. Async/Await

Handle asynchronous operations cleanly.

### Example


async function getData() {
    let response = await fetch('/api/user');
    let data = await response.json();

    console.log(data);
}


### Use Case

* API calls.
* AJAX requests.

---

# 12. Fetch API

Modern way to call APIs.

### Example


fetch('/api/user')
    .then(response => response.json())
    .then(data => console.log(data));


### Use Case

* Get data from server.

---

# 13. AJAX

Send request without page refresh.

### Example


$.ajax({
    url: "user.php",
    type: "POST",
    data: {id:1},
    success: function(response){
        console.log(response);
    }
});


### Use Case

* Login
* Registration
* Checkout forms

---

# 14. FormData

Send files/images through AJAX.

### Example


let formData = new FormData();

formData.append("image", file);


### AJAX Upload


$.ajax({
    url: "upload.php",
    type: "POST",
    data: formData,
    processData: false,
    contentType: false
});


### Use Case

* Image upload
* File upload

---

# 15. LocalStorage

Store data in browser permanently.

### Save


localStorage.setItem("name", "Chandan");


### Read


let name = localStorage.getItem("name");


### Use Case

* Save user preferences.
* Cart data.

---

# 16. Cookies

Store small data in browser.

### Create


document.cookie = "username=Chandan";


### Use Case

* Login session.
* User tracking.

---

# 17. setInterval()

Runs repeatedly after a fixed time.

### Example


setInterval(() => {
    console.log("Running");
}, 1000);


### Output

Every second:


Running


### Use Case

* Live updates.
* Countdown timer.

---

# 18. Polling

Repeatedly checking server status.

### Example


setInterval(() => {

    $.get("status.php", function(data){
        console.log(data);
    });

}, 5000);


### Use Case

* Order status.
* AI image generation status.
* Payment status.

---

# 19. Dynamic HTML Creation

Create HTML using JavaScript.

### Example


let html = `
<div>
   <h2>Product</h2>
</div>
`;

$("#container").append(html);


### Use Case

* Product listing.
* API response rendering.

---

# 20. jQuery Selectors

Select HTML elements.

### Examples


$("#id")


Select by ID


$(".class")


Select by class


$("p")


Select all paragraphs

---

# 21. closest()

Find nearest parent element.

### HTML

html
<div class="card">
    <button class="btn">Buy</button>
</div>


### jQuery


$(".btn").click(function() {

    let card = $(this).closest(".card");

    console.log(card);

});


### Use Case

Very common in checkout and cart pages.

Get the parent product card of clicked button.

---

# 22. Data Attributes

Store custom data in HTML.

### HTML

html
<button
    data-id="101"
    data-price="999">
    Buy
</button>


### jQuery


let id = $(this).data("id");
let price = $(this).data("price");


### Use Case

* Product ID
* Variant ID
* Price

---

# 23. JSON (JavaScript Object Notation)

Data format used between frontend and backend.

### Example


{
   "name":"Chandan",
   "age":30
}


### Convert Object to JSON


JSON.stringify(user);


### Convert JSON to Object


JSON.parse(jsonData);


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


$(document).ready(function () {
    console.log("DOM Ready");
});


`window.onload`

* Waits for complete page loading.
* Includes images, CSS, videos.


window.onload = function () {
    console.log("Page Loaded");
};


---

# 2. What is Event Delegation?

### Answer

Instead of attaching events to every element, attach to parent.


$(document).on("click", ".btn", function () {
    alert("Clicked");
});


### Why?

Works for dynamically added elements.

---

# 3. Difference between `.prop()` and `.attr()`?

### Answer

`.attr()`
Gets original HTML attribute.

html
<input type="checkbox" checked>



$('input').attr('checked');


Returns:

text
checked


`.prop()`
Gets current state.


$('input').prop('checked');


Returns:

text
true


### Use


$('#checkbox').prop('checked', true);


---

# 4. Difference between `.html()`, `.text()`, and `.val()`?

### Answer


$('#msg').html('<b>Hello</b>');


Output:

html
Hello (bold)


---


$('#msg').text('<b>Hello</b>');


Output:

text
<b>Hello</b>


---


$('#name').val();


Gets input value.

---

# 5. Difference between `append()` and `prepend()`?

### append()

Adds at end.


$('#list').append('<li>New</li>');


### prepend()

Adds at beginning.


$('#list').prepend('<li>New</li>');


---

# 6. What is Chaining?

### Answer

Multiple methods in one statement.


$('#box')
.addClass('active')
.show()
.css('color', 'red');


### Benefit

Cleaner code.

---

# 7. Difference between `find()` and `closest()`?

### HTML

html
<div class="card">
    <button class="btn">Buy</button>
</div>


### find()

Search child elements.


$('.card').find('.btn');


### closest()

Search parent elements.


$('.btn').closest('.card');


---

# 8. What is `this` in jQuery?

### Answer

Current element that triggered event.


$('.btn').click(function () {

    $(this).hide();

});


Only clicked button hides.

---

# 9. Difference between `hide()` and `remove()`?

### hide()


$('#box').hide();


Element exists but hidden.

---

### remove()


$('#box').remove();


Element completely deleted.

---

# 10. What is AJAX?

### Answer

Asynchronous JavaScript And XML.

Allows server communication without page refresh.


$.ajax({
    url: 'save.php',
    type: 'POST',
    success: function(response){
        console.log(response);
    }
});


---

# 11. Difference between GET and POST in AJAX?

### GET


$.get('user.php?id=1');


* Data in URL
* Limited length
* Less secure

---

### POST


$.post('user.php',{id:1});


* Data in request body
* Better for forms

---

# 12. How to send files using AJAX?

### Answer

Use FormData.


let fd = new FormData();

fd.append('image', file);



$.ajax({
    url:'upload.php',
    type:'POST',
    data:fd,
    processData:false,
    contentType:false
});


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


$('#box').empty();


Removes child content.

---

### remove()


$('#box').remove();


Removes entire element.

---

# 16. How to prevent form submission?


$('#form').submit(function(e){

    e.preventDefault();

});


### Use

AJAX form submission.

---

# 17. What is Debouncing?

### Answer

Delay execution until user stops typing.


let timer;

$('#search').keyup(function(){

    clearTimeout(timer);

    timer = setTimeout(function(){

        console.log('API Call');

    },500);

});


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

html
<button
data-id="10"
data-price="999">
Buy
</button>


### jQuery


let id = $(this).data('id');


---

# 20. How do you store data in browser?

### LocalStorage


localStorage.setItem('name','John');


Persists after browser close.

---

### SessionStorage


sessionStorage.setItem('name','John');


Removed when tab closes.

---

# 21. Difference between LocalStorage and SessionStorage?

| LocalStorage             | SessionStorage       |
| ------------------------ | -------------------- |
| Permanent                | Tab-based            |
| Survives browser restart | Deleted on tab close |

---

# 22. How do you check if an element exists?


if($('.box').length){
    console.log('Found');
}


---

# 23. How to disable a button?


$('#btn').prop('disabled', true);


Enable:


$('#btn').prop('disabled', false);


---

# 24. What is Polling?

### Answer

Repeatedly checking server.


setInterval(function(){

    $.get('status.php');

},5000);


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


let button = $('#btn');


Instead of


$('#btn').hide();
$('#btn').show();
$('#btn').text('Save');


Use cached selector.

---
