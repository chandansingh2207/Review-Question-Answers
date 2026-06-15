1.Context window
2.sql injection
3.Token & tokenizaton
4.Model parameters in ai




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

================================
Macrotask vs Microtask

Index + B Tree in mYsql 

AWS Services

Dockerfile vs Docker composer yml


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

## 5. What are Microservices, Monolith (Macro Service), and Queues?

### Monolith (Macro Service)

Everything is inside one application.

Example:


E-commerce App
 ├── Login
 ├── Products
 ├── Orders
 └── Payments


Single codebase.

### Microservices

Microservices is a software architecture where a large application is divided into many small, independent services, and each service performs a specific business function.

User Service
Product Service
Order Service
Payment Service

Advantages:
* Independent deployment
* Easy scaling
* Better maintainability

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

Context is the information the AI uses to understand your request and generate a relevant response.

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

An LLM has two different kinds of "memory":

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



=================================
VectorDB all concept,when to use vector db,when use ,Mysql.
Ai Inference
MCP all concept
Langchain All concept 
what is prompt.how to write good prompt?
how prompt works.
Semantic search.Similarity search
Chunks
Vector database, Mysql dtabase pros and cons.
AI Overlapping.


=====================



What is AI?
====================

**Interview Question:** What is AI?

**Simple Answer:**
AI (Artificial Intelligence) is technology that enables computers to perform tasks that normally require human intelligence, such as understanding language, recognizing images, making decisions, and answering questions.

**Example:**

* PHP application calculates tax using fixed rules.
* AI application can analyze customer behavior and recommend products automatically.

What is Regression? (Simple)

Regression is a machine learning technique used to predict a continuous numerical value.

Real-World Examples
Predict house prices
Predict employee salaries
Predict stock prices
Predict temperature
Predict sales revenue


How does a Prompt/ChatGpt work?
================================
A prompt is converted into tokens and combined with the conversation context. The AI model processes these tokens through a neural network and predicts the most likely next tokens to generate a response. Better prompts provide clearer context, which helps the model produce more accurate and relevant answers.


Prompt
   ↓
Tokenization
   ↓
Context (prompt + chat history)
   ↓
Transformer Model
   ↓
   ┌──────────────────────────┐
   │  Attention Mechanism     │
   │  (focus on important words) │
   └──────────────────────────┘
   ↓
Neural Network Layers
   ↓
Next-token prediction
   ↓
Repeat many times
   ↓
Final Answer

⭐ Super simple summary:
=========================
Tokens = input pieces
Attention = focus on important words
Transformer = brain structure
Prediction = output generation


Transformer
=============
A Transformer is a type of neural network architecture designed to understand relationships between words (or tokens) in a sequence. 
It was introduced in the 2017 paper "Attention Is All You Need" and is the foundation of most modern large language models.

Key facts
Published: June 2017 (NeurIPS proceedings)

Authors: Ashish Vaswani et al. (Google Brain, University of Toronto)


Simple analogy

Imagine you're reading a paragraph and trying to understand the meaning of a sentence.

Instead of reading one word at a time and trying to remember everything, you can:

Look at all the words in the sentence at once.
Focus on the words that are most relevant to the current word.
Build an understanding of the overall context.

That's essentially what a Transformer does.


What is Chain of Thought?
==========================
Breaking a problem into steps.

One-line memory trick:
===========================
Parameter = everything AI learns
Weight = importance inside that learning

What is a Parameter?
========================
A parameter is a value that the AI learns during training.

Most parameters in neural networks are weights.

So you can think:
Parameters = All Learned Values

Simple Analogy
Imagine a student preparing for exams.

During study:

Math = Very Important
Science = Important
History = Less Important

Why Do People Say
===================
"7 Billion Parameters"

Example:

Llama 3

8 Billion Parameters

means:

8 Billion Learned Numbers

stored inside the model.

What is a Weight? = Importance Score
====================================
A weight is just a number in an AI model that tells it how strong or important a connection is.

A weight is a number inside a neural network that tells AI how important something is.

Think of it like:

Weight = Importance Score

Weight
= Importance Score

Parameter
= Any Learned Value in the Model

Human Example
==============
Suppose you want to predict whether a person will get a job.

Factors:
Experience
Skills
Education

Not all factors have equal importance.

Example:
Experience = 80%
Skills = 70%
Education = 30%

These importance values are similar to weights.



Attention:
=============
Attention = a method for deciding which parts of input matter most for understanding or prediction.

Attention means: “focus more on important words and less on unimportant ones.”

In AI, attention is a mechanism that allows a model to focus on the most relevant parts of its input when making a prediction.

Think of it like reading a sentence:

"The cat sat on the mat because it was soft."

To understand what "it" refers to, you pay more attention to "the mat" than to other words. Attention lets AI models do something similar.


What is Overfitting?
======================
Overfitting happens when a model memorizes training data and performs poorly on new data.

What is Underfitting?
======================
Underfitting happens when the model is too simple and fails to learn the patterns in the data.

Example
A student studies only one page for an exam.

What is Noise in AI?
=====================
Answer:
"Noise is unwanted, incorrect, irrelevant, or misleading data that negatively affects model performance and prediction accuracy."

How Do You Reduce Noise?
=========================

Answer:
"We reduce noise through data cleaning, removing duplicates, correcting labels, handling missing values, selecting relevant features, and maintaining high-quality datasets."


Formula for a Good Prompt
============================
Role-Task-Context-Constraints-Output Format

Example
Role:
You are a senior Laravel developer.

Task:
Create a Laravel 11 REST API
for customer management.

Context:
Use MySQL.

Constraints:
Include validation.
Use service classes.

Output Format:
Return JSON responses.



When to use MYSQL and When to use VectorDB?
============================================
MySQL is used for structured data and exact queries such as customers, orders, products, and transactions. A Vector Database is used for semantic search, document retrieval, RAG applications, and similarity search. MySQL finds exact matches, while a Vector Database finds information based on meaning. In many AI applications, both are used together.

Use MySQL When You Need Exact Data

Examples:
Customers
Orders
Products
Employees
Payments
Invoices

Use Vector DB When You Need Meaning-Based Search

Examples:
PDFs
Company Policies
Knowledge Base
FAQs
Support Documents


How MCP Works?
================
MCP (Model Context Protocol) is a standard protocol that allows AI models to connect to external tools, databases, APIs, and applications. It enables AI to retrieve live data and perform actions through a common interface.

Why MCP?
============
Without MCP, every AI needs separate integrations. MCP provides a standard way for AI to discover and use tools.

What Problem Does MCP Solve?
=============================
It solves the problem of connecting AI models to real-world systems such as databases, CRMs, email services, and APIs using a common protocol.

Can MCP Access Live Data?
==========================
Yes. MCP is commonly used to retrieve real-time data from databases and applications.

What is LangChain?
===================
LangChain is a framework that helps build AI applications by connecting LLMs with prompts, memory, RAG, vector databases, tools, APIs, MCP servers, and AI agents.

Answer:
"LangChain is an AI application framework that helps developers connect LLMs with prompts, memory, documents, vector databases, tools, APIs, and agents."

Why use LangChain?

Answer:
"It simplifies building AI applications such as chatbots, RAG systems, and AI agents by providing reusable components and workflows."

Can LangChain work without RAG?
===================================
Answer:
Yes.

Example:

User
 ↓
Prompt
 ↓
LLM
 ↓
Answer

Does LangChain replace OpenAI?
===============================
Answer:
No.

OpenAI = AI Model
LangChain = Framework Around AI Model

Why Companies Use LangChain
===========================
Because it provides ready-made building blocks for:

✅ Chatbots

✅ RAG Systems

✅ AI Agents

✅ Enterprise Search

✅ Document Q&A

✅ Internal Company Copilots

Formula for a Good Prompt
============================
Role-Task-Context-Constraints-Output Format

Example
You are a senior Laravel developer.

Create a Laravel 11 REST API
for customer management.

Use MySQL.
Include validation.
Use service classes.
Return JSON responses.

Provide complete code.

Bad Prompt:
Create login API.

Good Prompt:
Create a Laravel 11 login API using JWT authentication.
Validate email and password.
Return JSON response.
Use MySQL database.

Types of Prompts

1. Zero-Shot Prompt
No examples given.
Translate English to Hindi.

2. One-Shot Prompt
One example given.
Hello → Hi
Convert:
Bye →

3. Few-Shot Prompt
Multiple examples given.
Hello → Hi
Thanks → Thank You
Sorry → Apologies

Convert:
Bye →


What is Semantic Search?
=========================
Semantic Search means searching based on the meaning of the query, not just exact keywords.

What is Similarity Search?
==========================
Similarity Search is the technical process used behind semantic search.

The system:
Converts text into vectors (embeddings)
Compares vectors
Finds the closest vectors

What are Chunks in AI/RAG?
==========================
A chunk is a small piece of a large document.

When a PDF, Word file, or webpage is too large, it is split into smaller sections called chunks.


###What is Chunk Overlap?
=========================
Chunk overlap means repeating some text between neighboring chunks so that important context is not lost when a document is split.

Example:

Chunk 1
Employees get 10 sick leaves.
Employees can work from home.

Chunk 2
Employees can work from home.
WFH is limited to 2 days.

Notice:
Employees can work from home.

appears in both chunks.

This is called overlap.



-------------------------------------------------------------------------------------------------------------------------------------

Q: How can AI hallucinations be reduced?
==========================================
Answer:
"AI hallucination can be reduced by providing accurate context, using RAG to fetch real data, lowering temperature, validating responses through databases or APIs, asking the model to cite sources, and using human review for critical decisions. The goal is to make the AI rely on verified information instead of guessing."

RAG (Retrieval-Augmented Generation) is generally considered one of the best approaches because the AI retrieves real-time information from trusted documents or databases before generating an answer, reducing the chance of making up facts.

2. Give Clear Context
The more context you provide, the less the model has to guess.

Bad Prompt
Explain the policy.

Good Prompt
Based on the attached HR policy PDF, explain the maternity leave policy.

5. Use Strong System Prompts

Example

You are an assistant.
Answer only from the provided context.
If information is unavailable, reply:
"I don't have enough information."
Do not make assumptions.

8. Human Review for Critical Tasks

For:

Medical advice
Legal documents
Financial decisions

Always keep a human in the loop.


How RAG Works (Retrieval-Augmented Generation)
=================================================
RAG first stores documents in a vector database by converting document chunks into embeddings. When a user asks a question, the question is converted into an embedding and matched against the stored vectors. The most relevant document chunks are retrieved and sent to the LLM as context. The LLM then generates an answer based on those retrieved documents, reducing hallucinations and improving accuracy."

RAG works like an open-book exam. When a user asks a question, RAG first searches the company documents for relevant information, then sends that information to the AI, and the AI answers based on the document instead of guessing.

PDF Upload
     |
     ▼
Text Extraction
     |
     ▼
Chunking
     |
     ▼
Embeddings
     |
     ▼
Vector Database
     |
     ▼
User Question
     |
     ▼
Similarity Search
     |
     ▼
Relevant Chunks
     |
     ▼
LLM
     |
     ▼
Final Answer

Rag & Mcp
Difference Between RAG (Retrieval-Augmented Generation) & MCP 
==============================================================
RAG is used to retrieve information from documents and knowledge bases, while MCP is used to connect AI with external tools, databases, and APIs to get live data or perform actions.

"In a company, RAG is used to retrieve information from documents such as HR policies, while MCP is used to access live systems such as employee databases. For example, to answer 'How many sick leaves do I have remaining?', RAG retrieves the leave policy from the HR document, MCP retrieves the employee's leave usage from the database, and the AI combines both to provide the final answer."


| Feature              | RAG                           | MCP                           |
| -------------------- | ----------------------------- | ----------------------------- |
| Purpose              | Read documents                | Use tools                     |
| Data Source          | PDFs, Docs, Knowledge Base    | APIs, Databases, Applications |
| Live Data            | No (usually stored documents) | Yes                           |
| Can Perform Actions? | No                            | Yes                           |
| Example              | Company Policy PDF            | MySQL, Shopify, Gmail         |
| Main Job             | Retrieve information          | Execute tools/actions         |



26. What is Multimodal AI?

Answer:
Multimodal AI can understand multiple types of input.

Examples:
Text
Images
Audio
Video


===========================================
ollama launch claude

ollama run llama3

Install Continue extension in VS Code.

Start Ollama: ollama serve

In Continue settings:

{
  "models": [
    {
      "title": "Llama3",
      "provider": "ollama",
      "model": "llama3:8b"
    }
  ]
}

Open your Laravel/PHP project

Difference Between AI, ML, and Deep Learning?
==============================================
AI
 └── Machine Learning
      └── Deep Learning
AI = Broad concept
ML = Learning from data
Deep Learning = Neural networks with many layers
Interview Answer

AI (Artificial Intelligence) = Making machines act smart like humans.
ML (Machine Learning) = A part of AI where machines learn patterns from data instead of being explicitly programmed.
Deep Learning = A part of ML that uses many-layered neural networks to learn complex patterns automatically.


How Chatgpt Works?
===================
Question: How does ChatGPT work?

Simple Interview Answer:

1.User enters a prompt.
2.The prompt is split into small pieces called tokens.
3.The Transformer analyzes the tokens and understands the context and relationships between words.
4.The AI predicts the most likely next token (word or part of a word).
5.It repeats this process token by token until the full response is generated.


In simple words

LangChain
============
"LangChain is a framework that helps connect LLMs with documents, databases, APIs, memory, and tools to build advanced AI applications such as chatbots, RAG systems, and AI agents."

LangChain is a framework used to build AI applications with Large Language Models (LLMs) like:

Laravel → Web Application Framework

LangChain → AI Application Framework

OpenAI GPT models
Meta Llama models
Anthropic Claude models
Google Gemini models

LangChain:

Calls your order API
Gets order details
Sends data to AI
AI replies

Hugging Face (simple explanation)
======================================
Hugging Face is like a GitHub + App Store for AI models.

It provides:
Thousands of pre-trained AI models
Datasets for training AI
Tools to use AI models easily

For example, if you want:
A chatbot model
A translation model
An image generation model

You can find and use them from Hugging Face.

Analogy:
GitHub stores code.
Hugging Face stores AI models.

What is Agentic AI?
====================
Answer:
Agentic AI refers to AI systems that can plan, make decisions, use tools, and execute multi-step tasks with limited human intervention.

Find all unpaid customers and send reminder emails.

Checks records
↓
Finds pending customers
↓
Calls customers
↓
Sends reminders
↓
Creates status report

What is an AI Copilot?
========================
Answer:
An AI Copilot is an AI assistant that helps users perform tasks such as coding, writing, analysis, and decision-making, while keeping the human in control of the final action."

Examples:

GitHub Copilot
AI customer support assistant
AI sales assistant

What is RAG (Retrieval-Augmented Generation)?
==================================================
Combines AI with external data for better answers.

It's a technique that helps an AI answer questions using information from external sources instead of relying only on what it learned during training.js

Example without RAG
Suppose you ask:

"What is our company's vacation policy?"

A normal AI model may not know because that information wasn't in its training data.

Example with RAG
When you ask the same question:

The system searches your company's documents.
It finds the vacation policy PDF.
It sends the relevant sections to the AI.
The AI generates an answer based on those sections.

What is Vibe Coding?
=====================
Vibe Coding is a modern way of programming where we describe what we want in natural language, and AI generates most of the code.

4. What is a Neural Network?
=============================
Answer:
A Neural Network is a computer system inspired by the way the human brain works.

It learns patterns from data and makes predictions or decisions.


6. What is an LLM?
Answer:
LLM stands for Large Language Model.

It is trained on massive amounts of text and can understand and generate human language.

Tokens:
========
Tokens are small pieces of text processed by AI.

The user writes text, but the model processes tokens. Tokenization turns the prompt into a structured sequence of numbers that the model can understand, calculate on, and use to generate the next response.

User Question
      ↓
Convert Text into Tokens
      ↓
Understand Context
      ↓
Predict Next Word
      ↓
Generate Response
      ↓
Show Result


Embeddings
==========
Embeddings convert text into numbers so AI can understand meaning.

Example:
Dog → [0.12,0.45,0.89]
Puppy → [0.15,0.48,0.85]

Embedding = the process/result of converting data (text, image, audio) into numbers.

Vector = the actual list of numbers produced by the embedding.


What is a Vector Database?
===============================
A vector database is a special database that stores data as vectors (lists of numbers) and finds information based on similarity or meaning.

You can use MySQL or MongoDB to store vectors, but vector databases are optimized to search millions or billions of vectors by meaning much faster and more efficiently, which is why they are preferred for AI applications.

Chroma
Pinecone
Weaviate
Qdrant
Milvus
LanceDB
Valid

Suppose you have a document:
-----------------------------
How to recover your account

AI converts it into a vector:
------------------------------

[0.12, 0.45, 0.88, ...]

AI Vector Database: Why It Is Used (Simple Explanation)
===========================================================
Vector database search using meaning not using the keyword.
If meaning is same then it return the result which other database can not do.

A vector database searches by meaning (semantic similarity), not just by exact keywords. If two sentences have the same or similar meaning, it can return relevant results even when the words are different. 

Traditional databases like MySQL usually search by exact words, patterns, or indexes, so they may miss those results.

Imagine you have 1 million documents and a user asks:

"How do I reset my password?"

The exact words "reset my password" may not exist in the document. Maybe the document says:

"To recover account access, click Forgot Password."

A normal database like MySQL searches for exact words or patterns. It may miss this result.

A vector database searches by meaning (semantic similarity), not just keywords.


What is MCP Server? (Model Context Protocol)
============================================
MCP Server helps AI connect with external tools, APIs, and databases securely.

MCP stands for - Model Context Protocol.

MCP (Model Context Protocol) is an open protocol that lets AI models communicate with external tools, databases, and APIs through a standard interface. An MCP server acts as a bridge between the AI and external systems, making tool integration simpler and more consistent.

An MCP Server acts as a secure bridge between AI and external systems by managing credentials, enforcing permissions, validating requests, and exposing only approved tools and data to the AI.

AI
 ↓
MCP Server
 ↓
(External Tools) API/Database/CRM/Files / GitHub / Gmail / Jira

What is Inference?
=====================
Ai model make prediction based on learning.

Inference is when a trained AI model uses what it has learned to make a prediction or generate an answer.

Think of it like:

Training = Learning
Inference = Using the learning

Real-Life Example
------------------
A student studies for an exam for 6 months.

Studying = Training
Writing answers in the exam = Inference


Ollama
============
Ollama is a tool that lets us run large language models (LLMs) directly on your own computer instead of sending our prompts to a cloud service.

You can think of it like this:

ChatGPT → usually runs on servers owned by a company.
Ollama → runs AI models on your laptop or desktop.
Simple analogy

Imagine AI models are like movies.

The model file is the movie.
Ollama is the video player.
Your computer is the TV.

Ollama loads the model and lets you chat with it.

How it works
Install Ollama.
Download a model (for example, Llama 3, Mistral, or Gemma).
Ollama loads the model into your computer's memory.
When you type a prompt:
Ollama sends the prompt to the model running locally.
The model predicts the next words one by one.
Ollama displays the response.

What is Context Window?
===============================
the amount of text it can read and use at once.

A context window is the amount of information an AI model can look at and remember at one time.

This includes:

Your current question
Previous messages in the chat
Uploaded documents
Instructions/system prompts
The AI's previous responses

Think of it like the AI's working memory.

Some older content may be dropped because it exceeds the context window.


Context limit
===================
AI models can only handle a certain number of tokens at once.

Example:

8,000-token context window
128,000-token context window
1,000,000-token context window (some models)

What is a Model?
====================
Answer:
A model is the trained AI system that makes predictions or generates answers.

What is RLHF?
=============
Answer:
Reinforcement Learning from Human Feedback.

Humans rate answers, and the model learns which responses are more useful.

========================================

## 1. What is AI?

**Interview Question:** What is AI?

**Simple Answer:**
AI (Artificial Intelligence) is technology that enables computers to perform tasks that normally require human intelligence, such as understanding language, recognizing images, making decisions, and answering questions.

**Example:**

* PHP application calculates tax using fixed rules.
* AI application can analyze customer behavior and recommend products automatically.

---

## 2. What is Machine Learning?

**Answer:**
Machine Learning (ML) is a branch of AI that enables computers to learn from data and improve their performance without being explicitly programmed for every rule.

**PHP Example:**

### Traditional PHP

if($amount > 10000){
   echo "Premium Customer";
}

### Machine Learning

Instead of fixed rules, ML learns from thousands of customer records and predicts whether a customer is premium.

---

## 3. What is Deep Learning?

**Answer:**
Deep Learning is a type of Machine Learning that uses neural networks with many layers to learn complex patterns.

A neural network is a machine learning model inspired by the way biological neurons are connected in the brain. It learns patterns from data by adjusting numerical weights between layers of artificial neurons.


**Example:**

* Face Recognition
* Self-driving cars
* ChatGPT

Think of it as:


AI
 └── Machine Learning
       └── Deep Learning


---

## 4. What is Generative AI?

**Answer:**
Generative AI creates new content such as text, images, code, audio, and videos.

**Examples:**

* ChatGPT → Text
* Midjourney → Images
* GitHub Copilot → Code

**PHP Example:**

User:
Write login API in PHP


AI generates:
<?php
$email=$_POST['email'];
$password=$_POST['password'];
?>


---
## 5. What is LLM?

**Answer:**
LLM (Large Language Model) is an AI model trained on huge amounts of text data to understand and generate human language.

**Examples:**

* ChatGPT
* Gemini
* Claude

**Simple Example:**
Like a very advanced autocomplete system trained on billions of words.

---

## 6. What is a Prompt?

**Answer:**
A prompt is the instruction given to an AI model.

**Example:**

Prompt:
Write a PHP API for user registration.


Output:


<?php
// registration code
?>


Prompt is similar to a function parameter.

---
## 7. What is Prompt Engineering?

**Answer:**
Prompt Engineering is the process of writing better instructions to get better AI responses.

### Bad Prompt
Write code

### Good Prompt
Write a Laravel 11 API for user registration using MySQL validation.

Better input = Better output.

---
## 8. What are Tokens?
**Answer:**
Tokens are small pieces of text processed by AI.

Example:
I love PHP

May become:
I
love
PHP

AI reads tokens instead of full sentences.

---
## 9. How does ChatGPT work?
**Simple Interview Answer:**

1. User enters a prompt.
2. Text is converted into tokens.
3. AI understands context using Transformer architecture.
4. AI predicts the most likely next word.
5. Words are generated one by one until the response is complete.

**Simple Example:**

Input:
PHP is a

AI predicts:
server-side

Then:
scripting

Then:
language

---

## 10. What is RAG?
**Answer:**
RAG (Retrieval Augmented Generation) allows AI to fetch external data before generating an answer.

**Example:**

Without RAG:
AI answers from training data.


With RAG:
AI searches company documents,
retrieves information,
then answers.


**Real Example:**
Chatbot answering questions from your HR policy PDF.

---

## 11. What is Vector Database?
**Answer:**
A Vector Database stores embeddings so AI can find similar information quickly.

**Example:**

Store:
PHP Tutorial
Laravel Guide
AWS Notes

User asks:
Laravel interview questions

Vector DB finds Laravel-related content even if exact words don't match.

Popular databases:
* Pinecone
* Weaviate
* Chroma

---

## 12. What are Embeddings?

**Answer:**
Embeddings convert text into numbers so AI can understand meaning.

Example:
Dog → [0.12,0.45,0.89]
Puppy → [0.15,0.48,0.85]

Since vectors are similar, AI knows Dog and Puppy are related.

---

## 13. What is an AI Agent?
**Answer:**
An AI Agent can think, decide, and use tools to complete tasks automatically.

**Example Workflow:**

User:
Find today's sales and email me a report.

Agent:

1. Query database
2. Generate report
3. Send email

No manual work required.

---

## 14. What is MCP Server?

**Answer:**
MCP (Model Context Protocol) is a standard that allows AI models to connect with external tools and data sources.

**PHP Example:**
ChatGPT wants customer details.
Instead of direct database access:

ChatGPT
   ↓
MCP Server
   ↓
MySQL

MCP acts like an API layer for AI.

--------------------------------------

## 15. What is Fine-Tuning?

**Answer:**
Teaching an existing model new domain knowledge.

**Example:**
General Model:


Knows everything.


Fine-Tuned Model:


Knows hospital policies,
medical procedures,
patient workflows.


---

## 16. What is Hallucination?

**Answer:**
When AI generates incorrect information confidently.

**Example:**

AI says:
PHP was invented in 2005.

Actual:
PHP was created in 1994.

That incorrect answer is a hallucination.

---

## 17. What is Human-in-the-Loop?

**Answer:**
A human reviews AI output before final action.

**Example:**

AI:
Screens 100 resumes


HR:
Approves final candidates


---

## 18. AI vs Traditional Programming

| Traditional Programming | AI                           |
| ----------------------- | ---------------------------- |
| Rules + Data = Output   | Data + Output = Learns Rules |
| Developer writes logic  | Model learns logic           |
| Fixed behavior          | Adaptive behavior            |
| Example: Tax Calculator | Example: Spam Detection      |

---

## 19. Real-World AI Project Interview Example
**Answer:**

1. User submits form.
2. Email content sent to AI.
3. AI classifies:

   * Spam
   * Not Spam
4. Save result in MySQL.
5. Valid emails go to CRM.
6. Spam emails go to review table.

This is similar to the n8n spam-filter workflow you've been discussing.

---

## 20. One-Line Interview Summary

**AI** → Makes machines intelligent.
**ML** → Learns from data.
**Deep Learning** → Uses neural networks.
**LLM** → Understands and generates text.
**Prompt** → Instruction given to AI.
**RAG** → AI + external knowledge.
**Embedding** → Text converted to vectors.
**Vector DB** → Stores embeddings.
**Agent** → AI that can use tools.
**MCP** → Standard for AI-tool communication.
**Hallucination** → AI gives wrong information confidently.

Master these 20 concepts first. They form the foundation for most AI, n8n, MCP, RAG, and LLM interview questions.


Here are **30 more AI interview questions and answers in very simple language**, especially useful for a PHP developer moving into AI.

---

# 21. What is NLP?

**Answer:**
NLP (Natural Language Processing) helps computers understand human language.

**Example:**

* ChatGPT answering questions
* Google Translate
* Email spam detection

---
# 22. What is Training in AI?

**Answer:**
Training is the process of teaching an AI model using large amounts of data.

**Example:**

Show AI thousands of emails:

text
Spam Email -> Spam
Good Email -> Not Spam

AI learns patterns from this data.

---
# 23. What is a Dataset?

**Answer:**
A dataset is a collection of data used to train AI.

**Example:**

| Email           | Label    |
| --------------- | -------- |
| Win $1000       | Spam     |
| Meeting at 5 PM | Not Spam |

This table is a dataset.

---
# 24. What is Supervised Learning?

**Answer:**
AI learns from labeled data.

**Example:**

text
Dog Image → Dog
Cat Image → Cat


Labels are already provided.

---

# 25. What is Unsupervised Learning?

**Answer:**
AI learns without labels and finds patterns itself.

**Example:**

Customer data:

text
Customer A
Customer B
Customer C


AI groups similar customers automatically.

---

# 26. What is Reinforcement Learning?

**Answer:**
AI learns through rewards and penalties.

**Example:**

Chess AI:

text
Good Move → Reward
Bad Move → Penalty


Eventually it learns to win.

---

# 27. What is a Model?

**Answer:**
A model is the trained AI system.

**Example:**
After training:

text
Data + Training = Model


ChatGPT itself is a model.

---

# 28. What is Inference?

**Answer:**
Inference means using a trained model to make predictions.

**Example:**

text
Training = Learning
Inference = Using learned knowledge


When you ask ChatGPT a question, it's performing inference.

---

# 29. What is AI Bias?

**Answer:**
Bias happens when AI gives unfair results because of biased training data.

**Example:**

If AI is trained mostly on male resumes, it may favor male candidates.

---

# 30. What is Accuracy?

**Answer:**
Accuracy shows how often AI gives correct answers.

Formula:

text
Correct Predictions / Total Predictions


Example:

text
95 correct out of 100
Accuracy = 95%


---

# 31. What is Overfitting?

**Answer:**
Overfitting happens when a model memorizes training data and performs poorly on new data.

**Example:**

Student memorizes answers instead of understanding concepts.

What is Bias in AI?

Answer:
Bias occurs when training data contains unfair patterns, causing the model to produce unfair results.

---

# 32. What is Underfitting?

**Answer:**
AI hasn't learned enough from training data.

**Example:**

Student studies only one chapter for the entire exam.

---

# 33. What is Computer Vision?

**Answer:**
Computer Vision allows computers to understand images and videos.

**Examples:**

* Face recognition
* Vehicle detection
* Medical image analysis

---

# 34. What is OCR?

**Answer:**
OCR (Optical Character Recognition) converts images into text.

**Example:**

Image:

text
Invoice.jpg

Output:
text
Invoice Number: 12345


---
# 35. What is Speech Recognition?

**Answer:**
Converts voice into text.

**Examples:**

* Siri
* Google Assistant
* Voice typing

---
# 36. What is Text-to-Speech?

**Answer:**
Converts text into spoken voice.

**Example:**
text
"Welcome to our website"

AI speaks the sentence aloud.

---
# 37. What is Sentiment Analysis?

**Answer:**
Determines whether text is positive, negative, or neutral.

**Example:**
text
"I love this product"

Result:
text
Positive
---
# 38. What is Classification?

**Answer:**
Classification means putting data into categories.

**Example:**

text
Email → Spam
Email → Not Spam
---

# 39. What is Regression?

**Answer:**
Regression predicts a numerical value.

**Example:**
Predict:

text
House Price = ₹50,00,000


---
# 40. What is Clustering?

**Answer:**
Grouping similar items together.

**Example:**
E-commerce website groups customers:

text
Students
Professionals
Retired Users


---
# 41. What is Transfer Learning?

**Answer:**
Using an already trained model and adapting it for a new task.

**Example:**
Take an image recognition model and retrain it to recognize medical images.

---
# 42. What is Temperature in LLMs?

**Answer:**
Temperature controls creativity.

**Low Temperature (0.2)**
text
More accurate
Less creative

**High Temperature (0.9)**
text
More creative
Less predictable

---
# 43. What is Context Window?

**Answer:**
Amount of information AI can remember in one conversation.

**Example:**
Like a whiteboard.
Small whiteboard → remembers less.
Large whiteboard → remembers more.

---

# 44. What is Token Limit?

**Answer:**
Maximum number of tokens AI can process at one time.

**Example:**

Long PDF + Question = Token usage.

---

# 45. What is Multimodal AI?

**Answer:**
AI that can work with multiple data types.

**Examples:**

* Text
* Images
* Audio
* Video

ChatGPT can analyze images and text, making it multimodal.

---

# 46. What is an API in AI?

**Answer:**
An API allows applications to communicate with AI models.

**PHP Example:**


$response = file_get_contents(
'https://api.openai.com/...'
);


Send prompt → Get AI response.

---

# 47. What is a Vector?

**Answer:**
A vector is a list of numbers representing meaning.

Example:

text
PHP → [0.12, 0.33, 0.91]
Laravel → [0.11, 0.30, 0.88]


AI sees them as related.

---

# 48. What is Semantic Search?

**Answer:**
Search by meaning instead of exact words.

**Example:**

Search:

text
PHP Framework


Results:

text
Laravel
Symfony
CodeIgniter


Even if "PHP Framework" isn't written exactly.

---

# 49. What is AI Automation?

**Answer:**
AI automatically performs tasks without human intervention.

**Example:**

text
New Email
↓
AI reads email
↓
Classifies priority
↓
Creates ticket


---

# 50. What is an AI Chatbot?

**Answer:**
A chatbot uses AI to interact with users through conversation.

**Examples:**

* ChatGPT
* Customer Support Bots
* Banking Assistants

---

# Quick Interview Revision

| Term            | Simple Meaning                    |
| --------------- | --------------------------------- |
| AI              | Makes machines intelligent        |
| ML              | Learns from data                  |
| Deep Learning   | Advanced ML using neural networks |
| NLP             | Understands language              |
| Dataset         | Collection of data                |
| Model           | Trained AI                        |
| Training        | Teaching AI                       |
| Inference       | Using AI                          |
| RAG             | AI + External Data                |
| Embedding       | Text converted to numbers         |
| Vector DB       | Stores embeddings                 |
| Agent           | AI that uses tools                |
| MCP             | Connects AI to tools              |
| OCR             | Image to Text                     |
| Computer Vision | Understands images                |
| Classification  | Category prediction               |
| Regression      | Number prediction                 |
| Clustering      | Group similar data                |
| Fine-Tuning     | Custom training                   |
| Hallucination   | Wrong AI answer                   |

These 50 questions cover about 80–90% of the AI concepts commonly discussed in beginner-to-intermediate AI interviews for developers.


===========================================================================================================
✅ 1. What is Generative AI?

Simple Answer:
Generative AI is a type of AI that can create new content like text, images, audio, or code based on user input.

Based on user input create output.

👉 Example:

ChatGPT writes text
AI creates images from prompts
AI generates code

✅ 2. What is an LLM (Large Language Model)?

Simple Answer:
An LLM is an AI model trained on huge text data to understand and generate human-like language.

👉 Examples:

ChatGPT
Gemini
Claude
✅ 3. What is Prompt Engineering?

Simple Answer:
Prompt engineering is the skill of writing clear and effective instructions to get the best output from AI.

👉 Example:
❌ Bad: “write code”
✅ Good: “Write a Laravel 11 API with authentication using JWT”

✅ 4. Popular Generative AI Tools (with creators)

🧠 Text / Chat AI
==============================
ChatGPT → Developed by OpenAI
Gemini → Developed by Google
Claude → Developed by Anthropic
LLaMA → Developed by Meta

💻 Code Generation AI
===============================
GitHub Copilot → GitHub + OpenAI
OpenAI Codex
Claude Code
Cursor
CodeWhisperer → Amazon

🎨 Image Generation Models
==============================
DALL·E → OpenAI
Midjourney → Midjourney Inc.
Stable Diffusion → Stability AI
Imagen → Google

🎥 Video Generation AI (important for interviews)
=================================
Sora → OpenAI
Runway Gen-2 → Runway


✅ 5. Types of Generative AI Models
1. Text Models
Generate text, chat, code
Example: ChatGPT, Claude

2. Image Models
Convert text → images
Example: DALL·E, Midjourney

3. Audio Models
Generate voice/music
Example: ElevenLabs

4. Video Models
Generate videos from text
Example: Sora

✅ 6. How Generative AI Works (Simple)

Train on large data (text/images)
Learn patterns
Predict next word/pixel
Generate output

👉 Based on Transformer architecture

✅ 7. What is Transformer Model?

Simple Answer:
A deep learning model that understands context using attention mechanism.

👉 Introduced in:

Attention Is All You Need

✅ 8. Common Interview Questions (with simple answers)

❓ Q1: Difference between AI, ML, DL?
AI → Smart systems
ML → Learns from data
DL → Neural networks (advanced ML)

❓ Q2: What is Generative vs Discriminative AI?

Generative → Creates data (images/text)
Discriminative → Classifies data (spam/not spam)

❓ Q3: What is hallucination in AI?

AI gives wrong or fake answers confidently

❓ Q4: What is fine-tuning?

Training a pre-trained model on specific data

❓ Q5: What is temperature in AI?

Temperature in AI controls how random or creative the AI's responses are.

Controls randomness:

Low → focused
High → creative


Simple Analogy

Imagine AI is choosing a chocolate from a box:

Low temperature: Almost always picks the most popular chocolate.
High temperature: More willing to try different chocolates, even unusual ones.


✅ 9. How to Create a Simple GenAI Chatbot

Basic flow:

User input
Send to API (OpenAI / Gemini)
Get response
Show in UI

👉 Tools:

Backend: Laravel / Node.js
API: OpenAI
Frontend: React / jQuery

✅ 10. Real Use Cases (good for interviews)
Chatbots (customer support)
Code generation
Image creation
Content writing
AI assistants

=====================

🧠 BASIC AI QUESTIONS (1–10)
1. What is AI?

AI (Artificial Intelligence) is the ability of machines to perform tasks that normally require human intelligence.

2. What is Machine Learning?

Machine Learning is a subset of AI where systems learn from data without being explicitly programmed.

3. What is Deep Learning?

Deep Learning uses neural networks with many layers to solve complex problems like image and speech recognition.

A neural network is a computer system inspired by the way the human brain processes information. It learns patterns from data and uses those patterns to make predictions or decisions.

Real-Life Examples
Face recognition on smartphones
Voice assistants like Siri and Google Assistant
Language models such as ChatGPT
Recommendation systems on YouTube and Netflix
Self-driving car perception systems

4. What is Generative AI?

Generative AI creates new content like text, images, or code (e.g., ChatGPT).

5. What is an LLM?

LLM (Large Language Model) is trained on large text data to generate human-like responses.

6. What is NLP?

Natural Language Processing helps machines understand human language.

7. What is Computer Vision?

It allows machines to understand images and videos.

8. What is a Dataset?

A collection of data used to train AI models.

9. What is Training Data?

Data used to teach a model patterns.

10. What is a Model?

A trained system that makes predictions or generates outputs.

🤖 MACHINE LEARNING QUESTIONS (11–20)

11. Types of Machine Learning?
Supervised
Unsupervised
Reinforcement Learning
12. What is Supervised Learning?

Learning using labeled data.

13. What is Unsupervised Learning?

Finding patterns in unlabeled data.

14. What is Reinforcement Learning?

Learning by rewards and penalties.

15. What is Overfitting?

Model performs well on training data but poorly on new data.

16. What is Underfitting?

Model fails to learn patterns properly.

17. What is Feature?

An input variable used for prediction.

18. What is Label?

The output or target variable.

19. What is Accuracy?

Percentage of correct predictions.

20. What is Loss Function?

Measures how wrong the model is.

🧠 DEEP LEARNING QUESTIONS (21–30)
21. What is a Neural Network?

A system inspired by the human brain to process data.

22. What is an Activation Function?

It decides whether a neuron should activate.

23. What is Backpropagation?

Process of updating weights to reduce error.

24. What is Epoch?

One complete pass of training data.

25. What is Batch Size?

Number of samples processed at once.

26. What is Gradient Descent?

Optimization algorithm to minimize loss.

27. What is CNN?

Convolutional Neural Network for images.

28. What is RNN?

Recurrent Neural Network for sequence data.

29. What is Transformer?

Model using attention mechanism for better understanding context.

30. Example of Transformer model?

GPT
BERT

✨ GENERATIVE AI QUESTIONS (31–40)

31. What is Prompt?

Input given to AI.

32. What is Prompt Engineering?

Writing better prompts to get better output.

33. What is Temperature?

Controls randomness in output.

34. What is Token?

Small unit of text (word/part of word).

35. What is Fine-tuning?

Training a pre-trained model on custom data.

36. What is Embedding?

Numerical representation of text.

37. What is Hallucination?

AI giving incorrect answers confidently.

38. What is Context Window?

Amount of text AI can remember in one request.

39. What is API in AI?

Interface to interact with AI models.

40. Example of AI APIs?

OpenAI API
Google AI APIs

🛠️ PRACTICAL & ADVANCED QUESTIONS (41–50)

41. How to build a chatbot?
UI + Backend + AI API

42. What is RAG (Retrieval-Augmented Generation)?

Combines AI with external data for better answers.

43. What is Vector Database?

Stores embeddings for fast search (e.g., Pinecone).

44. What is LangChain?

Framework to build AI applications.

45. What is Hugging Face?

Simple Answer:
Hugging Face is a platform where you can find, use, train, and share AI models, especially for Natural Language Processing (NLP) and Generative AI.

46. What is Open Source AI Model?

Freely available AI models (e.g., LLaMA).

47. What is Diffusion Model?

Used to generate images step-by-step from noise.

48. Example of Image Models?
DALL·E
Stable Diffusion

49. What are AI limitations?
Bias
Hallucination
Data dependency

50. Future of AI?
Automation
AI assistants
Personalized systems

===============================================================================
AI Fundamentals
===================
### Q1. What is Artificial Intelligence (AI)?

**AI** is when computers are made to think and perform tasks like humans, such as learning, solving problems, and making decisions.

### Q2. What is Machine Learning (ML)?

**Machine Learning** is a type of AI where computers learn from data and improve automatically without being programmed for every task.

### Q3. What is Deep Learning?

**Deep Learning** is a type of Machine Learning that uses layers of artificial neurons (neural networks) to learn complex patterns from data.

### Q4. What is Generative AI?

**Generative AI** is AI that can create new content such as text, images, music, videos, or code based on what it has learned.

### Q5. What is a Large Language Model (LLM)?

An **LLM** is an AI model trained on a huge amount of text to understand and generate human-like language. Examples include GPT, Claude, and Gemini.

### Q6. What is Multimodal AI?

**Multimodal AI** can understand and work with different types of data together, such as text, images, audio, and video.

==========
LLM Core Concepts
===================

### Q7. What is a token?

A **token** is a small piece of text that an LLM reads and processes. It can be a word, part of a word, or even a character.

### Q8. What is a context window?

The amount of text an AI model can remember and process at one time.

### Q9. What is temperature in LLM sampling?

**Temperature** controls how creative or random the AI's answers are.

* Low temperature = more accurate and predictable
* High temperature = more creative and varied

### Q10. What is Top-P (nucleus) sampling?

**Top-P** is a method that lets the AI choose words from the most likely options, helping balance creativity and accuracy.

### Q11. What is hallucination in LLMs?

A **hallucination** happens when an AI gives incorrect or made-up information as if it were true.

### Q12. What is fine-tuning?

**Fine-tuning** is training a pre-trained AI model on specific data to make it better at a particular task.

### Q13. What is instruction tuning?

**Instruction tuning** trains an AI using examples of instructions and correct answers so it can follow user commands more effectively.

### Q14. What is RLHF (Reinforcement Learning from Human Feedback)?

**RLHF** is a training method where human feedback is used to teach AI to give more helpful, safe, and preferred responses.

===============================

## Prompt Engineering Basics

### Q15. What is prompt engineering?

**Prompt engineering** is the practice of writing clear and effective prompts to get better answers from an AI model.

### Q16. What is zero-shot prompting?

**Zero-shot prompting** means asking the AI to do a task without giving any examples.

### Q17. What is one-shot prompting?

**One-shot prompting** means giving the AI one example before asking it to perform the task.

### Q18. What is few-shot prompting?

**Few-shot prompting** means providing a few examples to help the AI understand the task better.

### Q19. What is Chain of Thought (CoT) prompting?

A reasoning approach where AI solves problems step by step.


### Q20. What is Tree of Thoughts (ToT)?

**Tree of Thoughts** is a method where the AI explores multiple possible solutions and chooses the best one.

### Q21. What is ReAct prompting?

**ReAct (Reasoning + Acting)** allows the AI to think, take actions (like using tools), and then continue reasoning.

### Q22. What is role-based prompting?

**Role-based prompting** tells the AI to act as a specific person or expert, such as a teacher, doctor, or programmer.

### Q23. What is structured output prompting?

**Structured output prompting** asks the AI to return answers in a specific format, such as JSON, XML, or tables.

### Q24. What is prompt chaining?

**Prompt chaining** breaks a complex task into smaller steps, where the output of one step becomes the input for the next.

---

## Security & Privacy Basics

### Q25. What is prompt injection?

**Prompt injection** is an attack where hidden or malicious instructions try to make the AI ignore its original rules.

### Q26. What is data privacy in AI?

**Data privacy** means protecting personal and sensitive information from unauthorized access or misuse.

### Q27. What is PII (Personally Identifiable Information) protection?

**PII protection** keeps personal information such as names, phone numbers, emails, and addresses safe and secure.

### Q28. What are guardrails in AI?

**Guardrails** are safety rules and controls that help prevent AI from generating harmful or unsafe content.

### Q29. What is content moderation?

**Content moderation** is the process of checking and filtering AI-generated content to ensure it is safe and appropriate.

## RAG Fundamentals

### Q30. What is RAG (Retrieval-Augmented Generation)?

**RAG** is a technique where an AI first searches relevant documents and then uses that information to generate a better answer.

RAG (Retrieval-Augmented Generation)

AI first searches information, then creates an answer.

Retrieval

Finding relevant information from documents or databases.

### Q31. What are embeddings?

**Embeddings** are numerical representations of text that help AI understand the meaning of words and sentences.

### Q32. What is semantic search?

**Semantic search** finds information based on meaning and context, not just exact keywords.

### Q33. What is a vector database?

A **vector database** stores embeddings and helps quickly find similar information using vector search.

### Q34. What is chunking?

**Chunking** is the process of splitting large documents into smaller pieces for easier storage and retrieval.

### Q35. What is vector search?

**Vector search** finds similar content by comparing embeddings (vectors) instead of matching exact words.

### Q36. What is hybrid search?

**Hybrid search** combines keyword search and semantic search to improve search results.

### Q37. What is reranking?

**Reranking** means reordering search results to place the most relevant information at the top.

### Q38. What is a knowledge base?

A **knowledge base** is a collection of documents and information that AI can search and use to answer questions.

---

## AI Agents Basics

### Q39. What is an AI agent?

An **AI agent** is a system that can observe, think, make decisions, and perform tasks to achieve a goal.

### Q40. What is an autonomous agent?

An **autonomous agent** can work independently with little or no human guidance.

### Q41. What is agent memory?

**Agent memory** stores past information and interactions so the agent can remember and respond better.

### Q42. What is tool usage in agents?

**Tool usage** allows agents to use external tools such as APIs, calculators, databases, or web searches.

### Q43. What is multi-agent systems?

**Multi-agent systems** are groups of AI agents that work together to solve tasks or problems.

---

## MCP & APIs Basics

### Q44. What is MCP (Model Context Protocol)?

**MCP** is a standard way for AI models to connect safely with external tools, databases, and services.

### Q45. What is an MCP server?

An **MCP server** provides tools and resources that AI models can access and use.

### Q46. What is an MCP client?

An **MCP client** is the application that connects to MCP servers to use their tools and resources.

### Q47. What is function calling?

**Function calling** allows an AI model to request an external function with specific inputs to perform a task.

### Q48. What is API integration?

**API integration** connects AI applications with external services to exchange data and perform actions.

---

## Frameworks & APIs

### Q49. What is LangChain?

**LangChain** is a framework that helps developers build AI applications using LLMs, tools, memory, and workflows.

### Q50. What is the OpenAI API?

The **OpenAI API** allows developers to access AI models and use them in their own applications and software.



## Advanced LLM Concepts

### Q51. What is the transformer architecture?

A **Transformer** is a neural network architecture that uses attention mechanisms to understand relationships between words in a sentence.

### Q52. What is self-attention?

**Self-attention** helps a model focus on important words in a sentence by checking how each word relates to other words.

### Q53. What is multi-head attention?

**Multi-head attention** allows the model to look at information from different perspectives at the same time.

### Q54. What is positional encoding?

**Positional encoding** gives the model information about the order of words in a sentence.

### Q55. What is backpropagation?

**Backpropagation** is a learning process where the model uses its mistakes to improve its predictions.

### Q56. What is gradient descent?

**Gradient descent** is an optimization method that helps the model reduce errors step by step during training.

### Q57. What is overfitting?

**Overfitting** happens when a model memorizes training data and performs poorly on new, unseen data.

### Q58. What is regularization?

**Regularization** is a technique used to reduce overfitting and improve the model's ability to generalize.

### Q59. What is dropout?

**Dropout** randomly turns off some neurons during training to make the model more robust and prevent overfitting.

### Q60. What is batch normalization?

**Batch normalization** helps stabilize and speed up model training by normalizing data between layers.

---

## Tokenization & Optimization

### Q61. What is BPE (Byte Pair Encoding)?

**BPE** is a tokenization method that combines frequently used characters or word parts into tokens.

### Q62. What is SentencePiece?

**SentencePiece** is a tokenization method that learns tokens directly from text without relying on spaces between words.

### Q63. What is token efficiency?

**Token efficiency** means using fewer tokens while keeping the same meaning, reducing cost and improving speed.

### Q64. What is prompt compression?

**Prompt compression** is shortening a prompt by removing unnecessary words while keeping the important information.

### Q65. What is logit bias?

**Logit bias** is a way to increase or decrease the chance of certain words appearing in an AI's response.


## Advanced Prompt Engineering

### Q66. What is meta-prompting?

**Meta-prompting** is asking an AI to create or improve prompts for a task.

### Q67. What is prompt decomposition?

**Prompt decomposition** means breaking a complex problem into smaller, easier prompts.

### Q68. What is negative prompting?

**Negative prompting** tells the AI what to avoid in its response.

### Q69. What is dynamic few-shot prompting?

**Dynamic few-shot prompting** automatically selects the most relevant examples for a query.

### Q70. What is constraint-based prompting?

**Constraint-based prompting** gives specific rules, such as word limits, format, or content restrictions.

### Q71. What is in-context learning?

**In-context learning** is when an AI learns how to perform a task from examples provided in the prompt.

### Q72. What is prompt optimization?

**Prompt optimization** is the process of improving prompts to get better AI responses.

### Q73. What is system prompting?

**System prompting** provides the main instructions that guide the AI's behavior throughout a conversation.

---

## RAG Architecture Deep Dive

### Q74. What is the RAG pipeline?

The **RAG pipeline** works like this:
**User Query → Search Documents → Select Relevant Information → Send to LLM → Generate Answer**

### Q75. What is semantic similarity?

**Semantic similarity** measures how similar two pieces of text are in meaning.

### Q76. What is cosine similarity?

**Cosine similarity** is a mathematical method used to compare two vectors and measure how similar they are.

### Q77. What is ANN (Approximate Nearest Neighbor) search?

**ANN search** quickly finds vectors that are most similar to a given vector without checking every vector.

### Q78. What is Pinecone?

Pinecone is a cloud-based vector database used for storing and searching embeddings in AI applications.

### Q79. What is Weaviate?

Weaviate is an open-source vector database that supports semantic search and AI applications.

### Q80. What is Milvus?

Milvus is an open-source vector database designed for large-scale similarity search.

### Q81. What is Qdrant?

Qdrant is a vector database and search engine built for AI and machine learning applications.

### Q82. What is ChromaDB?

ChromaDB is a lightweight vector database commonly used in LLM and RAG projects.

### Q83. What is citation generation in RAG?

**Citation generation** adds source references to answers so users can verify where the information came from.

### Q84. What is context retrieval optimization?

**Context retrieval optimization** improves the quality of retrieved information through better search, chunking, and ranking methods.

### Q85. What is multi-hop retrieval?

**Multi-hop retrieval** gathers information from multiple documents or sources to answer complex questions.

### Q86. What is query expansion?

**Query expansion** creates additional related search queries to improve retrieval results.


## AI Agents & Orchestration

### Q87. What is agent planning?

**Agent planning** is the process of breaking a large goal into smaller tasks and deciding the steps needed to complete them.

### Q88. What is agent orchestration?

**Agent orchestration** is managing and coordinating multiple AI agents so they can work together effectively.

### Q89. What is CrewAI?

CrewAI is a framework for creating teams of AI agents with different roles and responsibilities.

### Q90. What is LangGraph?

LangGraph is a framework for building AI applications with workflows, memory, and multiple agents.

### Q91. What is agentic AI?

**Agentic AI** refers to AI systems that can make decisions and perform actions independently to achieve goals.

### Q92. What is workflow automation with agents?

**Workflow automation with agents** uses AI agents to complete multi-step tasks automatically without constant human involvement.

### Q93. What is agent evaluation?

**Agent evaluation** is measuring how well an AI agent performs tasks based on accuracy, speed, and success rate.

### Q94. What is agent monitoring?

**Agent monitoring** is tracking an agent's actions, decisions, and performance to improve reliability and fix issues.

---

## Advanced MCP

### Q95. What is MCP architecture?

**MCP architecture** is the overall design of how AI clients and servers communicate, share tools, and exchange information.

### Q96. What is MCP transport layer?

The **MCP transport layer** is the communication method (such as HTTP or WebSocket) used between MCP clients and servers.

### Q97. What is MCP tools?

**MCP tools** are functions or actions that an MCP server provides for AI models to use.

### Q98. What is MCP resources?

**MCP resources** are files, documents, databases, or other information that AI models can access through MCP.

### Q99. What is MCP prompts?

**MCP prompts** are predefined instructions or templates provided by an MCP server to guide AI behavior.

### Q100. What is MCP security?

**MCP security** protects MCP systems using authentication, permissions, and validation to prevent unauthorized access.

---

## AI Frameworks & Libraries

### Q101. What is LangGraph?

LangGraph is a framework for building complex AI workflows using graphs and multiple agents.

### Q102. What is LlamaIndex?

LlamaIndex is a framework that helps connect LLMs to external data sources for retrieval and question answering.

### Q103. What is Haystack?

Haystack is a framework for building search, RAG, and NLP applications.

### Q104. What is Semantic Kernel?

Semantic Kernel is a framework from Microsoft that helps integrate AI models into business applications.

### Q105. What is AutoGen?

AutoGen is a framework for creating multiple AI agents that can communicate and work together automatically.


## Infrastructure & Deployment

### Q106. What is an AI gateway?

An **AI gateway** is a system that manages and routes requests to different AI models and providers.

### Q107. What is model routing?

**Model routing** chooses the best AI model for a task based on cost, speed, or performance.

### Q108. What is load balancing for AI?

**Load balancing** distributes requests across multiple servers or models to avoid overload.

### Q109. What is rate limiting?

**Rate limiting** controls how many requests a user or application can make within a certain time.

### Q110. What is caching in AI systems?

**Caching** stores previous responses so repeated requests can be answered faster and more cheaply.

### Q111. What is observability in AI?

**Observability** is monitoring and tracking AI systems to understand their behavior and performance.

### Q112. What is latency optimization?

**Latency optimization** is improving system speed so users get responses faster.

### Q113. What is cost optimization?

**Cost optimization** is reducing AI expenses by using resources more efficiently.

---

## Memory & Context Management

### Q114. What is short-term memory in agents?

**Short-term memory** stores recent conversation details for the current session.

### Q115. What is long-term memory in agents?

**Long-term memory** stores information for future sessions and long-term learning.

### Q116. What is conversation memory?

**Conversation memory** keeps track of previous messages to maintain context during a chat.

### Q117. What is session management?

**Session management** handles user sessions and maintains their state while interacting with a system.

### Q118. What is context management?

**Context management** ensures the right information is available when the AI makes decisions or responds.

---

## Claude API & Other Model APIs

### Q119. What is the Claude API?

The **Claude API** allows developers to use Anthropic's Claude AI models in their applications.

### Q120. What is the Gemini API?

The **Gemini API** allows developers to access Google's Gemini AI models for different tasks.

### Q121. What are local LLMs?

**Local LLMs** are AI models that run on your own device or server instead of the cloud.

### Q122. What is model switching?

**Model switching** is changing between different AI models depending on the task or requirements.

---

## Emerging Concepts

### Q123. What is Model Context Engineering (MCE)?

**Model Context Engineering (MCE)** is the process of designing and managing the information given to an AI model for better results.

### Q124. What is prompt caching?

**Prompt caching** stores frequently used prompts so they can be reused quickly and at lower cost.

### Q125. What is knowledge graph integration?

**Knowledge graph integration** combines structured knowledge with AI models to improve accuracy and reasoning.

### Q126. What is hybrid RAG?

**Hybrid RAG** combines vector search, keyword search, and knowledge graphs to retrieve better information.

### Q127. What is multi-modal RAG?

**Multi-modal RAG** retrieves and uses information from text, images, audio, and videos.

### Q128. What is streaming responses?

**Streaming responses** send AI output piece by piece as it is generated instead of waiting for the full answer.

### Q129. What is function result validation?

**Function result validation** checks whether tool outputs are correct, safe, and useful before the AI uses them.

### Q130. What is agent debugging?

**Agent debugging** is the process of finding and fixing errors in an AI agent's decisions, actions, or workflow.

Advanced Level
Deep Learning Theory
Q131. Explain attention complexity and its computational implications.

Attention complexity is usually O(n²), meaning computation grows quickly as input length increases, making long contexts expensive.

Q132. What is sparse attention?

Sparse attention lets tokens focus only on selected tokens instead of all tokens, reducing computation and memory usage.

Q133. What are mixture of experts (MoE) models?

MoE models use multiple expert networks and send each input to only the most relevant experts, improving efficiency.

Q134. What is neural architecture search (NAS)?

NAS automatically finds the best neural network design for a specific task.

Q135. What is curriculum learning in LLM training?

Curriculum learning trains models using easier examples first and harder examples later.

Q136. What is knowledge distillation for LLMs?

Knowledge distillation transfers knowledge from a large model to a smaller model.

Q137. Explain scaling laws in LLMs.

Scaling laws show that model performance generally improves when model size, training data, and computing power increase.

Q138. What is quantization in neural networks?

Quantization reduces the precision of model weights (e.g., 32-bit to 8-bit) to make models smaller and faster.

Q139. What is pruning in neural networks?

Pruning removes unnecessary neurons or connections to reduce model size and improve speed.

Q140. What is distillation loss in multi-task learning?

Distillation loss helps a model learn multiple tasks by balancing different learning objectives.

Advanced Prompt Engineering
Q141. What is self-refining prompting?

Self-refining prompting asks the model to review and improve its own answer.

Q142. What is adversarial prompting?

Adversarial prompting uses challenging inputs to test the model's weaknesses and robustness.

Q143. What is retrieval-augmented prompting?

Retrieval-augmented prompting adds information retrieved from external sources into the prompt.

Q144. What is program-aided language models?

Program-aided language models generate code or logical steps to help solve problems more accurately.

Q145. What is in-context instruction generation?

In-context instruction generation creates task instructions dynamically based on the input.

Q146. What is adaptive prompting?

Adaptive prompting changes prompts automatically based on previous results to improve performance.

Q147. What is chain prompting?

Chain prompting uses multiple connected prompts where each output becomes input for the next step.

Q148. What is semantic routing in prompts?

Semantic routing sends different types of queries to different prompts or models based on their meaning.

Advanced RAG Systems
Q149. What is iterative retrieval-augmentation?

Iterative RAG repeatedly retrieves information and refines searches until enough information is collected.

Q150. What is learning-to-rank for RAG?

Learning-to-rank uses machine learning to sort retrieved documents by relevance.

Q151. What is dense passage retrieval (DPR)?

DPR uses embeddings to find documents that are semantically similar to a query.

Q152. What is ColBERT?

ColBERT is a retrieval method that compares query and document tokens for accurate search results.

Q153. What is cross-encoder reranking?

Cross-encoder reranking evaluates a query and document together to calculate a more accurate relevance score.

Q154. What is self-supervised contrastive learning for embeddings?

Contrastive learning trains embeddings by bringing similar items closer and pushing different items apart.

Q155. What is domain-specific embeddings?

Domain-specific embeddings are embeddings trained for a particular field, such as healthcare or finance.

Q156. What is entity-aware RAG?

Entity-aware RAG tracks people, places, organizations, and other entities across documents for better understanding.

Q157. What is multi-modal retrieval in RAG?

Multi-modal retrieval searches information across text, images, audio, and video.

Q158. What is recursive retrieval?

Recursive retrieval uses retrieved information to create new searches and gather more relevant data.

Q159. What is prompt-aware retrieval?

Prompt-aware retrieval considers the prompt's intent when selecting relevant information.

Q160. What is graph-based RAG?

Graph-based RAG stores knowledge as connected graphs, helping AI understand relationships between pieces of information.

# Advanced AI Security

### Q161. What is adversarial training for safety?

**Adversarial training** improves model safety by training it with difficult or malicious examples.

### Q162. What is watermarking for LLM detection?

**Watermarking** adds hidden patterns to AI-generated content so it can later be identified as AI-created.

### Q163. What is membership inference attacks?

A **membership inference attack** tries to determine whether specific data was used to train a model.

### Q164. What is model inversion attacks?

A **model inversion attack** attempts to reconstruct training data from a model's outputs.

### Q165. What is differential privacy for LLMs?

**Differential privacy** adds controlled noise to training data or results to protect individual privacy.

### Q166. What is federated learning for AI?

**Federated learning** trains models on multiple devices without moving the data to a central location.

### Q167. What is homomorphic encryption?

**Homomorphic encryption** allows computations to be performed on encrypted data without decrypting it.

### Q168. What is secure multi-party computation?

**Secure multi-party computation (SMPC)** allows multiple parties to work together on data without revealing their private information.

### Q169. What is input sanitization and validation?

**Input sanitization and validation** removes harmful or invalid content before it reaches the AI system.

### Q170. What is output filtering?

**Output filtering** checks AI responses and removes unsafe, harmful, or restricted content before showing it to users.

---

# AI Governance & Compliance

### Q171. What is AI ethics?

**AI ethics** focuses on using AI responsibly, fairly, and safely.

### Q172. What is fairness in AI?

**Fairness in AI** means treating all users equally and avoiding bias or discrimination.

### Q173. What is explainability and interpretability?

* **Explainability**: Making AI decisions easy for humans to understand.
* **Interpretability**: Understanding how the AI model works internally.

### Q174. What is model auditing?

**Model auditing** is the process of checking AI systems for accuracy, bias, security, and compliance.

### Q175. What is AI governance frameworks?

**AI governance frameworks** are rules and policies that guide the responsible development and use of AI.

### Q176. What is GDPR compliance for AI?

**GDPR compliance** ensures AI systems follow privacy laws and protect user data rights.

### Q177. What is algorithmic auditing?

**Algorithmic auditing** tests AI systems to find biases, errors, or unwanted behaviors.

### Q178. What is responsible disclosure for AI vulnerabilities?

**Responsible disclosure** means reporting AI security issues privately first, giving developers time to fix them before public release.


## Model Evaluation & Benchmarking

### Q179. What is MMLU?

**MMLU** is a test that checks how well AI knows many subjects like science, math, and humanities.

### Q180. What is HELM benchmark?

**HELM** is a benchmark that evaluates AI models in many ways like accuracy, fairness, and safety.

### Q181. What is hallucination detection?

**Hallucination detection** is finding when AI gives false or made-up information.

### Q182. What are automatic evaluation metrics?

**Automatic metrics** are tools like BLEU and ROUGE that measure AI output quality without humans.

### Q183. What is human evaluation in AI?

**Human evaluation** is when people judge how good or accurate AI responses are.

### Q184. What is benchmark gaming?

**Benchmark gaming** is when AI performs well on tests but poorly in real-world use.

### Q185. What is multilingual evaluation?

**Multilingual evaluation** checks how well AI works in different languages.

### Q186. What is robustness testing?

**Robustness testing** checks how well AI performs under difficult or unusual inputs.

---

## Advanced AI Architecture

### Q187. What is serverless AI architecture?

**Serverless AI** uses cloud services where you don’t manage servers directly; it scales automatically.

### Q188. What is edge AI deployment?

**Edge AI** runs AI models on local devices instead of cloud servers for faster and private processing.

### Q189. What is AI microservices architecture?

**AI microservices architecture** breaks AI systems into small independent services that work together.

### Q190. What is AI SaaS architecture?

**AI SaaS** delivers AI features through cloud software that many users can access.

### Q191. What is distributed inference?

**Distributed inference** splits AI processing across multiple machines to handle large workloads.

### Q192. What is model parallelism?

**Model parallelism** splits a large model across multiple devices to run it efficiently.

### Q193. What is data parallelism?

**Data parallelism** runs the same model on different data across multiple devices at the same time.

### Q194. What is pipeline parallelism?

**Pipeline parallelism** splits model layers across devices so data flows through them like a pipeline.

---

## Emerging & Trending Topics

### Q195. What is AI observability in production?

**AI observability** monitors AI systems using logs, metrics, and traces to track performance and issues.

### Q196. What is evaluation frameworks like Evals?

**Evaluation frameworks** are tools used to systematically test and measure AI model performance and safety.

### Q197. What is guardrails-as-code?

**Guardrails-as-code** means writing safety rules as code to automatically control AI behavior.

### Q198. What is AI-assisted code generation?

**AI-assisted code generation** is when AI helps write, fix, or improve software code.

### Q199. What is explainable AI (XAI)?

**Explainable AI (XAI)** makes AI decisions easier for humans to understand.

### Q200. What is the future of AI governance and regulation?

The **future of AI governance** includes stronger global rules and laws to make AI safer, fairer, and more responsible.

=========================================================================




