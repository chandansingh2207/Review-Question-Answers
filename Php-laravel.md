
=============================================
1. How PHP works: request-response cycle
2. Can we work only with PHP
3. How to embedded HTML with PHP
4. Database engines, how transaction work
5. what is microservice and macroservice queues in JS
6. what is context, parameter
7. Does LLM holds any memory or database (large dataset)
8. prompt, hallucination
9. difference between chat Tool and google search

=======================================================================1

Here are simple interview-friendly answers:

## 1. How PHP works (Request → Response Cycle)

### Flow:

1. User opens a website in browser.
2. Browser sends a request to web server (Apache/Nginx).
3. Server finds the PHP file.
4. PHP code executes on the server.
5. PHP may read/write data from MySQL.
6. PHP generates HTML.
7. HTML is sent back to browser.
8. Browser displays the page.

### Example


<?php
echo "Hello World";
?>


Browser receives:

html
Hello World


**Important:** PHP runs on the server, not in the browser.

---

## 2. Can we work only with PHP?

**Yes, but with limitations.**

PHP can:

* Handle business logic
* Connect to database
* Create APIs
* Process forms

But modern websites usually need:

| Technology | Purpose          |
| ---------- | ---------------- |
| PHP        | Backend          |
| HTML       | Page structure   |
| CSS        | Design           |
| JavaScript | User interaction |
| MySQL      | Data storage     |

Example:

* PHP saves customer data.
* HTML shows form.
* CSS styles form.
* JavaScript validates form.

---

## 3. How to Embed HTML with PHP?

PHP can be mixed directly with HTML.

### Example
<h1>Welcome</h1>
<?php
$name = "Chandan";
?>
<p>Hello <?php echo $name; ?></p>

Output:
Welcome
Hello Chandan

### Alternative
<?= $name ?>

Same as:
<?php echo $name; ?>

---
## 4. Database Engines & How Transactions Work

### Common MySQL Engines

InnoDB supports transactions, foreign keys, row-level locking, and crash recovery, making it suitable for modern applications. MyISAM is simpler and can be faster for some read-only workloads, but it does not support transactions or foreign keys and uses table-level locking. Therefore, InnoDB is generally preferred.

| Feature                 | InnoDB               | MyISAM                           |
| ----------------------- | -------------------- | ---------------------------------|
| Transactions            | ✅ Supported          | ❌ Not supported               |
| Rollback (Undo changes) | ✅ Yes                | ❌ No                          |
| Foreign Keys            | ✅ Yes                | ❌ No                          |
| Data Safety             | ✅ Better             | ❌ Lower                       |
| Table Locking           | ❌ Row-level locking  | ✅ Table-level locking         |
| Read Speed              | Good                 | Often faster for simple reads    |
| Crash Recovery          | ✅ Automatic recovery | ❌ More risk of corruption     |


Most projects use **InnoDB**.

### What is a Transaction?

A transaction is a group of SQL statements that should either:

* All succeed
* Or all fail

### Example: Bank Transfer

sql
START TRANSACTION;

UPDATE account
SET balance = balance - 1000
WHERE id = 1;

UPDATE account
SET balance = balance + 1000
WHERE id = 2;

COMMIT;
If any query fails:

sql
ROLLBACK;

Money won't be lost.

### Interview Definition

> Transaction ensures data consistency by treating multiple SQL operations as one unit.

---


### Queue in JS/System Design

Queue is used for background tasks.

Example:

Customer places order.

Instead of:
Order → Send Email → Generate Invoice → SMS
User waits.

Use Queue:
Order Created
     ↓
 Queue
     ↓
 Worker processes Email/SMS later

Popular:

* Redis Queue
* RabbitMQ
* Amazon SQS

---

## 6. What is Context and Parameter?

Context is the information that AI uses to understand your request and generate a relevant response.

Parameter
Parameters are the internal values (weights) that an AI model learns during training.

Input passed to a function.

javascript
function greet(name) {
   console.log(name);
}


`name` is a parameter.

### Context

The environment in which code runs.

JavaScript example:

javascript
const user = {
   name: "Chandan",
   show() {
      console.log(this.name);
   }
}


Here `this` refers to current object.

That current object is the context.


---

## 7. Does LLM Hold Any Memory or Database?

An LLM has two different kinds of "memory"

Context Window (Temporary Memory):
----------------------------------
Remembers the current conversation.
Uses previous messages to answer follow-up questions.
Once the conversation ends or the context is removed, that information is no longer available.

Persistent Memory (if a system provides it):
---------------------------------------------
Some AI applications can save user preferences or notes separately.
This is handled by an external memory system, not by the LLM's parameters themselves.

### Short Answer
No.
Context Window (Temporary Memory)

LLM does not work like MySQL.

### During Training
Model learns patterns from huge amounts of text.

After training:
* Knowledge is stored as weights (numbers)
* Not as rows and tables

### Example

MySQL:

ID | Name
1  | Chandan

LLM:
Does not store data like this.
It stores learned patterns.

### Memory in ChatGPT
There can be:

1. Conversation Context
2. Saved Memory (if enabled)
3. External Database/Vector DB connected by developers

---

## 8. Prompt and Hallucination

### Prompt

Instruction given to AI.

Example:


Explain MySQL JOIN in simple terms.


This is a prompt.

### Hallucination

AI generates information that sounds correct but is actually wrong.

Example:


Who won Cricket World Cup 2030?


AI may invent an answer because the event hasn't happened.

### How to Reduce Hallucination?

* Give clear prompts
* Provide context
* Use RAG (database search)
* Use MCP/tools
* Verify important answers

---

## 9. Difference Between ChatGPT Tool and Google Search

| ChatGPT              | Google Search                            |
| -------------------- | ---------------------------------------- |
| Gives direct answer  | Gives links                              |
| Understands context  | Keyword search                           |
| Can summarize        | User reads websites                      |
| Can write code       | Cannot directly write complete solutions |
| Can explain concepts | Finds pages containing concepts          |

### Example

Ask:
Explain Laravel Middleware.

### Google

Returns links:

* Docs
* Blogs
* Tutorials

### ChatGPT

Directly explains:

> Middleware is a filter that runs before or after a request. It is used for authentication, logging, etc.

### Best Practice

* Use Google to find sources.
* Use ChatGPT to understand and summarize.






Compliance:
=======================
Payment Card Industry Data Security Standard (PCI DSS)
PCI DSS (Payment Card Industry Data Security Standard) is a security standard designed to protect credit and debit card information.

GDPR (General Data Protection Regulation) is a privacy law of the European Union that governs how organizations collect, store, process, and protect personal data of individuals in the EU/EEA.

CAN-SPAM Act (Simple Explanation)
==================================
Entity: CAN-SPAM Act

The CAN-SPAM Act is a US law for marketing emails.

It tells businesses how to send promotional emails legally.

Rules

✅ Tell users who sent the email

✅ Use a genuine subject line

✅ Include your business information

✅ Provide an unsubscribe link

✅ Stop sending emails after a user unsubscribes

Digital Personal Data Protection Act (DPDP Act)
===============================================
Entity: Digital Personal Data Protection Act
The DPDP Act is India's privacy and personal data protection law.
Its purpose is to protect people's personal information online.




============================

Ques,jobs,schedulers

Service Provider
=====================
A Service Provider is where you register services in the container.
It tells Laravel what services and classes to load when the app starts.

When Laravel loads Service Providers, it runs two important methods:

👉 register() → Register services

👉 boot() → Start or configure services

config/app.php file inside 'providers' array 

config/app.php → providers array (Simple Explanation)

The providers array is a list of Service Providers that Laravel loads when the app starts.

👉 In simple words:
It tells Laravel which setup files to run first.


Example (config/app.php)
'providers' => [
    App\Providers\AppServiceProvider::class,
    App\Providers\AuthServiceProvider::class,
    App\Providers\RouteServiceProvider::class,
],


Service Container: 
==================
The Laravel Service Container is a powerful tool for managing class dependencies and performing dependency injection in our application. Here’s a concise overview of its key features and usage:

🔹 Step 1: Create a Service Class

📂 app/Services/PaymentService.php
===================================

<?php

namespace App\Services;

class PaymentService
{
    public function pay()
    {
        return "Payment Done";
    }
}



🔹 Step 2: Use Service in Controller (Dependency Injection)
============================================================

📂 app/Http/Controllers/OrderController.php

<?php

namespace App\Http\Controllers;

use App\Services\PaymentService;

class OrderController extends Controller
{
    public function store(PaymentService $paymentService)
    {
        return $paymentService->pay();
    }
}



| Without Service Container          | With Service Container               |
| ---------------------------------- | ------------------------------------ |
| `$payment = new PaymentService();` | Laravel automatically creates object |
| Manual object creation             | Automatic dependency injection       |
| Tight coupling                     | Loose coupling                       |




Laravel is automatically giving PaymentService to the store() method.


👉 You did NOT create it using new PaymentService()
Laravel did it for you using the Service Container.



Dependency injection :
======================
In Laravel, dependency injection allows us to inject dependencies (like services, classes, or objects) directly into the constructor 
method of a class, rather than having to manually create instances of these dependencies.



Step 1: Service Provider Example
================================
namespace App\Services;

class SMSService {
    public function send($msg)
    {
        return "SMS Sent: ".$msg;
    }
}



Step 2: Inject it in Controller
==================================
use App\Services\SMSService;

class UserController extends Controller  //"UserController is a controller and gets all Laravel controller features."
{
    public function sendSMS(SMSService $sms) //"I need an object of SMSService."
    {
        return $sms->send("Welcome User!");
    }
}




✔ Laravel automatically creates SMSService

✔ Injects it into the method

✔ No need to do $sms = new SMSService()

1. Job
=============
A Job is a class that contains a task.

Example: Send an email after user registration.

Create a job:

php artisan make:job SendWelcomeEmail

Job class:

class SendWelcomeEmail implements ShouldQueue
{
    public function handle()
    {
        Mail::to('[email protected]')
            ->send(new WelcomeMail());
    }
}

The actual work is written inside the handle() method.


2. Queue
===============
A Queue executes jobs asynchronously (in the background).

Without Queue:

User clicks Register
↓

Email sent
↓

Response returned

User waits until the email is sent.

With Queue:

User clicks Register
↓

Job pushed to queue
↓

Response returned immediately
↓

Queue worker sends email

Dispatch a job:

SendWelcomeEmail::dispatch();

Run queue worker:

php artisan queue:work

Common queue drivers:

Database

Redis

Amazon SQS

Beanstalkd


3. Scheduler
=====================
The Task Scheduler runs tasks automatically at scheduled times.

Instead of creating multiple cron jobs:

Backup database at 1 AM

Send reports at 8 AM

Clear cache every hour

Laravel manages them centrally.

Example in routes/console.php (Laravel 11+) or scheduler configuration:

Schedule::command('backup:run')
    ->dailyAt('01:00');

Run every minute from server cron:

* * * * * php /path-to-project/artisan schedule:run

Laravel then decides which tasks should execute.


Interface:
===========
The interface only declares methods; it does not contain the actual implementation.

An interface defines what methods a class must implement, but not how those methods work.


⭐ Key Points

Interface has only method declarations, no method body.

A class can implement multiple interfaces.

Used to achieve abstraction.


Interfaces: 
PHP supports interface inheritance, where a class can implement multiple interfaces. Interfaces define contracts that classes must follow 
by implementing specified methods. This allows classes to inherit method signatures from multiple sources without inheriting 
implementation details.

Ex: 
====
interface Animal {
    public function makeSound();
}


class Dog implements Animal {
    public function makeSound() {
        echo "Bark";
    }
}


class Cat implements Animal {
    public function makeSound() {
        echo "Meow";
    }
}


Abstract Class:
=================
An abstract class in PHP is used to define a common structure and force child classes to follow certain rules while sharing common code.

An abstract class contains both abstract and normal methods and is used as a base class for other classes.

Abstract class can have method body.

Abstract class can have abstract methods.

Child class must implement abstract methods.


Real-Life Example: Vehicle

Think of a Vehicle.

Every vehicle can start, but the way it moves differs:

Car moves on roads.

Boat moves on water.

Airplane moves in the air.

So, we create an abstract class Vehicle with a common method and an abstract method.

Abstract class defines common behavior and forces child classes to implement required methods.


abstract class Payment {
    abstract public function pay();
}



class CreditCard extends Payment {
    public function pay() {
        echo "Pay via Card";
    }
}


Supports single inheritance.

| Feature          | **Abstract Class**                             | **Interface**                                 |
| ---------------- | ---------------------------------------------- | --------------------------------------------- |
| Methods          | Can have **abstract + normal methods**         | Only **method declarations**                  |
| Method Body      | ✅ Allowed                                     | ❌ Not allowed                               |
| Variables        | Can have properties                            | ❌ No properties                              
| Inheritance      | A class can **extend only one** abstract class | A class can **implement multiple** interfaces |
| Access Modifiers | Can use `public`, `protected`, `private`       | Methods are **public by default**             |
| Object Creation  | ❌ Cannot create object                        | ❌ Cannot create object                     |
| Purpose          | Provides **base code + rules**                 | Provides **only rules (contract)**            |
| Use Case         | When some common logic is shared               | When behavior must be enforced                |
| Keyword Used     | `extends`                                      | `implements`                                  |



12) Explain traits in Laravel. 
==============================
A trait is a reusable piece of code that we can use in many Classes.
A trait is used to reuse common functionality across multiple Classes in PHP.

Key Points
==========
Traits contain methods with body.
One class can use multiple traits.
Avoids code duplication.
Uses use keyword.


In PHP, multiple inheritance is not supported. **** Use to create reusable function.

*****In PHP, A trait is a mechanism for code reuse that allows developers to create reusable functions/methods 
that can be used in multiple classes.


Example:
========

trait LoggerTrait
{
    public function log($message)
    {
        echo $message;
    }
}

Using Trait in a Class

class User
{
    use LoggerTrait;
}


$user = new User();
$user->log('User created');



Example:
========

<?php

trait Hello {
    public function sayHello() {
        echo 'Hello';
    }
}

// Define a class that uses the trait
Class Greeting {

    use Hello;
    public function greet($name) {
        $this->sayHello();
        echo $name;
    }

}

// Create an instance of the class and call the method
$obj = new Greeting();
$obj->greet('Alex'); // Outputs: Hello Alex

?>

Difference Between isset() and empty() in PHP
===============================================
isset()
========
Checks whether a variable:
Exists, and
Is not NULL

$name = "Chandan";

if(isset($name)){
    echo "Variable exists";
}

empty()
========
empty() checks whether a variable has an empty value such as "", 0, false, NULL, or an undefined variable.

$name = "";

if(empty($name)){
    echo "Variable is empty";
}


##.htaccess file##
==================
.htaccess is used to configure Apache web server settings such as URL rewriting, redirects, security rules, and HTTPS enforcement at the application level.


##.ini file##
==============
.ini files are used to store application or server configuration settings in a simple key-value format.

Upload file size
Memory limit
Error reporting
Timezone
upload_max_filesize = 20M
memory_limit = 256M


robots.txt File
=================
Used to tell search engine crawlers which pages or folders they can or cannot access.


### 1. What is ORM (Object-Relational Mapping)?

ORM is a technique that lets you work with database tables as PHP objects instead of writing SQL queries manually.

**Example:**
$user = User::find(1);
echo $user->name;


Instead of:
sql
SELECT * FROM users WHERE id = 1;

---

### 2. Difference between CHAR and VARCHAR?

| CHAR              | VARCHAR                 |
| ----------------- | ----------------------- |
| Fixed length      | Variable length         |
| Faster            | Saves space             |
| Pads extra spaces | Stores only actual data |

**Example:**

sql
CHAR(10) = 'PHP'      // Uses 10 chars
VARCHAR(10) = 'PHP'  // Uses only 3 chars


---

### 3. What is Cardinality in Database?

Cardinality means **how unique the values are in a column**.

**Example:**

* Email column → High Cardinality (mostly unique)
* Gender column → Low Cardinality (Male/Female)

High cardinality columns are good candidates for indexing.

---

### 4. What is UNION in SQL?

UNION combines results from multiple SELECT queries.

SELECT name FROM employees
UNION
SELECT name FROM customers;

Returns all unique names from both tables.

---

### 5. Difference between UNION and INNER JOIN?

**UNION**

* Combines rows vertically.
* Same number of columns required.

SELECT name FROM employees
UNION
SELECT name FROM customers;


**INNER JOIN**

* Combines related data horizontally.
* Uses matching columns.

SELECT e.name, d.department
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.id;

---

### 6. Purpose of $$a and &$a in PHP?

#### $$a (Variable Variable)

$a = "name";
$$a = "Chandan";

echo $name; // Chandan

`$$a` means the value of `$a` becomes the variable name.

#### &$a (Reference)

$a = 10;
$b = &$a;

$b = 20;

echo $a; // 20

Both variables point to the same memory location.

---

### 7. Difference between break and continue?

**break**

* Stops the loop completely.

for($i=1;$i<=5;$i++){
    if($i==3) break;
    echo $i;
}
// Output: 1 2


**continue**
* Skips current iteration.


for($i=1;$i<=5;$i++){
    if($i==3) continue;
    echo $i;
}
// Output: 1 2 4 5

---

### 8. break vs exit()

**break**

* Stops only the loop.

**exit()**

* Stops the entire PHP script.

### 9. Have you used single pipe (|) operator in PHP?

Yes.

It is a **Bitwise OR** operator.


$a = 5; // 101
$b = 3; // 011

echo $a | $b; // 111 = 7


Commonly used in permissions, flags, and bit masking.

---

### 10. What is a Trait in PHP?

Trait is a mechanism for reusing code across multiple classes.


trait Logger {
    public function log() {
        echo "Logging";
    }
}

class User {
    use Logger;
}


---

### 11. Benefit of Traits?

* Reuse code
* Avoid duplication
* Multiple classes can use the same methods

**Example:** Logging, File Upload, Email Sending functions.

---

### 12. Static Variable vs Regular Variable

#### Static Variable

Shared by all objects.


class Test {
    public static $count = 0;
}


Access:
Test::$count;

#### Regular Variable

Each object gets its own copy.

class Test {
    public $name;
}

---
### 13. Can a private member be accessed outside the class?

**No.**

class User {
    private $name = "John";
}

$user = new User();
echo $user->name; // Error
---

### 14. How can you access a private member outside the class?

Using a **public getter method**.


class User {
    private $name = "John";

    public function getName() {
        return $this->name;
    }
}



echo $user->getName();


---

### 15. Real-life example of Abstract Class

Abstract class defines common behavior and forces child classes to implement required methods.


abstract class Payment {
    abstract public function pay();
}



class CreditCard extends Payment {
    public function pay() {
        echo "Pay via Card";
    }
}


**Real-life:** Payment Gateway system (Card, UPI, PayPal all have different payment methods).

---

### 16. Purpose of .htaccess File

`.htaccess` is used to configure the web server.

Common uses:

* URL Rewriting
* Redirects
* Password Protection
* Custom Error Pages
* Force HTTPS

Example:

apache
RewriteEngine On
RewriteRule ^product/([0-9]+)$ product.php?id=$1


---

### 17. How many types of APIs have you worked with?

Typical answer:

> I have mainly worked with REST APIs. I have integrated payment APIs, CRM APIs, shipping APIs, SMS APIs, email APIs, and third-party services using JSON over HTTP.

Examples:

* Stripe API
* Twilio API
* Shopify API
* Checkout APIs
* CRM APIs

---

### 18. What does REST stand for?

**REST = Representational State Transfer**

It is an architectural style used to build web APIs.

---

### 19. What makes REST APIs useful?

* Simple to use
* Uses HTTP methods (GET, POST, PUT, DELETE)
* Fast communication between applications
* Language independent
* Widely supported

**Example:**

http
GET /users/1


Returns user information in JSON format.

---

### 20. Do you have any questions you'd like to ask me?

Good interview questions:

1. What are the main responsibilities of this role?
2. What technologies does the team currently use?
3. What challenges is the team facing?
4. How is success measured in this position?
5. What are the next steps in the interview process?

These questions show interest and professionalism.

---

### Quick Interview Answers (1 Line)

* **ORM:** Database tables mapped to PHP objects.
* **CHAR:** Fixed length string.
* **VARCHAR:** Variable length string.
* **Cardinality:** Uniqueness of data in a column.
* **UNION:** Combines results of multiple SELECT queries.
* **INNER JOIN:** Combines related data from tables.
* **$$a:** Variable variable.
* **&$a:** Reference variable.
* **break:** Exit loop.
* **continue:** Skip current iteration.
* **exit():** Stop entire script.
* **Trait:** Reusable code block for classes.
* **Static Variable:** Shared across all objects.
* **Private Member:** Accessible only inside class.
* **Abstract Class:** Base class with mandatory methods.
* **.htaccess:** Apache configuration file.
* **REST:** Representational State Transfer.
* **REST API Benefit:** Simple, scalable, and widely used.

=========================================================================================================================================
LARAVEL :
---------------------

Reference :

https://www.guru99.com/laravel-interview-questions.html  

Laravel 11 was released on March 12, 2024.

Laravel 10 was released in February 2023  support for PHP 8.1, meaning that developers must upgrade to PHP 8.1 or later to use Laravel 10.

Laravel 9 was released in February 2022 and supported PHP 8.0 but also PHP 7.4. 


Laravel (Release date June 2011)
---------------------------------

laravel is a free and open-source PHP web framework, created by Taylor Otwell and intended for the development of web applications following the model–view–controller architectural pattern and based on Symfony.

How laravel works ?
--------------------
The Laravel request lifecycle involves the following key stages:

Laravel works by receiving a request through index.php, processing it via middleware, routes, and controllers, and then sending a response back to the user.

Incoming request
Entry point (public/index.php)
Bootstrap process
Service providers registration
HTTP Kernel and middleware handling
Routing
Controller processing
Response creation
Response middleware
Final response to the user
Logging and termination

php artisan key:generate
=========================
Generates a unique APP_KEY for a Laravel application, which is used to encrypt sessions, cookies, and sensitive data.
It is required for application security and must be set before running the app.

One-liner (interview gold ✨):
👉 It creates the encryption key that secures Laravel’s data.

MVC splits an application into 3 parts.
==========
HMVC (Hierarchical MVC)
==========
Simple meaning:
HMVC is MVC inside MVC (modules).


| MVC                            | HMVC               |
| ------------------------------ | ------------------ |
| Single structure               | Modular structure  |
| One big application            | Many small modules |
| Simple apps                    | Large apps         |
| Less organized in big projects | Highly organized   |



Eloquent ORM (Object Relational Mapping)
=========================================
Eloquent lets us work with database tables using PHP classes instead of writing SQL queries manually.

Why Use Eloquent?

Benefits:

Easy syntax
Less SQL writing
Faster development
Relationship handling
Cleaner code



✅ What is boot() used for in a Laravel Model?
===============================================
The boot() method is used to run code automatically when a model event happens.

It allows you to hook into model events like:

creating
created
updating
updated
deleting
deleted

Ex: This is called automatically when a new record is being created

protected static function boot()
{
    parent::boot();

    static::creating(function ($funnel) {  // called automatically when a new record is being created
        if (empty($funnel->slug)) {
            $funnel->slug = Str::slug($funnel->funnel_name);
        }
    });
}


robot.txt
=============
robots.txt is a file that tells search engines what they can or cannot visit on your website.

Simple Example
User-agent: *
Disallow: /admin/
Allow: /


Meaning:
User-agent: * → all bots
Disallow: /admin/ → don’t crawl admin page
Allow: / → allow everything else


✅ LARAVEL 12 - COMPLETE BLOG MODULE SETUP (EXISTING PROJECT)

============================================================ 
PHASE 1 -
CREATE REQUIRED FILES
============================================================

1.  Create Model, Migration, Factory, Seeder: 
Command: php artisan make:model Blog -mfs

2.  Create Resource Controller: 
Command: php artisan make:controller BlogController –resource

============================================================ 
PHASE 2 -
CONFIGURE MIGRATION
============================================================

File: database/migrations/xxxx_create_blogs_table.php

Replace the up() method with:

Schema::create(‘blogs’, function (Blueprint $table) {
$table->id();
$table->string(‘title’); 
$table->string(‘slug’)->unique();
$table->text(‘content’); 
$table->string(‘image’)->nullable();
$table->boolean(‘status’)->default(1);
$table->timestamps(); 
});

Run Migration: php artisan migrate

============================================================ 
PHASE 3 -
CONFIGURE MODEL
============================================================

File: app/Models/Blog.php

Add:

use HasFactory;

protected $fillable = [ ‘title’, ‘slug’, ‘content’, ‘image’, ‘status’];

(Optional Slug Auto Generation inside boot method)

============================================================ 
PHASE 4 -
CONFIGURE FACTORY
============================================================

File: database/factories/BlogFactory.php

use Illuminate\Support\Str;

public function definition(): array
{
    $title = $this->faker->sentence();

    return [
        'title'   => $title,
        'slug'    => Str::slug($title),
        'content' => $this->faker->paragraph(),
        'image'   => null,
        'status'  => 1,
    ];
}

============================================================ 
PHASE 5 -
CONFIGURE SEEDER
============================================================

File: database/seeders/BlogSeeder.php

Add:

Blog::factory()->count(20)->create();

Register in: database/seeders/DatabaseSeeder.php

$this->call(BlogSeeder::class);

Run Seeder: php artisan db:seed

============================================================ 
PHASE 6 -
ADD ROUTES 
============================================================

File: routes/web.php

Add:

Route::resource(‘blogs’, BlogController::class);

============================================================ 
PHASE 7 -
CONTROLLER METHODS (CRUD)
============================================================

File: app/Http/Controllers/BlogController.php

Methods required:

index() - List blogs
create() - Show create form
store() - Save blog
show() - View single blog 
edit() - Show edit form 
update() - Update blog
destroy() - Delete blog

============================================================ 
PHASE 8 -
CREATE VIEWS
============================================================

Create folder: resources/views/blogs

Create files: index.blade.php ,create.blade.php, edit.blade.php, show.blade.php

============================================================ 
PHASE 9 -
TEST MODULE 
============================================================

1.  Run server: php artisan serve

2.  Open in browser: http://127.0.0.1:8000/blogs

3.  Test Create, Edit, Delete functionality

============================================================ 
FINAL
RESULT 
============================================================

-   Blogs table created
-   Full CRUD operations working
-   Seeder data inserted
-   Clean Laravel module structure

====================================================END OF BLOG MODULE SETUP===================================

| Factory                       | Seeder                       |
| ==============================| ============================ |
| Generates fake data structure | Calls factory to insert data |
| Used for testing              | Used for database population |
| Can be used in Tinker         | Used in `db:seed` command    |


What is a pivot?
================
In Laravel 12, a pivot is used for a many-to-many relationship.
A pivot table is the middle (join) table that connects two models.

In your case:
Order
Product

One order can have many products, and one product can belong to many orders → many-to-many.

Composer:  
=========
Composer is a tools used to managing its dependencies, which are noted in the composer.json file and placed in the source folder.

**** A composer is a tool that includes all the dependencies and libraries. Composer is used to managing its dependencies, which are noted in the composer.json file and placed in the source folder.

A composer is a tool that includes all the dependencies and libraries. It helps the user to develop a project concerning the mentioned framework. Third-party libraries can be installed easily using composer.


Laravel Tinker
===============
Laravel Tinker is a command-line tool in Laravel used to run PHP/Laravel code directly without creating routes or controllers.

Run this command in terminal:

php artisan tinker

Fetch Data
User::all();





Kernal : It serves as the main entry point for the application's request lifecycle.
==========
Handle incoming request and response. Kernal handles the incoming requests and their corresponding responses. 
It serves as the main entry point for the application's request lifecycle

In Laravel, the Kernel is a crucial component that handles the incoming requests and their corresponding responses. 
It serves as the main entry point for the application's request lifecycle.

There are two primary kernels in Laravel: HTTP kernal, Console Kernal
-----------------------------------------

| Feature | HTTP Kernel            | Console Kernel            |
| ------- | ---------------------- | ------------------------- |
| Handles | Web requests           | CLI (Artisan) commands    |
| Uses    | Middleware             | Console commands          |
| File    | app/Http/Kernel.php    | app/Console/Kernel.php    |
| Purpose | Process HTTP lifecycle | Process command lifecycle |



1. HTTP Kernel:
================
Purpose: Manages incoming HTTP requests and responses.

Handles web requests, manages middleware, and routes requests to the appropriate controllers.

Location: app/Http/Kernel.php


Key Features:

Middleware Registration: Defines global middleware that runs on every request, as well as route-specific middleware that runs only for 
certain routes.

Request Handling: Receives the incoming request and processes it through the registered middleware, routing, and controllers.

Response Handling: Prepares and sends the response back to the user after all processing is complete.


protected $middleware = [
    \App\Http\Middleware\CheckForMaintenanceMode::class,
    // Other global middleware...
];

protected $routeMiddleware = [
    'auth' => \App\Http\Middleware\Authenticate::class,
    // Other route-specific middleware...
];


2.Console Kernel:
==================
Purpose: Manages console commands and Artisan commands.

Manages Artisan commands, allowing for custom command registration and task scheduling.

Location: app/Console/Kernel.php


Key Features:
Command Registration: Registers custom Artisan commands and built-in commands.
Schedule Tasks: Defines scheduled tasks that run at specified intervals using the Laravel scheduler.

Example:
protected $commands = [
    \App\Console\Commands\YourCustomCommand::class,
    // Other commands...
];

protected function schedule(Schedule $schedule)
{
    $schedule->command('your:command')->hourly();
}


Laravel 12 Packages (Super Short – Interview Ready)
======================================================
Laravel 12 provides official packages like Sanctum, Passport, Socialite, Cashier, Scout, Horizon, Telescope, and Envoy to handle 
authentication, APIs, billing, search, queues, debugging, and deployment.

Breeze → Simple authentication
Jetstream → Advanced auth (2FA, teams)
Sanctum → API auth for SPA & mobile
Passport → OAuth2 for public APIs
Socialite → Social login (Google, Facebook)
Cashier → Subscription payments
Scout → Full-text search
Horizon → Redis queue dashboard
Telescope → Debug & monitor app
Envoy → Deployment automation

One-liner:
==========
Laravel 12 official packages handle auth, APIs, payments, search, queues, debugging, and deployment.

Laravel Default Package:
========================
Although Laravel has various packages for developers, a few default packages come pre-installed with the framework. 
These default Laravel packages include:

Socialite === easy way to authenticate users via OAuth providers.Enable login with social accounts (Google, Facebook, GitHub, etc.).
Cashier ===   Laravel Cashier provides an interface for managing subscription billing with services like Stripe and Braintree.
Passport === Laravel Passport is an OAuth2 server implementation for API authentication.


Envoy    === Laravel Envoy is a tool for running deployment scripts and task automation.
Scout  === solution for full-text search.
Telescope === Debug application behavior in real-time.Monitor requests, exceptions, database queries, and logs.
Horizon === Laravel Horizon provides a beautiful dashboard and configuration system for managing Redis queues.Monitor queue job 
processing in real-time.Track job failures and retry attempts.Configure queue workers and their settings from the dashboard.



******Laravel Blade Template : Use to define section of content that filled by child theme.
==============================
A Laravel Blade template is Laravel’s built-in templating engine used to create dynamic HTML pages in a clean and structured way.

@yield is used in Laravel Blade templates to "show content from child pages inside a layout."
==============================
Define a Layout with @yield:

example:    @yield('content') == Show content from child pages.

Create a layout file (e.g., layouts/app.blade.php):
=======================
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@yield('title')</title>
</head>
<body>
    <header>
        <h1>My Website</h1>
    </header>

    <main>
        @yield('content')
    </main>

    <footer>
        <p>© 2024 My Website</p>
    </footer>
</body>
</html>

Create a Child View:
=====================
In your child view (e.g., views/home.blade.php), you can extend the layout and fill in the sections defined by @yield:

@extends('layouts.app')

@section('title', 'Home Page')

@section('content')
    <h2>Welcome to the Home Page</h2>
    <p>This is the main content area.</p>
@endsection

@extends
Used to connect a Blade page to a layout file.
(It tells Laravel which layout this page will use.)

@section
Defines a content section in the page.
This content is injected into the matching @yield in the layout.

Flexibility: You can have multiple sections in your layout and customize the content in each child view.

@push('css'):used in Laravel Blade to add CSS from a child page into a layout.

@stack('css'):used in a layout file to display all CSS that was pushed from child pages.

@push('css') → adds CSS to stack
@stack('css') → outputs all added CSS

6️⃣ Display Data

{{ }} → escaped output

{!! !!} → unescaped HTML

$message = "<strong>Success!</strong> Data saved.";

{{ $message }} → shows
<strong>Success!</strong> Data saved.

{!! $message !!} → shows
Success! Data saved.


Laravel commands :
--------------------
php artisan make:model Todo -mcr


Brief :

-m, to create migration

-c to create controller

-r to specify the controller has resource



The command php artisan make:model Todo -mcr in Laravel generates several files and classes related to a "Todo" model with certain features enabled:

| Flag   | Full Form      | What it Creates             | Purpose                          |
| ------ | -------------- | --------------------------- | -------------------------------- |
| **-m** | `--migration`  | Migration file              | Creates table structure in DB    |
| **-c** | `--controller` | Controller file             | Handles HTTP requests            |
| **-r** | `--resource`   | Resource controller methods | Creates **RESTful CRUD methods** |


public function index()    // Show all records
public function create()   // Show form to create
public function store()    // Save new record
public function show()     // Show single record
public function edit()     // Show form to edit
public function update()   // Update record
public function destroy()  // Delete record



Model (Todo.php): path : app/Models
-------------------------------------
Model intract with the database table associated with it. 

This creates the model class itself, typically located in the app/Models directory.
It provides an interface for interacting with the database table associated with the Todo model.

Migration (create_todos_table.php): path : database/migrations
------------------------------------------------------------------
This creates a migration file under the database/migrations directory.

The migration file contains instructions for creating the corresponding database table for the Todo model.

Controller (TodoController.php): Controller Handle CRUD Operation.
-------------------------------------------------------------------
The controller handles HTTP requests related to CRUD (Create, Read, Update, Delete) operations for the Todo model.

This generates a controller class under the app/Http/Controllers directory.

Resource (TodoResource.php): Function to handle crud operation 
------------------------------
The function of a resource controller in Laravel is to handle typical CRUD (Create, Read, Update, Delete) operations on a resource, such 
as a database table, by defining and implementing methods that correspond to these actions. It simplifies the routing and handling of 
these operations, following RESTful conventions.

Laravel :
-----------
Laravel is a popular PHP framework known for its elegant syntax and powerful features. It comes with a set of helpful command-line tools 
known as Artisan commands.

These commands allow us to perform various tasks such as database migrations, seeding, generating code scaffolding, clearing caches, and 
more. Below are some commonly used Artisan commands in Laravel:

Creating a new Laravel project:
-------------------------------------
composer create-project --prefer-dist laravel/laravel projectName

--prefer-dist: *************
===============================
This is an option for the create-project command that specifies a preference for downloading package distributions (i.e., pre-built packages) rather than cloning the version control repository. This option can speed up the installation process by avoiding the need to clone the entire repository.

When we run this command, Composer will download the Laravel framework and its dependencies, set up the project structure, and install 
any required packages. After the command completes, 
well have a new Laravel project set up in a directory with the name we specified.


Starting the development server:
----------------------------------
php artisan serve

Creating a new controller:
---------------------------
php artisan make:controller ControllerName

Creating a new model:
----------------------
php artisan make:model ModelName

Creating a new migration:
---------------------------
php artisan make:migration create_table_name

Running migrations:
----------------------
php artisan migrate

Rolling back the last database migration:
-------------------------------------------
php artisan migrate:rollback

Seeding the database:
------------------------
php artisan make:seeder UsersTableSeeder

php artisan db:seed

Inside the seeder class, we define the sample data we want to insert. 
For example, we might create multiple users or populate other tables with sample records.

Generating a new middleware:
-----------------------------------
php artisan make:middleware MiddlewareName

Creating a new artisan command:
--------------------------------
php artisan make:command CommandName

Clearing the cache:
-----------------------
php artisan cache:clear

Clearing configuration cache:
------------------------------
php artisan config:clear

Clearing route cache:
--------------------------
php artisan route:clear

Viewing all available Artisan commands:
------------------------------------------
php artisan list


Laravel:
---------
Route, Reverse routing, routing group (which i used in admin route and written all admin related routes inside the admin route).

Explain web.php: (web.php is the primary route file)
=================
These routes handle web requests that users make through their browsers.

web.php is where we define routes that respond to HTTP GET, POST, PUT, PATCH, and DELETE requests. 
These routes handle web requests that users make through their browsers.

In Laravel, web.php is the primary route file for defining routes that are typically accessed via web browsers. When we create a new
Laravel application, we will find this file located in the routes directory (routes/web.php).

Here’s what web.php is used for and how it fits into a Laravel application:

Defining Web Routes: web.php is where we define routes that respond to HTTP GET, POST, PUT, PATCH, and DELETE requests. 
These routes handle web requests that users make through their browsers.

Middleware Group: By default, the routes defined in web.php are assigned to the web middleware group. This group provides features like session state and CSRF protection, which are commonly needed for web applications.

Route Naming and Namespace: we can name routes and apply route middleware within web.php. Additionally, routes defined here are typically in the global namespace.

Named Routes
================
we may specify a name for a route by chaining the name method onto the route definition:

Named routes allow the convenient generation of URLs or redirects for specific routes. 

Route::get('/user/profile', function () {})->name('profile');


Reverse routing :
==================
In Laravel, reverse routing refers to the process of generating URLs based on named routes . 

Using Reverse routing we can generate URLs based on route names.

Example:

Route::get('user/profile', function () {})->name('profile');

<a href="{{ route('profile') }}">Edit User</a>

Using Named Routes in Redirects

Named routes are particularly useful when redirecting within application. Instead of hardcoding URLs, we can use the route names:

return redirect()->route('profile');


Route Groups : 
=================
Route groups let us apply common settings (like prefix, middleware, controller, namespace) to multiple routes at once.

For admin we create a admin route group and add all the admin related routes inside this group.


🔹 3. Prefix + Middleware (Most Common)

Route::prefix('admin')
    ->middleware(['auth', 'admin'])
    ->group(function () {


        Route::get('/dashboard', function () {
            return 'Dashboard';
        });


        Route::get('/reports', function () {
            return 'Reports';
        });
});


6. Combine prefix + name + controller

🔥 Very common in real projects

Route::prefix('admin')
    ->name('admin.')
    ->controller(AdminController::class)
    ->group(function () {


        Route::get('/dashboard', 'dashboard')->name('dashboard');
        Route::get('/users', 'users')->name('users');
});


CSRF (Cross-Site Request Forgery) : Laravel generates CSRF tokens for each active user session.
=====================================
Laravel generates CSRF tokens for each active user session.

These tokens are included automatically in forms and AJAX requests generated by Laravel, typically through the @csrf Blade directive.

CSRF (Cross-Site Request Forgery) is a type of attack where unauthorized commands are transmitted from a user to the web application.

Laravel provides built-in CSRF protection to guard against these attacks, ensuring the security of web application.

Laravel generates CSRF tokens for each active user session. 
These tokens are included automatically in forms and AJAX requests generated by Laravel, 
typically through the @csrf Blade directive.

<form method="POST" action="/profile">
    @csrf
    <!-- Other form fields -->
</form>


Laravel Cashier (Stripe) :  This is the package for stripe in laravel.
==========================
Laravel Cashier is an official Laravel package that provides an easy interface for Stripe subscriptions and payments.

composer require laravel/cashier

📦 Install Cashier (Stripe)
Step 1: Install package
composer require laravel/cashier

📌 Step 2: Add Stripe Keys in .env
STRIPE_KEY=pk_test_xxx
STRIPE_SECRET=sk_test_xxx

📌 Step 3: Add Billable Trait to User Model
use Laravel\Cashier\Billable;

class User extends Authenticatable
{
    use Billable;
}


This gives the User model methods like:

charge()

newSubscription()

subscribed()

subscription()

invoices()

🔄 Step 4: Run Cashier Migration
php artisan vendor:publish --tag="cashier-migrations"
php artisan migrate


This creates subscription tables:

subscriptions

subscription_items

customers

charges


Test Card:
================

Name: Test

Number: 4242 4242 4242 4242

CSV: 123

Expiration Month: 12

Expiration Year: 2028


Laravel Social Media login (Facebook,Linkedin,Twitter) : Laravel Socialite is the Package.
=======================================================
Laravel Socialite is the package used for social login.

Laravel Socialite is Laravel’s official package for OAuth-based social login.
It makes it extremely easy to authenticate users using popular platforms like:

Google
Facebook
GitHub
LinkedIn
Twitter
Instagram
Bitbucket
GitLab
Microsoft
Apple (via Socialite Providers)


For Facebook login Steps:
============================
Fill in the required fields like App Name, Application Description, and Website URL. Callback URLs should be set to 

Go to Facebook for Developers and sign in with your Facebook account.

for Facebook Login with Laravel Socialite, you must create a Facebook App in Meta Developers.
This app can be private (development mode) during testing, or public when going live.

To use Facebook Login through Socialite, you must create a Facebook App on:

🔗 https://developers.facebook.com/

This app gives you:

App ID
App Secret
Valid OAuth Redirect URLs
Permissions (like email, public_profile)

You cannot use Facebook Login without creating this app.

We get client_id, client_secret, redirect url.

'facebook' => [
    'client_id' => env('FACEBOOK_CLIENT_ID'),
    'client_secret' => env('FACEBOOK_CLIENT_SECRET'),
    'redirect' => 'https://your-app-url/login/facebook/callback',
],

Step 1: Set Up Facebook Developer Account and App
====================================================

Create a Facebook Developer Account:
Go to Facebook for Developers and sign in with your Facebook account.

Create a New App:
Click on "My Apps" and then "Add a New App".
Choose a Display Name and Contact Email for your app.


Configure Basic Settings:
After creating the app, you'll be redirected to the app dashboard.
Under "Settings" > "Basic", note down your App ID and App Secret. You'll need these for Laravel configuration.


Add Facebook Login:
In the app dashboard, go to "Products" > "+ Add a Product".

Add Facebook Login to your app.
Configure the Valid OAuth Redirect URIs under "Facebook Login" > "Settings". This should be https://your-app-url/login/facebook/callback.

For Twitter Login Steps:
===========================

Sign in to the developer account, create an App,

Fill in the required fields like App Name, Application Description, and Website URL. Callback URLs should be set to 


We get client_id, client_secret, redirect url.

'twitter' => [
    'client_id' => env('TWITTER_CLIENT_ID'),
    'client_secret' => env('TWITTER_CLIENT_SECRET'),
    'redirect' => 'https://your-app-url/login/twitter/callback',
],


TWITTER_CLIENT_ID=your-twitter-api-key
TWITTER_CLIENT_SECRET=your-twitter-api-secret
TWITTER_REDIRECT=https://your-app-url/login/twitter/callback


Laravel Observer:
==================
A Laravel Observer is used to automatically run code when a model changes takes place.

👉 When something happens to a model (create, update, delete),
👉 the observer listens and does the work.

In Laravel, an observer is a class that allows us to perform some tasks/events, such as when a model is created, updated, saved, deleted, etc. 
Example: Like when a user is created we send welcome mail to user.
send notification when a post is created
generate slug automatically
log when deleted

1. Creating an Observer
You can create an observer using the Artisan command:

php artisan make:observer ModelObserver --model=User (here 'User' is Model Name)

2. Defining Observer Methods
here's a basic observer for a User model:

<?
namespace App\Observers;

use App\Models\User;

class UserObserver
{
    public function creating(Post $post)
    {
        // Logic to execute before a Post is created
    }

    public function created(Post $post)
    {
        // Logic to execute after a Post is created
    }

    public function updating(Post $post)
    {
        // Logic to execute before a Post is updated
    }

    public function updated(Post $post)
    {
        // Logic to execute after a Post is updated
    }

       public function saving(Post $post)
    {
        // Logic to execute before a Post is saving
    }

    public function saved(Post $post)
    {
        // Logic to execute after a Post is saved
    }

    public function deleting(Post $post)
    {
        // Logic to execute before a Post is deleting
    }

    public function deleted(Post $post)
    {
        // Logic to execute after a Post is deleted
    }




}
?>

3. Registering the Observer
==============================
You need to register the observer in the AppServiceProvider or any service provider you choose. 
Open app/Providers/AppServiceProvider.php and add the observer registration in the boot method:

namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use App\Models\User;
use App\Observers\UserObserver;

class AppServiceProvider extends ServiceProvider
{
    public function boot()
    {
        User::observe(UserObserver::class);
    }
}


========================================================================================================================
Table of Contents:

Laravel Interview Questions and Answers for Freshers

1) What is Laravel?
Laravel is an open-source widely used PHP framework. The platform was intended for the development of web application by using MVC architectural pattern. Laravel is released under the MIT license.

MIT : Massachusetts Institute of Technology.

Therefore, its source code is hosted on GitHub. It is a reliable PHP framework as it follows expressive and accurate language rules.

2) What is the latest Laravel version?

The latest stable release of Laravel is version 11. It's been publicly available since March 12, 2024


📁 Laravel 11 Folder Structure (Simplified)
================================================

app/: Contains the core application code, including Controllers, Models, and other logic.
bootstrap/: Contains files that bootstrap the Laravel framework and configure autoloading.
config/: Contains configuration files for various parts of the application.
database/: Contains database-related files such as migrations, seeders, and factories.
public/: The web server's document root; contains the front controller (index.php) and public assets.
resources/: Contains assets that are compiled or processed by Laravel (such as views, language files, and frontend assets).
routes/: Contains route definitions for wer application.
storage/: Contains files generated by the framework, such as logs, cache, session files, and uploaded files.
tests/: Contains automated tests for wer application.
vendor/: Contains Composer dependencies.
.env: Environment configuration file.
artisan: Laravel's command-line interface executable.
composer.json: Defines the project dependencies.
webpack.mix.js: Configuration for Laravel Mix, which provides a fluent API for defining Webpack build steps.


Removed folders: app/Console, app/Exceptions, app/Http/Middleware.

Routes, Middlewares, and Exceptions are now registered in the bootstrap/app.php file.


In simple words:
Laravel 11 = major cleanup + new structure
Laravel 12 = smoother, optimized version of Laravel 11

Laravel 12 mainly improves:

starter kits
dependencies
developer experience
stability

No huge changes like Laravel 11 introduced.


3) Define composer. (Dependency Manager/ Package Manger)

Composer (Dependency Manager): Composer is a dependency manager for PHP that is widely used in Laravel and other PHP projects. 
It allows us to manage dependencies (download libraries and packages) required by our PHP project.

Composer manages these dependencies by downloading them into the project and autoloads them so they can be easily used in code.

It is an application-level package manager for PHP. It provides a standard format for managing PHP software dependencies and libraries.


4) What is HTTP middleware?

Laravel includes a middleware that checks whether application user is authenticated or not.

HTTP middleware is a technique for filtering HTTP requests. 


| Type                  | Where Used              | Example            |
| --------------------- | ----------------------- | ------------------ |
| **Global**            | Runs on all requests    | `VerifyCsrfToken`  |
| **Route Middleware**  | Added to specific route | `auth`, `throttle` |
| **Middleware Groups** | Apply a bunch together  | `web`, `api`       |


5) Name aggregates methods of query builder
============================================
Aggregate methods are used to calculate values from the database.

👉 They return a single value (number)

Aggregates methods of query builder are: 1) max(), 2) min(), 3) sum(), 4) avg(), and 5) count().

6) What is a Route?
====================
A route in Laravel maps a URL and HTTP method to a controller or function that handles the request.

A route is basically an endpoint specified by a URI (Uniform Resource Identifier). It acts as a pointer in Laravel application.

Most commonly, a route simply points to a method on a controller and also indictates which HTTP methods are able to hit that URI.

Route::get('/user/profile', function () {
    //
})->name('profile');


Route Groups:
==================
we can group routes that share common attributes:

Route::prefix('admin')->group(function () {

    Route::get('dashboard', function () {
        return 'Admin Dashboard';
    });

    Route::get('users', function () {
        return 'Admin Users';
    });

});

php artisan migrate:fresh
============================
🔥 What happens when you run it?

Drops all tables from the database.
Runs all migrations again from the beginning.
Creates a fresh database structure.

7) Why use Route?
==================
Using route name we navigate or access different parts of an app without the need to type the file name. 
Routing in Laravel allows users to route all their application demands to its appropriate controller. Most primary routes in Laravel acknowledge and accept a Uniform Asset Identifier together with a closure, giving  a simple and expressive way of routing.

Routes are stored inside files under the /routes folder inside the project’s root directory. By default, there are a few different files corresponding to the different “sides” of the application (“sides” comes from the hexagonal architecture methodology).

8) What do we mean by bundles/package ?
In Laravel, bundles are referred to as packages. These packages are used to increase the functionality of Laravel. A package can have views, configuration, migrations, routes, and tasks.

9) Explain important directories used in a common Laravel application.
Directories used in a common Laravel application are:

App/: This is a source folder where our application code lives. 
All controllers, policies, and models are inside this folder.


Config/: Holds the app’s configuration files. 
These are usually not modified directly but instead, rely on the values set up in the .env (environment) file at the root of the app.

Database/: Houses the database files, including migrations, seeds, and test factories.

Public/: Publicly accessible folder holding compiled assets and of course an index.php file.

10) What is a Controller?

A controller handles requests, processes data, and returns responses in a Laravel application.

A controller is the “C” in the “MVC” (Model-View-Controller) architecture, which is what Laravel is based on.

11) Explain reverse routing in Laravel. :  **********
===========================================
In Laravel, reverse routing refers to the process of generating URLs based on named routes . 

Using Reverse routing we can generate URLs based on route names.

Example:

Route::get('user/profile', function () {})->name('profile');

Using Named Routes in Redirects

Named routes are particularly useful when redirecting within application. Instead of hardcoding URLs, we can use the route names:

return redirect()->route('profile');

or 

<a href="{{route('profile')}}">Profile</a> ==== reverse routing


This can be useful  to generate URLs dynamically in  views or controllers, rather than hardcoding them



Once we have a named route, we can generate URLs to that route using the global route function:

$url = route('profile');

Use of reverse routing:
--------------------------
Ease of modification: With reverse routing, we can modify the routes in one location and Laravel will automatically update all the 
corresponding URLs throughout the application.

Cleaner code: Reverse routing makes the code cleaner and easier to read and understand. By referring to the route’s name instead of the
 actual URL, wer intentions are made clearer.

// web.php
Route::get('/profile', [UserController::class, 'profile'])->name('profile');

<a href="{{ route('profile') }}">My Profile</a>

// Change URL in one place only:

Route::get('/user/profile', [UserController::class, 'profile'])->name('profile');

Reverse routing can simplify URL management, improve maintainability, and simplify refactoring in Laravel applications.

*****************************************************************************
In PHP, multiple inheritance is not supported. ****

By using interfaces and traits, PHP provides mechanisms to achieve code reuse and modularity similar to multiple inheritance, 

Define Interface: For Code reuse similar to multiple inheritance.

=======================================================================

An interface defines what methods a class must implement, but not how those methods work.

⭐ Key Points

Interface has only method declarations, no method body
A class can implement multiple interfaces
Used to achieve abstraction

Interfaces: PHP supports interface inheritance, where a class can implement multiple interfaces. Interfaces define contracts that classes must follow by implementing specified methods. This allows classes to inherit method signatures from multiple sources without inheriting implementation details.

Ex: 

interface Interface1 {
    public function method1();
}

interface Interface2 {
    public function method2();
}

class MyClass implements Interface1, Interface2 {
    public function method1() {
        // Implementation
    }

    public function method2() {
        // Implementation
    }
}

Abstract Class:
=================
An abstract class in PHP is used to define a common structure and force child classes to follow certain rules while sharing common code.

An abstract class contains both abstract and normal methods and is used as a base class for other classes.

Abstract class can have method body.

Abstract class can have abstract methods.

Child class must implement abstract methods.


Real-Life Example: Vehicle

Think of a Vehicle.

Every vehicle can start, but the way it moves differs:

Car moves on roads.
Boat moves on water.
Airplane moves in the air.

So, we create an abstract class Vehicle with a common method and an abstract method.


Supports single inheritance.

| Feature          | **Abstract Class**                             | **Interface**                                 |
| ---------------- | ---------------------------------------------- | --------------------------------------------- |
| Methods          | Can have **abstract + normal methods**         | Only **method declarations**                  |
| Method Body      | ✅ Allowed                                     | ❌ Not allowed                               |
| Variables        | Can have properties                            | ❌ No properties                              
| Inheritance      | A class can **extend only one** abstract class | A class can **implement multiple** interfaces |
| Access Modifiers | Can use `public`, `protected`, `private`       | Methods are **public by default**             |
| Object Creation  | ❌ Cannot create object                        | ❌ Cannot create object                     |
| Purpose          | Provides **base code + rules**                 | Provides **only rules (contract)**            |
| Use Case         | When some common logic is shared               | When behavior must be enforced                |
| Keyword Used     | `extends`                                      | `implements`                                  |



12) Explain traits in Laravel. 
==============================
A trait is a reusable piece of code that you can use in many Classes.
A trait is used to reuse common functionality across multiple Classes in PHP.

Key Points
==========
Traits contain methods with body.
One class can use multiple traits.
Avoids code duplication.
Uses use keyword.


In PHP, multiple inheritance is not supported. **** Use to create reusable function.

*****In PHP, A trait is a mechanism for code reuse that allows developers to create reusable functions/methods 
that can be used in multiple classes.


Example:
========

trait LoggerTrait
{
    public function log($message)
    {
        echo $message;
    }
}

Using Trait in a Class

class User
{
    use LoggerTrait;
}


$user = new User();
$user->log('User created');



Example:
========

<?php

trait Hello {
    public function sayHello() {
        echo 'Hello';
    }
}

// Define a class that uses the trait
Class Greeting {

    use Hello;
    public function greet($name) {
        $this->sayHello();
        echo $name;
    }

}

// Create an instance of the class and call the method
$obj = new Greeting();
$obj->greet('Alex'); // Outputs: Hello Alex

?>


13) Explain the concept of contracts in Laravel.

In Laravel, Contracts are like interfaces in PHP.

A contract defines what a class should do, but not how it does it.
Contract = collection of required functions

Simple Example
Think of a remote control:

The remote has buttons like powerOn()
It does not care how the TV turns on internally

That button definition is like a contract.

In Laravel
Laravel uses contracts to define services such as:

Authentication
Caching
Queue
Mail

Example contract:

Encryption vs Hashing (Key Difference)
===========================================
🔐 Encryption

Reversible (you can decrypt the data)
Used when you need the original value later

Use encryption when:

Storing API keys
Credit card tokens (not raw cards)
Sensitive user data (SSN, PAN, secrets)

Laravel example:

use Illuminate\Support\Facades\Crypt;

$encrypted = Crypt::encryptString('secret');
$decrypted = Crypt::decryptString($encrypted);

🔑 Hashing
==============
Hashing is a one-way process:
Converts data into a fixed-length string
Cannot be reversed

Used to verify, not retrieve data
Use hashing when:

Passwords

OTP verification

Tokens you only need to compare

Laravel example:

use Illuminate\Support\Facades\Hash;

$hash = Hash::make('password');

Hash::check('password', $hash); // true

Bcrypt (Specific Hashing Algorithm)
===================================
Bcrypt is a secure password hashing algorithm designed specifically for passwords.
Laravel uses bcrypt by default for passwords.

$password = bcrypt('mypassword');

OR,
use Illuminate\Support\Facades\Hash;
Hash::make('mypassword');

| bcrypt()      | Hash::make()           |
| ------------- | ---------------------- |
| Direct helper | Laravel facade         |
| Only bcrypt   | Uses configured driver |
| Less flexible | Recommended by Laravel |
| Older style   | Modern/preferred style |


Why Use bcrypt?

It helps protect passwords if the database is hacked.

Why bcrypt is special

✔ Automatically adds salt.
✔ Slow by design (prevents brute-force attacks).
✔ Adjustable cost factor.
✔ Resistant to rainbow-table attacks.

use Illuminate\Support\Facades\Hash;

User::create([
    'name' => $request->name,
    'email' => $request->email,
    'password' => Hash::make($request->password),
]);


Password check using Hash::check()
=======================================
use Illuminate\Support\Facades\Hash;


if (Hash::check($request->password, $user->password)) {
    // login success
} else {
    // wrong password
}


use Illuminate\Support\Facades\Hash;
Hash::make('password'); // uses bcrypt by default

14) How will we register service providers? ****** config/app.php file inside 'providers' array 
================================================================================================
A Service Provider is where you register services in the container.

Service Provider = Where you register services.
Service Container = Where Laravel stores and resolves those services.

Use to add extra feature to our application.
Service providers are the central place to configure web application.***

Exampale: Auth,Encryption,Password,Cache,Cookie,Session,Validation,Database,Mail.

Service providers are the central place to configure web application.***

In Laravel, service providers are an essential part of the framework's architecture. They bootstrap various services within the application, such as registering bindings in the service container, defining routes, or configuring other aspects of the framework.

We can register service providers in the config/app.php configuration file that contains providers array where we can mention the service provider class name.

php artisan make:provider RiakServiceProvider

Exampale: Auth, Encryption, Password, Cache,Cookie,Session,Validation, Database, Mail


'providers' => [

        /*
         * Laravel Framework Service Providers...
         */
        Illuminate\Auth\AuthServiceProvider::class, 
        Illuminate\Encryption\EncryptionServiceProvider::class,
        Illuminate\Cache\CacheServiceProvider::class,
        Illuminate\Auth\Passwords\PasswordResetServiceProvider::class,
        Illuminate\Session\SessionServiceProvider::class,
        Illuminate\Translation\TranslationServiceProvider::class,
        Illuminate\Validation\ValidationServiceProvider::class,
        Illuminate\Cache\CacheServiceProvider::class,


        Illuminate\Broadcasting\BroadcastServiceProvider::class,
        Illuminate\Bus\BusServiceProvider::class,
       
        Illuminate\Foundation\Providers\ConsoleSupportServiceProvider::class,
        Illuminate\Cookie\CookieServiceProvider::class,
        Illuminate\Database\DatabaseServiceProvider::class,
        Illuminate\Encryption\EncryptionServiceProvider::class,
        Illuminate\Filesystem\FilesystemServiceProvider::class,
        Illuminate\Foundation\Providers\FoundationServiceProvider::class,
        Illuminate\Hashing\HashServiceProvider::class,
        Illuminate\Mail\MailServiceProvider::class,
        Illuminate\Notifications\NotificationServiceProvider::class,
        Illuminate\Pagination\PaginationServiceProvider::class,
        Illuminate\Pipeline\PipelineServiceProvider::class,
        Illuminate\Queue\QueueServiceProvider::class,
        Illuminate\Redis\RedisServiceProvider::class,
   
        Illuminate\View\ViewServiceProvider::class,

        /*
         * Package Service Providers...
         */

        /*
         * Application Service Providers...
         */
        App\Providers\AppServiceProvider::class,
        App\Providers\AuthServiceProvider::class,
        // App\Providers\BroadcastServiceProvider::class,
        App\Providers\EventServiceProvider::class,
        App\Providers\RouteServiceProvider::class,

    ],



15) Where will we define Laravel’s Facades?

**** Facades  provides static interface of the classes.We can access object from the application's service container.

In a Laravel application, a facade is a class that provides access to an object from the application's service container.****
They serve as a convenient way to access Laravel services without injecting them into the classes manually.

All facades of Laravel have defined in Illuminate\Support\Facades namespace.

All of Laravel's facades are defined in the Illuminate\Support\Facades namespace. So, we can easily access a facade like so:

use Illuminate\Support\Facades\Cache;
use Illuminate\Support\Facades\Route;
use DB;


🔹 Common Facades Examples
==========================
Route::get('/', function () {
    return 'Hello';
});


Cache::put('key', 'value');
Log::info('User logged in');
Auth::user();
DB::table('users')->get();


 
Examples:
=========
Let’s take an example using the Cache facade in Laravel:


use Illuminate\Support\Facades\Cache;
use DB;


// Using the facade to store a value in the cache
Cache::put('key', 'value', $minutes);

// Retrieving a value from the cache
$value = Cache::get('key');

In Laravel, DB is a built-in Facade that provides a static interface to Laravel's database operations. 
It allows us to interact with the database without needing to instantiate and manage database connections manually.

Example:
========
use Illuminate\Support\Facades\DB;

// Using the DB facade to insert data into a table
DB::table('users')->insert([
    'name' => 'John Doe',
    'email' => 'john@example.com',
    'password' => bcrypt('secret'),
]);

| Facade      | Purpose              |
| ----------- | -------------------- |
| **DB**      | Database queries     |
| **Cache**   | Cache data           |
| **Cookie**  | Set & get cookies    |
| **Auth**    | Authentication       |
| **Route**   | Define routes        |
| **Log**     | Write logs           |
| **Session** | Session handling     |
| **Mail**    | Send emails          |
| **Config**  | Access config values |


16) State the difference between get and post method.

The GET and POST methods are two primary HTTP methods used for sending data from a client (such as a web browser) to a server and vice versa.

When using GET, the data is appended to the URL as a query string. For example, http://example.com/resource?id=123&name=John.

Get : Typically used for requesting data from a server. For example, fetching a web page, an image, or other resources.

Get method allows us to send a limited amount of data in the header. 

Post: allows us to send a large amount of data in the body.

Post : Commonly used for submitting form data, uploading files, or any request where the action may change the state on the server.

get send data in url.

post send data in the body.

17) List default packages of Laravel.

Authentication,Routing,Middleware,Eloquent ORM,Blade Templating Engine,Database Migrations and Seeds.

Default packages of Laravel 5.6 are: 1) Envoy, 2) Passport, 3) Socialite, 4) Cashier, 5) Horizon, and 6) Scout.

Here's a list of some of the key default packages included in a fresh Laravel installation:

Laravel/Framework
The core package of Laravel that provides the base functionality of the framework (Authentication,Routing,Middleware,Eloquent ORM,Blade Templating Engine,Database Migrations and Seeds).

Illuminate (various sub-packages)
Laravel's core components are organized under the Illuminate namespace, including:

Illuminate/Auth - Authentication services.
Illuminate/Cache - Caching services.
Illuminate/Database - Database support, including Eloquent ORM and query builder.
Illuminate/Encryption - Encryption utilities.
Illuminate/Filesystem - File system abstraction.
Illuminate/Notifications - Notification system.
Illuminate/Session - Session management.
Illuminate/Validation - Form validation.
Illuminate/View - View handling (Blade templates).
Illuminate/Mail - Mail services.
Illuminate/Queue - Queue management.
Illuminate/Bus - Command bus.
Illuminate/Logging - Logging functionality.
Laravel/Passport

A package for API authentication using OAuth2, typically used for securing APIs in Laravel.

Laravel/Sanctum
A simpler alternative to Passport, designed for token-based authentication in SPAs (Single Page Applications) or simple API usage.

Laravel/Dusk
Browser automation and testing package that provides an expressive syntax for end-to-end testing of web applications using a real browser.

Laravel/Tinker
A REPL (Read-Eval-Print Loop) for interacting with your Laravel application's codebase via the command line.

Laravel/Scout
Provides full-text search capabilities for Eloquent models using drivers like Algolia.

Laravel/Envoyer
A deployment tool for zero-downtime deployments for Laravel applications (requires a subscription).

Laravel/UI
Provides basic scaffolding for user authentication (login, registration) and front-end framework integrations (Bootstrap, Vue.js, etc.).

FakerPHP/Faker
A package for generating fake data (e.g., names, addresses, text) commonly used in seeding and testing.

GuzzleHTTP/Guzzle
A PHP HTTP client that simplifies sending HTTP requests and handling responses, commonly used for making external API calls.

Symfony Components
Laravel uses several Symfony components as part of its core, such as:

Symfony/Console - Command-line interface (CLI) components.

Symfony/HttpFoundation - HTTP-related functionality (requests, responses, etc.).

Symfony/Routing - URL routing.

NunoMaduro/Collision
A package that provides error handling and user-friendly exception reporting, designed to improve the developer's experience.
These packages are generally included in a fresh Laravel installation and can be extended or removed based on your application's requirements. Many of these packages are integral to Laravel's philosophy of providing a robust, developer-friendly, and full-featured framework.

| Method       | Used For       |
| ------------ | -------------- |
| Session Auth | Websites       |
| Token Auth   | APIs           |
| Sanctum      | Simple API/SPA |
| Passport     | OAuth2 APIs    |
| Socialite    | Social login   |



18) What is service container in Laravel?
Service container is a tool used for performing dependency injection in Laravel.

19) How can we enable query log in Laravel?
we can use enableQueryLog method to enable query log in Laravel.

public function index()
{
    DB::enableQueryLog();

    $arr_user = DB::table('users')->select('name', 'email as user_email')->get();
    // same will work for Eloquent
    // $u = User::find(1);

    dd(DB::getQueryLog());
}



20) Explain the concept of events in Laravel.

Events are used to say:
In Laravel, Events are used to perform actions when something happens in the application.

“When an event happens → run some code automatically.”

Real Life Example

User registers
Send welcome email
Notify admin
Log activity

21) Explain dependency injection and their types.

In Laravel, dependency injection allows us to inject dependencies (like services, classes, or objects) directly into the constructor or 
method of a class, rather than having to manually create instances of these dependencies.

Laravel provides a powerful service container that manages class dependencies and performs dependency injection automatically. 
This makes it very easy to swap, mock, or replace services as needed.

It is a technique in which one object is dependent on another object. 

There are three types of dependency injection: 1) Constructor injection, 2) setter injection, and 3) interface injection.

22) What are the advantages of using Laravel?
==================================================

Here are important benefits of Laravel:

Laravel has blade template engine to create dynamic lawets and increase compiling tasks.
Reuse code without any hassle.
Laravel provides we to enforce constraints between multiple DBM objects by using an advanced query builder mechanism.
The framework has an auto-loading feature, so we don’t do manual maintenance and inclusion paths.
The framework helps us to make new tools by using LOC container.
Laravel offers a version control system that helps with simplified management of migrations.


Composer :

Laravel utilizes Composer, a PHP dependency manager, to package and manage dependencies at the project level. This modular approach allows developers to easily add or remove components, ensuring a lightweight and efficient project structure.

Eloquent ORM (Object-Relational Mapping):

Eloquent provides a simple ActiveRecord implementation for working with our database. It allows developers to interact with databases using PHP objects, reducing the need for SQL queries and making database interactions more intuitive and efficient.

MVC Architecture Support:

Laravel follows the MVC (Model-View-Controller) architectural pattern out of the box. This separation of concerns makes it easier to manage complex applications, improve code organization, and facilitate better scalability.


Blade Templating Engine:

Laravel's Blade templating engine offers a powerful and straightforward syntax for creating views. It includes features like template inheritance, sections, and lawets, which streamline the process of designing lawets and managing reusable content.

Routing System:

Laravel provides a simple and expressive routing system that allows developers to define routes using a concise syntax. Named routes, middleware, and route parameter binding are among the many features that make Laravel's routing system flexible and powerful.

Artisan CLI (Command-Line Interface):

Laravel includes a command-line interface called Artisan, which provides a range of helpful commands for automating repetitive tasks. Developers can use Artisan to generate code, run migrations, clear caches, and perform other routine operations, boosting productivity.

Authentication and Authorization:

Laravel makes implementing authentication and authorization mechanisms a breeze. It includes pre-built authentication scaffolding that can be easily customized to fit the needs of wer application. Laravel also provides fine-grained access control through its middleware and policies.

Community and Ecosystem:

Laravel has a vibrant and active community of developers who contribute packages, tutorials, and resources. This ecosystem ensures ongoing support, frequent updates, and a wealth of third-party integrations that extend Laravel's capabilities.

Security Features:

Laravel takes security seriously and includes built-in features such as CSRF (Cross-Site Request Forgery) protection, XSS (Cross-Site Scripting) protection, secure authentication mechanisms, and encryption. These features help developers build secure applications by default.

Integration with Queues and Scheduler:

Laravel provides robust support for handling asynchronous tasks and scheduled jobs through its built-in queue and task scheduler mechanisms. This allows developers to offload time-consuming tasks to the background, improving application responsiveness and scalability.



23) Explain validation concept in Laravel.

Validations are an important concept while designing any Laravel application. It ensures that the data is always in an expected format before it stores into the database. Laravel provides many ways to validate our data.

Base controller trait uses a ValidatesRequests class which provides a useful method to validate requests coming from the client machine.

24) What does ORM stand for? : Object Relationship Mapping ***
================================================================
ORM stands for Object Relational Mapping

Eloquent lets you work with database tables using PHP classes instead of writing SQL queries manually.

Each model corresponds to a single table, and interaction with the table (like querying or updating data) is done through the model.

Example: If we have a User model, it typically maps to a users table in our database.

One-to-One: A User has one Profile.
One-to-Many: A User has many Posts.
Many-to-Many: Users belong to many Roles.


25) How can we reduce memory usage in Laravel?
While processing a large amount of data, we can use the cursor method in order to reduce memory usage.

Laravel Interview Questions and Answers for 2 & 3 Years Experience.

26) List available types of relationships in Laravel Eloquent.
Types of relationship in Laravel Eloquent are: 1) One To One 2) One To Many 3) Many To Many 4) Has Many Through, and 5) Polymorphic Relations.

27) Name the Template Engine utilized by Laravel.

Blade is a powerful template engine utilized by Laravel.

28) Name databases supported by Laravel.

Laravel supports the following databases:

SQLite
MySQL
SQL Server
PostgreSQL


29) Why are migrations important? ==> To maintain database, create, update tables. 

Laravel migrations are a powerful feature that allows us to manage database schema (create,update database schema) using PHP code rather 
than SQL.

Migrations are important because it allows us to share application by maintaining database consistency. Without migration, it is 
difficult to share any Laravel application. It also allows us to sync database.

To create a new migration, we use the php artisan make:migration command followed by the name of the migration. 

For example, to create a migration for a users table:

php artisan make:migration create_users_table

This command will create a new migration file in the database/migrations directory.

Each migration file contains two main methods: up() and down(). 

The up() method is used to define the changes we want to make to the database.

while the down() method specifies how to undo/revert back those changes (i.e., rollback).

Example:
==========
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

class CreateUsersTable extends Migration
{
    public function up()
    {
        Schema::create('users', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->string('email')->unique();
            $table->timestamps();
        });
    }

    public function down()
    {
        Schema::dropIfExists('users');
    }
}

To execute all pending migrations and update user database schema, run the migrate Artisan command:

php artisan migrate

If we need to undo the last migration operation, we can use the rollback command:

php artisan migrate:rollback

To rollback all migrations and reset the database, use:

php artisan migrate:reset

Seed Database After Migration: 

we can seed our database with test data after running migrations using command

 php artisan migrate --seed.

30) Define Lumen  
Lumen is a micro-framework. It is a smaller, and faster, version of a building Laravel based services, and REST API’s.

31) Explain PHP artisan
An artisan is a command-line tool of Laravel. It provides commands that help us to build Laravel application without any hassle.

32) How can we generate URLs?
Laravel has helpers to generate URLs. This is helpful when we build link in our templates and API response.

33) Which class is used to handle exceptions?
Laravel exceptions are handled by App\Exceptions\Handler class.

34) What are common HTTP error codes?

The most common HTTP error codes are:

4xx - Client Errors
These errors indicate that the client (e.g., web browser or app) made a bad request.

400 Bad Request
The server cannot process the request due to malformed syntax or invalid request parameters.

401 Unauthorized
The request requires user authentication. The client must provide valid credentials (e.g., login details).

403 Forbidden
The server understood the request, but the client does not have permission to access the requested resource.

404 Not Found
The server cannot find the requested resource. This is one of the most common errors when a URL is misspelled or the page doesn't exist.

405 Method Not Allowed
The method used in the request (like GET, POST, PUT) is not allowed for the requested resource.

408 Request Timeout
The server timed out while waiting for the request from the client.

429 Too Many Requests
The client has sent too many requests in a given amount of time, typically due to rate limiting.

5xx - Server Errors
These errors indicate that the server failed to fulfill a valid request.

500 Internal Server Error
A generic error indicating that the server encountered an unexpected condition that prevented it from fulfilling the request.

502 Bad Gateway
The server, while acting as a gateway or proxy, received an invalid response from an upstream server.

503 Service Unavailable
The server is currently unable to handle the request due to temporary overloading or maintenance of the server.

504 Gateway Timeout
The server, while acting as a gateway or proxy, did not receive a timely response from an upstream server.

505 HTTP Version Not Supported
The server does not support the HTTP protocol version used in the request.

35) Explain fluent query builder in Laravel.
It is a database query builder that provides convenient, faster interface to create and run database queries.

36) What is the use of dd() "Dump and Die" function? *****

This function is used to dump contents of a variable to the browser. The full form of dd is Dump and Die.
After dumping the variables, dd() stops the execution of further code. 

We can use dd() to dump variables, arrays, objects, or any other type of data:


$name = 'John Doe';
dd($name);

output : John Doe

$array = ['apple', 'orange', 'banana'];
dd($array);

output :
array:3 [
  0 => "apple"
  1 => "orange"
  2 => "banana"
]

37) List out common artisan commands used in Laravel.

Laravel supports following artisan commands:

PHP artisan down;
PHP artisan up;
PHP artisan make:controller;
PHP artisan make:model;
PHP artisan make:migration;
PHP artisan make:middleware;


38) How to configure a mail-in Laravel?
The default email sending package in Laravel is the Mail package. In config/mail.php the configuration file includes.

The default email sending package in Laravel is the Mail package, which supports various drivers like SMTP, Mailgun, and Postmark. You 
can easily configure the mail service in the config/mail.php file and send emails with simple, intuitive code using the Mail facade.

39) Explain Auth.
It is a method of identifying user login credential with a password. In Laravel it can be managed with a session which takes two parameters 
1) username and 2) password.

40) Differentiate between delete() and softDeletes(). *******

delete(): Permanently removes the record from the database.

softDeletes(): Marks the record as deleted by setting a timestamp (deleted_at) but does not physically remove it from the database.

41) How can we make real time sitemap.xml file in Laravel? ******

A sitemap.xml file lists all the URLs of website in a structured format. It helps search engines navigate through the site.
thereby potentially improving our site's visibility and accessibility in search engine results pages (SERPs).

Search engine crawlers use sitemaps to discover and prioritize content on website. This is particularly useful for new websites or 
websites with a large number of pages, ensuring that all pages are indexed promptly.

we can create all web pages of a website to tell the search engine about the organizing site content. The crawlers of search engine read 
this file intelligently to crawl a website.

42) Explain faker in Laravel.
It is a type of module or packages which are used to create fake data. This data can be used for testing purpose.

It is can also be used to generate: 1) Numbers, 2) Addresses, 3) DateTime, 4) Payments, and 5) Lorem text.

43) How will we check table is exists or in the database?
Use hasTable() Laravel function to check the desired table is exists in the database or not.

44) What is the significant difference between insert() and insertGetId() function in Laravel?

Insert(): This function is simply used to insert a record into the database. It not necessary that ID should be autoincremented.

InsertGetId(): This function also inserts a record into the table, but it is used when the ID field is auto-increment.

45) Explain active record concept in Laravel.

Each database table has a corresponding "Model" in Laravel to interact with database.It helps us to deal with CRUD operation.

In active record, class map to the database table. It helps we to deal with CRUD operation.

46) List basic concepts in Laravel?
Following are basic concepts used in Laravel:

Routing
Eloquent ORM
Middleware
Security
Caching
Blade Templating


47) Define Implicit Controller.
Implicit Controllers help we to define a proper route to handle controller action. 
we can define them in route.php file with Route:: controller() method.

48) How to use the custom table in Laravel Model?

In order to use a custom table, we can override the property of the protected variable $table.

49) What is MVC framework?

It is Model, View, and Controller:

Model: Model defines logic to write Laravel application.

View: It covers UI logic of Laravel application.

Controller: It is work as an interface between Model, and View. It is a way how the user interacts with an application.

HMVC Hierarchical Structure:
==============================
Each module has its own MVC 

 HMVC allows us to organize our application into smaller, reusable modules or packages. Each module typically has its own MVC triad (Model, View, Controller), 

50) Define @include.

@include is used to load more than one template view files. It helps us to include view within another view. 
User can also load multiple files in one view.


51) Explain the concept of cookies.
Cookies are small file sent from a particular website and stored on PC by user’s browser while the user is browsing.

52) Which file is used to create a connection with the database?
To create a connection with the database, we can use .env file.

53) What is Eloquent?


54) Name some Inbuilt Authentication Controllers of Laravel.
Laravel installation has an inbuilt set of common authentication controllers. These controllers are:

RegisterController
LoginController
ResetPasswordController
ForgetPasswordController

55) Define Laravel guard.

Laravel guard is a special component that is used to find authenticated users. The incoming requested is initially routed through this 
guard to validate credentials entered by users.

56) What is Laravel API rate limit? => No of Api request within time interval.

In Laravel, throttling refers to limiting the number of attempts or requests that can be made to certain routes or parts of our 
application within a specified period of time.


we can apply throttling to routes using middleware. Laravel provides a built-in throttle middleware that we can use to specify the
maximum number of requests allowed and the time frame (in minutes) during which these requests are counted.

Example:

Route::middleware('throttle:rate_limit,rate_limit_interval')->group(function () {
    // wer routes here
});


Route::middleware('throttle:api')->group(function () {
    Route::get('/profile', 'UserController@profile');
});

we can customize the throttle middleware in app/Http/Kernel.php by adding or modifying the throttle middleware:


protected $middlewareGroups = [
    'api' => [
        'throttle:60,1', // 60 requests per minute
        'auth:api',
    ],
];

57) Explain collections in Laravel ===> provide a fluent, convenient way of working with arrays of data. 

In Laravel, collections are a powerful feature provided by the Illuminate\Support\Collection class, which extends PHP's built-in array functions to provide a fluent, convenient way of working with arrays of data. 

Collections is a wrapper class to work with arrays. Laravel Eloquent queries use a set of the most common functions to return database result.

58) What is the use of DB facade?

In Laravel, facades provide a static interface to classes that are available in the service container.

DB facade is used to run SQL queries like create, select, update, insert, and delete.

we can execute raw SQL queries using the DB::select, DB::insert, DB::update, and DB::delete methods. For example:

Example:
============
use Illuminate\Support\Facades\DB;

// Selecting data
$users = DB::select('SELECT * FROM users');

// Inserting data
DB::insert('INSERT INTO users (name, email) VALUES (?, ?)', ['John Doe', 'john.doe@example.com']);

// Updating data
DB::update('UPDATE users SET name = ? WHERE id = ?', ['Jane Doe', 1]);



59) What is the use of Object Relational Mapping?

Object Relational Mapping is a technique that helps developers to address, access, and manipulate objects without considering the relation between object and their data sources.

60) Explain the concept of routing in Laravel.

It allows routing all the application requests to the controller. 
Laravel routing acknowledges and accepts a Uniform Resource Identifier with a closure.

61) What is Ajax in Laravel?

Ajax stands for Asynchronous JavaScript and XML is a web development technique that is used to create asynchronous Web applications. In Laravel, response() and json() functions are used to create asynchronous web applications.

62) What is a session in Laravel?

Session is used to pass user information from one web page to another. Laravel provides various drivers like a cookie, array, file, Memcached, and Redis to handle session data.

63) How to access session data?
Session data be access by creating an instance of the session in HTTP request. Once we get the instance, use get() method with a “Key” as a parameter to get the session details.


// Using Session facade
use Illuminate\Support\Facades\Session;

Session::put('key', 'value');

// Using Session facade
$value = Session::get('key');


// Check if session key exists or not
if (Session::has('key')) {
    // Key exists in the session
}

64) State the difference between authentication and authorization.

Authentication : is the process of verifying the identity of a user or system.

Example:
Username and password: Most typical for user login.


while authorization refers to gathering access to the system.

Authorization: (After login what user is able to access )
Authorization, on the other hand, determines what a user or system is allowed to do after successful authentication. It answers the question, "What are we allowed to do?" Authorization involves granting or denying access to resources or functionalities based on the authenticated user's identity and their permissions or roles.

65) Explain to listeners.
Listeners are used to handling events and exceptions. The most common listener in Laravel for login event is LoginListener.

66) What are policies classes?
Policies classes include authorization logic of Laravel application. These classes are used for a particular model or resource.

67) How to rollback last migration?

Use need to use artisan command to rollback the last migration.

php artisan migrate:rollback

If we have multiple migration batches and we want to rollback more than one step, we can specify the number of steps to rollback:

php artisan migrate:rollback --step=2


68) What do we mean by Laravel Dusk?
Laravel Dusk is a tool which is used for testing JavaScript enabled applications. It provides powerful, browser automation, and testing API.

69) Explain Laravel echo.
It is a JavaScript library that makes possible to subscribe and listen to channels Laravel events. we can use NPM package manager to install echo.

70) What is make method?

Laravel developers can use make method to bind an interface to concreate class. This method returns an instance of the class or interface. Laravel automatically inject dependencies defined in class constructor.

71) Explain Response in Laravel.

All controllers and routes should return a response to be sent back to the web browser. Laravel provides various ways to return this 
response. 
The most basic response is returning a string from controller or route.

1. String Response
2. View Response
3. JSON Response
4. Redirect Response


72) What is query scope?
It is a feature of Laravel where we can reuse similar queries. We do not require to write the same types of queries again in the Laravel project. Once the scope is defined, just call the scope method when querying the model.

73) Explain homestead in Laravel.

Laravel homestead is the official, disposable, and pre-packaged vagrant box that a powerful development environment without installing HHVM, a web server, and PHP on wer computer.

74) What is namespace in Laravel?

In Laravel (and PHP), a namespace is mainly used to avoid name conflicts between classes.

75) What is Laravel Forge?

Laravel Forge helps in organizing and designing a web application. Although the manufacturers of the Laravel framework developed this 
toll, it can automate the deployment of every web application that works on a PHP server.




Laravel Interview Questions and Answers for 10+ Years Experience
==================================================================
76) State the difference between CodeIgniter and Laravel.

Parameter 

CodeIgniter Laravel
Support of ORM  CodeIgniter does not support Object-relational mapping.      Laravel supports ORM.
Provide Authentication  It does provide user authentication.               It has inbuilt user authentication.
Programming Paradigm  It is component-oriented.                              It is object-oriented.
Support of other Database Management System It supports Microsoft SQL Server, ORACLE, MYSQL, IBM DB2, PostgreSQL, JDBC, and orientDB compatible.      It supports PostgreSQL, MySQL, MongoDB, and Microsoft BI, but CodeIgniter additionally supports other databases like Microsoft SQL Server, DB2, Oracle, etc.
HTTPS Support CodeIgniter partially support HTTPS. Therefore, programmers can use the URL to secure the data transmission process by creating PATS. Laravel supports custom HTTPS routes. The programmers can create a specific URL for HTTPS route they have defined.


77) What is an Observer?

In Laravel, an observer is a class that allows you to listen for Eloquent events, such as when a model is created, updated, deleted, etc. 



78) What is the use of the bootstrap directory? *******
It is used to initialize a Laravel project. This bootstrap directory contains app.php file that is responsible for bootstrapping the framework.

79) What is the default session timeout duration? *****
The default Laravel session timeout duration is 2 hours.

80) How to remove a complied class file?
Use clear-compiled command to remove the compiled class file.

81) In which folder robot.txt is placed? ****
Robot.txt file is placed in Public directory.

82) Explain API.PHP route.
Its routes correspond to an API cluster. It has API middleware which is enabled by default in Laravel. These routes do not have any state and cross-request memory or have no sessions.

83) What is named route?
Name route is a method generating routing path. The chaining of these routes can be selected by applying the name method onto the description of route.

84) what is open source software?
Open-source software is a software which source code is freely available. The source code can be shared and modified according to the user requirement.

85) Explain Loggin in Laravel.
It is a technique in which system log generated errors. Loggin is helpful to increase the reliability of the system. Laravel supports various logging modes like syslog, daily, single, and error log modes.

86) What is Localization?
It is a feature of Laravel that supports various language to be used in the application. A developer can store strings of different languages in a file, and these files are stored at resources/views folder. Developers should create a separate folder for each supported language.

87) Define hashing in Laravel.
It is the method of converting text into a key that shows the original text. Laravel uses the Hash facade to store the password securely in a hashed manner.

88) Explain the concept of encryption and decryption in Laravel.
It is a process of transforming any message using some algorithms in such way that the third user cannot read information. Encryption is quite helpful to protect wer sensitive information from an intruder.

Encryption is performed using a Cryptography process. The message which is to be encrypted called as a plain message. The message obtained after the encryption is referred to as cipher message. When we convert cipher text to plain text or message, this process is called as decryption.

89) How to share data with views?
To pass data to all views in Laravel use method called share(). This method takes two arguments, key, and value.

Generally, share() method are called from boot method of Laravel application service provider. A developer can use any service provider, AppServiceProvider, or our own service provider.

90) Explain web.php route.

Web.php is the public-facing “browser” based route. This route is the most common and is what gets hit by the web browser. They run through the web middleware group and also contain facilities for CSRF protection (which helps defend against form-based malicious attacks and hacks) and generally contain a degree of “state” (by this I mean they utilize sessions).

91) How to generate a request in Laravel?
Use the following artisan command in Laravel to generate request:

php artisan make:request UploadFileRequest
These interview questions will also help in wer viva(orals)

we Might Like:
PHP Registration Form using GET, POST Methods with Example
PHP Session & PHP Cookies with Example
PHP File() Handling & Functions
PHP Tutorial for Beginners: Learn in 7 Days
CakePHP Tutorial for Beginners: What is CakePHP Framework?
Post navigation
Report a Bug
Prev
Next




Top Tutorials

About
About Us
Advertise with Us
Write For Us
Contact Us
Python
Testing
Hacking
Career Suggestion
SAP Career Suggestion Tool
Software Testing as a Career

Interesting
eBook
Blog
Quiz
SAP eBook
SAP
Java
SQL
Execute online
Execute Java Online
Execute Javascript
Execute HTML
Execute Python
Selenium
Build Website
VPNs

© Copyright - Guru99 2023         Privacy Policy  |  Affiliate Disclaimer  |  ToS


