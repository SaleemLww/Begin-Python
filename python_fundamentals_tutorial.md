# Python Fundamentals: Complete Beginner to Intermediate Course
## Part 1 – Python Fundamentals

---

## Slide 1: Welcome to Python Programming

- Python is a high-level, interpreted programming language
- Known for its simplicity and readability
- Used in web development, data science, AI, automation, and more
- This course will teach you Python from the ground up
- We'll build a strong foundation with hands-on examples

**Speaker Notes:**
Welcome, everyone! I'm excited to guide you through Python Fundamentals. Python is one of the most popular programming languages today, and for good reason—it's easy to learn, yet powerful enough to build complex applications. In this course, we'll start from absolute zero. No prior programming experience is needed. We'll move step by step, explaining each concept clearly, and you'll write real Python code that runs in Google Colab. By the end of this module, you'll have a solid grasp of Python's core concepts, and you'll be ready to tackle more advanced topics. Let's begin!

---

## Slide 2: What is Python and Why It Exists

- Created by Guido van Rossum in the late 1980s
- Designed as a successor to ABC language
- Philosophy: "Readability counts" (The Zen of Python)
- Python emphasizes code clarity and simplicity
- It's an interpreted language, not compiled

**Speaker Notes:**
Python was born out of a desire for a language that’s both powerful and easy to read. Guido van Rossum wanted a language that could be used by beginners yet still handle complex tasks. Python’s design philosophy is captured in "The Zen of Python," which includes principles like "Beautiful is better than ugly" and "Simple is better than complex." Because Python is interpreted, you can write a line of code and immediately see the result, making it great for learning. We'll see that in action with Google Colab.

---

## Slide 3: How Python Code Executes

- Python source code (`.py` files) is read by the interpreter
- The interpreter converts code to bytecode
- Bytecode runs on the Python Virtual Machine (PVM)
- No separate compilation step (unlike C or Java)
- Interactive mode (REPL) lets you execute code line by line

**Speaker Notes:**
Let's demystify how Python works under the hood. When you write a Python script, the interpreter reads your code, translates it into an intermediate form called bytecode, and then the Python Virtual Machine executes that bytecode. This process happens automatically, so you don't need to compile anything manually. That's why you can just open a Colab notebook, type `print("Hello")`, and see the output instantly. We'll use both scripts and the REPL (Read‑Eval‑Print Loop) to get comfortable with both execution styles.

---

## Slide 4: Installing Python & Using REPL vs Scripts

- Python can be installed from python.org or via package managers
- REPL (interactive shell) is great for quick experiments
- Scripts (`.py` files) are for reusable, longer programs
- Google Colab provides a ready‑to‑use Python environment
- We'll use Colab for all examples in this course

**Speaker Notes:**
You have two main ways to run Python: the REPL and script files. The REPL is like a conversation with Python—you type a command, Python responds, and you see the result immediately. It's perfect for testing small ideas. Scripts, on the other hand, are text files containing a sequence of commands; you run the whole file at once. In this course, we'll use Google Colab, which gives you a Python environment in your browser, so you don't need to install anything. Let me show you a quick Colab example.

```python
# This is a Colab cell – try it yourself!
print("Hello, Python!")
x = 5 + 3
print("5 + 3 =", x)
```

---

## Slide 5: Variables – Deep Explanation with Memory Model

- A variable is a named reference to a value stored in memory
- Assignment uses the `=` operator
- Python variables are like sticky notes, not boxes
- Variables can be reassigned to different values
- Variable names must follow naming rules (letters, digits, underscores)

**Speaker Notes:**
Think of a variable as a sticky note that you attach to a value in your computer's memory. When you write `age = 25`, you're not putting 25 inside a box called "age"; you're creating a sticky note labeled "age" that points to the number 25. This subtle difference is important because Python can have multiple sticky notes pointing to the same value. Let's look at a memory diagram and see how assignment works.

```python
# Variable assignment
age = 25
name = "Alice"
temperature = 98.6
is_student = True

# Reassignment
age = 26   # The sticky note moves to a new value
print(age) # Output: 26
```

---

## Slide 6: Dynamic Typing Explained Clearly

- Python is dynamically typed: variable types are determined at runtime
- No need to declare variable types (unlike C or Java)
- The same variable can hold values of different types over time
- Type checking happens when operations are performed
- Use `type()` to inspect the type of any value

**Speaker Notes:**
In statically‑typed languages like Java, you must declare that `age` is an integer before you can use it. Python doesn't require that. When you write `age = 25`, Python figures out that 25 is an integer and treats `age` as an integer variable. Later, you can assign a string to the same variable: `age = "twenty‑five"`. That's dynamic typing—flexible but requiring care. We'll use `type()` to see the current type.

```python
# Dynamic typing in action
value = 10
print(type(value))   # <class 'int'>

value = "ten"
print(type(value))   # <class 'str'>

value = 3.14
print(type(value))   # <class 'float'>
```

---

## Slide 7: Data Types – int, float, bool, str, None

- `int` – whole numbers (e.g., `42`, `-7`, `0`)
- `float` – numbers with decimal points (e.g., `3.14`, `-0.001`)
- `bool` – logical values `True` or `False`
- `str` – text, enclosed in single or double quotes
- `None` – represents "no value" or "null"

**Speaker Notes:**
Python has several built‑in data types that you'll use every day. Integers and floats handle numbers; booleans represent truth values; strings represent text. There's also `None`, which is Python's way of saying "nothing here." Let's look at examples of each type and see how they behave in operations.

```python
# Examples of each data type
integer_example = 42
float_example = 3.14159
boolean_example = True
string_example = "Hello, Python!"
nothing = None

print(integer_example, type(integer_example))
print(float_example, type(float_example))
print(boolean_example, type(boolean_example))
print(string_example, type(string_example))
print(nothing, type(nothing))
```

---

## Slide 8: Strings in Depth – Immutability, Indexing, Slicing

- Strings are immutable: cannot be changed after creation
- Characters can be accessed via zero‑based indexing
- Slicing extracts substrings using `[start:stop:step]`
- Negative indices count from the end of the string
- Common string methods: `.upper()`, `.lower()`, `.strip()`, `.split()`

**Speaker Notes:**
Strings are sequences of characters. Once a string is created, you cannot alter its characters—this is called immutability. But you can create new strings based on the old ones. Indexing lets you grab a single character, while slicing lets you grab a range. We'll practice with some real‑world examples.

```python
text = "Python Programming"

# Indexing
first_char = text[0]   # 'P'
last_char = text[-1]   # 'g'

# Slicing
sub = text[0:6]        # 'Python'
sub2 = text[7:]        # 'Programming'
sub3 = text[::2]       # 'Pto rgamn'

print(first_char, last_char)
print(sub, sub2, sub3)

# String methods
print(text.upper())    # 'PYTHON PROGRAMMING'
print(text.lower())    # 'python programming'
```

---

## Slide 9: type() and id() with Examples

- `type()` returns the class (data type) of an object
- `id()` returns the unique memory address identifier
- Useful for debugging and understanding object identity
- Two variables with the same value may have the same `id` (interning)
- `is` operator compares identities, `==` compares values

**Speaker Notes:**
To peek under Python's hood, we have `type()` and `id()`. `type()` tells you what kind of data you're dealing with. `id()` gives you the memory address where the value is stored—if two variables have the same `id`, they refer to the exact same object in memory. This is key to understanding Python's memory model.

```python
a = 100
b = 100
c = 500
d = 500

print(type(a))          # <class 'int'>
print(id(a), id(b))     # Same id (small integers are interned)
print(id(c), id(d))     # Different ids (larger integers may not be interned)

# Identity vs equality
print(a is b)           # True (same object)
print(c is d)           # False (different objects)
print(c == d)           # True (same value)
```

---

## Slide 10: Operators – Arithmetic, Comparison, Logical, Identity

- Arithmetic: `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulo), `**` (exponent)
- Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical: `and`, `or`, `not`
- Identity: `is`, `is not`
- Membership: `in`, `not in`

**Speaker Notes:**
Operators are symbols that perform operations on values. Arithmetic operators do math; comparison operators compare values; logical operators combine boolean expressions. The identity operators `is` and `is not` check whether two variables refer to the same object, while `in` checks membership in a sequence. Let's try them out.

```python
# Arithmetic
print(10 + 3)   # 13
print(10 / 3)   # 3.333...
print(10 // 3)  # 3 (floor division)
print(10 % 3)   # 1 (remainder)
print(2 ** 4)   # 16 (2 to the power 4)

# Comparison
print(5 > 3)    # True
print(5 == 5.0) # True (value equality)

# Logical
print(True and False)   # False
print(True or False)    # True
print(not True)         # False

# Identity
x = [1,2,3]
y = [1,2,3]
print(x is y)   # False (different objects)
print(x == y)   # True (same contents)
```

---

## Slide 11: Control Flow – if, elif, else, Ternary Operator

- `if` executes a block when a condition is true
- `elif` checks another condition if the previous ones are false
- `else` catches all other cases
- Indentation defines code blocks (no braces!)
- Ternary operator: `value_if_true if condition else value_if_false`

**Speaker Notes:**
Control flow lets your program make decisions. The `if` statement is the most basic building block. Python uses indentation (usually 4 spaces) to group statements together—this is a key part of Python's readability. We'll also look at the concise ternary operator for simple choices.

```python
# if‑elif‑else
temperature = 30

if temperature > 35:
    print("It's hot!")
elif temperature > 20:
    print("It's pleasant.")
else:
    print("It's cold.")

# Ternary example
age = 18
status = "adult" if age >= 18 else "minor"
print(status)   # 'adult'
```

---

## Slide 12: Loops – for, while, range, break, continue

- `for` loop iterates over a sequence (list, string, range, etc.)
- `while` loop repeats as long as a condition is true
- `range()` generates a sequence of numbers
- `break` exits the loop immediately
- `continue` skips the rest of the current iteration

**Speaker Notes:**
Loops automate repetitive tasks. A `for` loop is perfect when you know how many times you want to iterate, or when you have a collection of items. A `while` loop keeps going until a condition becomes false. We'll use `range()` to create numeric sequences, and we'll see how `break` and `continue` give us finer control.

```python
# for loop with range
for i in range(5):
    print(i)   # prints 0,1,2,3,4

# while loop
count = 0
while count < 3:
    print("Counting:", count)
    count += 1

# break and continue
for num in range(10):
    if num == 2:
        continue   # skip 2
    if num == 7:
        break      # stop at 7
    print(num)     # prints 0,1,3,4,5,6
```

---

## Slide 13: Functions – Why They Exist, Syntax, return vs print

- Functions bundle reusable code into a named block
- Defined with `def` keyword, followed by a name and parentheses
- `return` sends a value back to the caller; `print` only displays output
- Functions can accept parameters and return values
- Calling a function executes its code

**Speaker Notes:**
Functions are the building blocks of modular programming. Instead of writing the same code over and over, you define a function once and call it whenever needed. The `def` keyword starts a function definition. Inside, you can use `return` to send a result back to the caller, or `print` to just show something on the screen. Let's compare.

```python
# Function that prints (no return)
def greet(name):
    print("Hello,", name)

greet("Alice")   # Output: Hello, Alice

# Function that returns a value
def add(a, b):
    return a + b

result = add(5, 3)
print(result)    # Output: 8
```

---

## Slide 14: Parameters, Arguments, Default Values

- Parameters are variables listed in the function definition
- Arguments are the actual values passed when calling the function
- Default values allow parameters to be optional
- Positional arguments match by order
- Keyword arguments are specified by parameter name

**Speaker Notes:**
When you define a function, you list its parameters inside the parentheses. When you call the function, you supply arguments. Python lets you assign default values to parameters, making them optional. You can also pass arguments by position or by keyword, which gives you flexibility.

```python
# Function with default parameter
def greet(name, greeting="Hello"):
    print(greeting, name)

greet("Bob")                # Hello Bob
greet("Bob", "Hi")          # Hi Bob

# Keyword arguments
def describe_person(name, age, city):
    print(f"{name} is {age} years old, lives in {city}")

describe_person(age=25, city="NYC", name="Charlie")
```

---

## Slide 15: *args and **kwargs

- `*args` collects extra positional arguments into a tuple
- `**kwargs` collects extra keyword arguments into a dictionary
- Useful for writing flexible functions that accept variable numbers of arguments
- The names `args` and `kwargs` are conventions; you can choose other names
- Can be combined with regular parameters

**Speaker Notes:**
Sometimes you want a function that can accept any number of arguments. That's where `*args` and `**kwargs` come in. The single asterisk `*args` packs positional arguments into a tuple; the double asterisk `**kwargs` packs keyword arguments into a dictionary. This pattern is common in libraries and frameworks.

```python
# Example with *args
def sum_all(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_all(1, 2, 3, 4))   # 10

# Example with **kwargs
def print_profile(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_profile(name="Diana", age=30, city="London")
```

---

## Slide 16: Scope and LEGB Rule

- Scope defines where a variable is accessible
- LEGB: Local → Enclosing → Global → Built‑in
- Variables defined inside a function are local to that function
- `global` keyword allows modifying a global variable inside a function
- `nonlocal` accesses variables from an enclosing (non‑global) scope

**Speaker Notes:**
Python uses the LEGB rule to resolve variable names. It first looks in the Local scope, then in any Enclosing function scopes, then in the Global (module‑level) scope, and finally in the Built‑in scope. Understanding scope prevents bugs where you accidentally refer to the wrong variable. Let's see examples.

```python
x = "global"   # global variable

def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print("inner sees:", x)   # local
    inner()
    print("outer sees:", x)       # enclosing

outer()
print("global sees:", x)          # global

# Using global keyword
def change_global():
    global x
    x = "modified"
change_global()
print(x)   # "modified"
```

---

## Slide 17: Python OOPs Concepts with Examples

- Object‑Oriented Programming (OOP) models real‑world entities as objects
- Class: blueprint for objects; defines attributes and methods
- Object: instance of a class
- Inheritance: child classes inherit from parent classes
- Encapsulation: bundling data with methods that operate on that data
- Polymorphism: same interface for different data types

**Speaker Notes:**
OOP is a paradigm that organizes code around objects. A class is like a cookie cutter; objects are the cookies. Attributes are data stored inside an object; methods are functions that belong to the object. Inheritance lets you create specialized classes that reuse code. Encapsulation hides internal details, and polymorphism lets you treat different kinds of objects uniformly.

```python
# Simple class example
class Dog:
    def __init__(self, name, age):
        self.name = name   # attribute
        self.age = age

    def bark(self):        # method
        print(f"{self.name} says woof!")

# Create an object
my_dog = Dog("Buddy", 3)
my_dog.bark()              # Buddy says woof!
print(my_dog.age)          # 3

# Inheritance example
class Puppy(Dog):
    def play(self):
        print(f"{self.name} is playing!")

pup = Puppy("Max", 1)
pup.bark()   # inherited
pup.play()   # own method
```

---

## Slide 18: Python File System

- The `os` and `shutil` modules provide file‑system operations
- `open()` function reads/writes files; use `with` for automatic cleanup
- Modes: `'r'` read, `'w'` write (overwrites), `'a'` append, `'rb'` binary read
- File paths can be absolute or relative
- Always close files or use context managers

**Speaker Notes:**
Working with files is essential for real‑world programs. Python's built‑in `open()` function gives you a file object. The `with` statement ensures the file is closed properly, even if an error occurs. We'll also look at how to navigate directories, check if a file exists, and copy or delete files.

```python
# Writing to a file
with open("example.txt", "w") as f:
    f.write("Hello, file!\n")
    f.write("This is a second line.")

# Reading from a file
with open("example.txt", "r") as f:
    content = f.read()
    print(content)

# Using os module
import os
print(os.listdir("."))   # list files in current directory
```

---

## Slide 19: Python Database Connectivity (NoSQL, MySQL, Postgres)

- Python supports many databases via drivers
- SQL databases: MySQL (`mysql‑connector‑python`), PostgreSQL (`psycopg2`)
- NoSQL databases: MongoDB (`pymongo`), Redis (`redis`)
- ORMs (Object‑Relational Mappers) like SQLAlchemy abstract SQL
- Basic steps: connect, create cursor, execute query, fetch results, close

**Speaker Notes:**
Python is a great language for database work. For SQL databases, you install a driver, establish a connection, and run SQL commands through a cursor. For NoSQL databases, you use a client library that talks to the database's native API. We'll look at a simple MySQL example and a MongoDB example.

*Note: In Google Colab, run `!pip install mysql‑connector‑python pymongo` before executing these examples.*

```python
# MySQL example (requires mysql‑connector‑python installed)
import mysql.connector

conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="secret",
    database="testdb"
)
cursor = conn.cursor()
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()
for row in rows:
    print(row)
cursor.close()
conn.close()

# MongoDB example (requires pymongo)
from pymongo import MongoClient
client = MongoClient("mongodb://localhost:27017/")
db = client["mydatabase"]
collection = db["users"]
result = collection.find({"age": {"$gt": 20}})
for doc in result:
    print(doc)
```

---

## Slide 20: Introduction to Flask

- Flask is a lightweight web framework for Python
- Ideal for building web applications and APIs
- Routes map URLs to Python functions
- Uses Jinja2 templating for dynamic HTML
- Can be extended with numerous extensions

**Speaker Notes:**
Flask makes it easy to create web applications with minimal boilerplate. You define routes—URLs that trigger Python functions. Those functions return HTML, JSON, or any other HTTP response. Flask is great for beginners because you can start with a few lines of code and gradually add features.

*Note: In Google Colab, run `!pip install flask` before executing this example.*

```python
# A minimal Flask app (install flask first)
from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "<h1>Welcome to my Flask app!</h1>"

@app.route("/hello/<name>")
def hello(name):
    return f"<p>Hello, {name}!</p>"

if __name__ == "__main__":
    app.run(debug=True)
```

---

## Slide 21: One‑Page Web Application Using Python

- Combine Flask with HTML/CSS/JavaScript for a full web app
- Serve static files (CSS, JS) from a `static` folder
- Use templates to separate logic from presentation
- Handle form submissions with `request.form`
- Deploy to platforms like Heroku, PythonAnywhere, or AWS

**Speaker Notes:**
Let's build a simple one‑page app that lets users submit a form and see results. We'll create an HTML template with a form, a Flask route to handle the submission, and some basic styling. This will show you how front‑end and back‑end work together.

*Note: Ensure you have Flask installed (`!pip install flask`). Also create a `templates` folder in Colab for the HTML file.*

```python
# app.py
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/", methods=["GET", "POST"])
def index():
    message = ""
    if request.method == "POST":
        name = request.form.get("name")
        message = f"Hello, {name}!"
    return render_template("index.html", message=message)

if __name__ == "__main__":
    app.run(debug=True)
```

```html
<!-- templates/index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Greeting App</title>
</head>
<body>
    <h1>Enter your name</h1>
    <form method="POST">
        <input type="text" name="name" placeholder="Your name">
        <button type="submit">Submit</button>
    </form>
    {% if message %}
        <h2>{{ message }}</h2>
    {% endif %}
</body>
</html>
```

---

## Slide 22: Introduction to FastAPI

- FastAPI is a modern, fast web framework for building APIs
- Built on Starlette and Pydantic; supports async/await
- Automatic interactive API documentation (Swagger UI)
- Type‑hint driven request/response validation
- High performance, comparable to Node.js and Go

**Speaker Notes:**
FastAPI is a newer framework that's gaining rapid adoption, especially for APIs. It uses Python type hints to automatically validate request data and generate OpenAPI documentation. It's also very fast because it's built on async foundations. Let's create a simple API endpoint.

*Note: In Google Colab, run `!pip install fastapi uvicorn` before executing this example.*

```python
# Install fastapi and uvicorn first
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI!"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

Run with: `uvicorn main:app --reload`

---

## Slide 23: Creating RESTful APIs

- REST (Representational State Transfer) is an architectural style
- Uses HTTP methods: GET (read), POST (create), PUT (update), DELETE (delete)
- Resources are identified by URLs
- Stateless communication; each request contains all needed information
- Return data typically in JSON format

**Speaker Notes:**
RESTful APIs are the standard way for applications to communicate over HTTP. We'll design a simple API for a todo list, implementing all four CRUD operations. We'll use Flask for this example, but the same principles apply to FastAPI or any other framework.

*Note: This example requires Flask (`!pip install flask`).*

```python
from flask import Flask, jsonify, request

app = Flask(__name__)
todos = []

@app.route("/todos", methods=["GET"])
def get_todos():
    return jsonify(todos)

@app.route("/todos", methods=["POST"])
def add_todo():
    new_todo = request.json
    todos.append(new_todo)
    return jsonify(new_todo), 201

@app.route("/todos/<int:index>", methods=["DELETE"])
def delete_todo(index):
    if 0 <= index < len(todos):
        deleted = todos.pop(index)
        return jsonify(deleted), 200
    return jsonify({"error": "Not found"}), 404
```

---

## Slide 24: Introduction to Python Microservices

- Microservices architecture splits an application into small, independent services
- Each service runs in its own process and communicates via lightweight protocols (HTTP, gRPC)
- Benefits: scalability, independent deployment, technology diversity
- Challenges: network latency, data consistency, operational complexity
- Python frameworks like FastAPI, Flask, Nameko are commonly used

**Speaker Notes:**
Instead of building one monolithic application, you can build a set of microservices. Each service handles a specific business capability (e.g., user authentication, payment processing). They talk to each other over the network, usually via HTTP REST or gRPC. Python's ease of development makes it a popular choice for microservices.

*Note: This example requires FastAPI and Pydantic (`!pip install fastapi pydantic`).*

```python
# Example: a simple user service with FastAPI
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    id: int
    name: str
    email: str

users_db = []

@app.post("/users/")
def create_user(user: User):
    users_db.append(user)
    return {"message": "User created", "user": user}

@app.get("/users/{user_id}")
def get_user(user_id: int):
    for user in users_db:
        if user.id == user_id:
            return user
    return {"error": "User not found"}
```

---

## Slide 25: Creating Login Authentication Microservice

- Authentication verifies user identity (who you are)
- Authorization determines permissions (what you can do)
- Common methods: password‑based, token‑based (JWT), OAuth
- Store passwords securely using hashing (bcrypt, argon2)
- Use environment variables for secrets (never hard‑code)

**Speaker Notes:**
Let's build a microservice that handles user registration and login. We'll store users in a dictionary (in real life, a database), hash passwords with bcrypt, and issue JSON Web Tokens (JWT) for authenticated sessions. This service can be consumed by a front‑end or other microservices.

*Note: This example requires PyJWT and bcrypt (`!pip install pyjwt bcrypt`).*

```python
# Install pyjwt and bcrypt
import jwt
import bcrypt
from datetime import datetime, timedelta
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

app = FastAPI()
SECRET_KEY = "your‑secret‑key"   # In production, use environment variable

class UserRegister(BaseModel):
    username: str
    password: str

users = {}

@app.post("/register")
def register(user: UserRegister):
    if user.username in users:
        raise HTTPException(status_code=400, detail="Username already exists")
    # Hash password
    hashed = bcrypt.hashpw(user.password.encode(), bcrypt.gensalt())
    users[user.username] = hashed
    return {"message": "User registered"}

@app.post("/login")
def login(user: UserRegister):
    stored_hash = users.get(user.username)
    if not stored_hash or not bcrypt.checkpw(user.password.encode(), stored_hash):
        raise HTTPException(status_code=401, detail="Invalid credentials")
    # Create JWT token
    token = jwt.encode(
        {"username": user.username, "exp": datetime.utcnow() + timedelta(hours=1)},
        SECRET_KEY,
        algorithm="HS256"
    )
    return {"token": token}
```

---

## Slide 26: Securing Microservices

- Use HTTPS to encrypt traffic
- Validate and sanitize all inputs to prevent injection attacks
- Implement rate limiting to protect against DoS
- Use API keys or OAuth for service‑to‑service authentication
- Monitor and log access for security auditing

**Speaker Notes:**
Security is critical in a microservices architecture because each service is exposed over the network. We need to ensure that only authorized clients can call our services, that data is encrypted in transit, and that common vulnerabilities like SQL injection or XSS are prevented. We'll discuss best practices and tools that help.

*Note: This example requires slowapi (`!pip install slowapi`).*

```python
# Example: adding rate limiting with slowapi
from slowapi import Limiter, _rate_limit_exceeded_handler
from slowapi.util import get_remote_address
from fastapi import FastAPI, Request

limiter = Limiter(key_func=get_remote_address)
app = FastAPI()
app.state.limiter = limiter
app.add_exception_handler(429, _rate_limit_exceeded_handler)

@app.get("/protected")
@limiter.limit("5/minute")
def protected_route(request: Request):
    return {"message": "You are within rate limit"}
```

---

## Slide 27: Common Beginner Mistakes & Best Practices

- Forgetting colons at the end of `if`, `def`, `for`, etc.
- Mixing tabs and spaces (use 4 spaces consistently)
- Using `==` instead of `is` for identity comparisons
- Modifying a list while iterating over it
- Not closing files or database connections
- Best practice: write readable code, use meaningful names, add comments, write tests

**Speaker Notes:**
Everyone makes mistakes when learning. The key is to recognize them early and develop good habits. We'll go through a checklist of common pitfalls and how to avoid them. We'll also talk about Pythonic ways of writing code—embracing Python's philosophy to write clear, maintainable programs.

```python
# Common mistake: mutable default argument
def add_item(item, lst=[]):   # Danger: default list is shared across calls!
    lst.append(item)
    return lst

# Fix: use None as default
def add_item(item, lst=None):
    if lst is None:
        lst = []
    lst.append(item)
    return lst

# Best practice: use list comprehensions
numbers = [1, 2, 3, 4]
squares = [n**2 for n in numbers]   # instead of a manual loop
```

---

## Slide 28: Course Wrap‑Up & Next Steps

- You've learned Python fundamentals: variables, types, control flow, functions, OOP, file I/O, databases, web frameworks, APIs, microservices
- Practice is essential – write code daily, solve problems on platforms like LeetCode, HackerRank
- Explore advanced topics: data science (pandas, NumPy), machine learning (scikit‑learn, TensorFlow), DevOps (Docker, CI/CD)
- Join the Python community: PyCon, local meetups, online forums
- Keep learning and building projects!

**Speaker Notes:**
Congratulations! You've completed Part 1 of our Python course. You now have a strong foundation to tackle real‑world projects. Remember, programming is a skill that improves with practice. Don't be afraid to make mistakes—they're part of the learning process. In the next module, we'll dive deeper into data structures, algorithms, and more advanced Python features. Thank you for joining, and happy coding!

---

## Appendix: Google Colab Quick Start

- Open [colab.research.google.com](https://colab.research.google.com)
- Click "New Notebook"
- Type Python code in cells and press Shift+Enter to run
- Use `!pip install` to install packages
- Save your notebook to Google Drive

**Speaker Notes:**
If you haven't used Colab before, here's a quick guide. Colab gives you a free Python environment with GPU/TPU support. You can write code in cells, run them, and see output immediately. It's perfect for following along with this course. Let's install a package as an example.

```python
!pip install numpy pandas   # Installs numpy and pandas
import numpy as np
arr = np.array([1,2,3])
print(arr)
```

---

*End of Part 1 – Python Fundamentals*
