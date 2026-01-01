# Python Data Structures & Functional Programming: Complete Intermediate Course
## Part 2 – Python Data Structures & Functional Programming

---

## Slide 1: Welcome to Data Structures & Functional Programming

- Building on Python fundamentals to master intermediate concepts
- Data structures organize and store data efficiently
- Functional programming emphasizes pure functions and immutability
- This module bridges basic Python to advanced programming
- Real-world applications: data analysis, web development, automation

**Speaker Notes:**
Welcome back! In Part 1, you learned Python's fundamentals. Now, we dive deeper into how Python handles data organization and functional programming paradigms. Data structures are the backbone of efficient programs—they determine how quickly you can search, sort, and manipulate data. Functional programming, on the other hand, offers a different mindset: treating computation as evaluation of mathematical functions. By the end of this module, you'll be able to choose the right data structure for any problem and write cleaner, more maintainable code using functional techniques. Let's get started!

---

## Slide 2: Lists – Python's Workhorse Data Structure

- Ordered, mutable sequences of items
- Created with square brackets: `[1, 2, 3]` or `list()`
- Zero‑based indexing: `my_list[0]` gets first element
- Slicing: `my_list[start:stop:step]` extracts sublists
- Common methods: `.append()`, `.extend()`, `.insert()`, `.remove()`, `.pop()`

**Speaker Notes:**
Lists are Python's most versatile data structure. They can hold any type of object, they're mutable (you can change them after creation), and they maintain insertion order. Understanding lists deeply is crucial because many other data structures build on similar concepts. Let's explore creation, indexing, slicing, and essential methods with practical examples.

```python
# Creating lists
numbers = [1, 2, 3, 4, 5]
mixed = [10, "hello", 3.14, True]
empty = []
from_range = list(range(5))  # [0, 1, 2, 3, 4]

# Indexing and slicing
print(numbers[0])      # 1 (first element)
print(numbers[-1])     # 5 (last element)
print(numbers[1:4])    # [2, 3, 4] (slice from index 1 to 3)
print(numbers[::2])    # [1, 3, 5] (every second element)

# List methods
numbers.append(6)      # [1, 2, 3, 4, 5, 6]
numbers.insert(2, 99)  # [1, 2, 99, 3, 4, 5, 6]
numbers.remove(99)     # [1, 2, 3, 4, 5, 6]
last = numbers.pop()   # last = 6, numbers = [1, 2, 3, 4, 5]
```

---

## Slide 3: Tuples – Immutable Sequences

- Ordered, immutable sequences: cannot be changed after creation
- Created with parentheses: `(1, 2, 3)` or `tuple()`
- Single‑element tuple requires a trailing comma: `(42,)`
- Use cases: fixed collections, dictionary keys, function returns
- Faster than lists for iteration and memory‑efficient

**Speaker Notes:**
Tuples are like lists but immutable. Once created, you cannot add, remove, or modify elements. This immutability makes tuples suitable for representing fixed data (like coordinates, RGB colors, or database records) and for use as dictionary keys (which must be immutable). Tuples also convey semantic meaning: "this collection shouldn't change." Let's compare tuples with lists and see real‑world examples.

```python
# Creating tuples
point = (10, 20)
rgb = (255, 0, 0)
single = (5,)          # Note the comma
empty_tuple = ()
from_list = tuple([1, 2, 3])  # (1, 2, 3)

# Accessing elements (same as lists)
print(point[0])        # 10
print(rgb[1:])         # (0, 0)  (slicing returns a new tuple)

# Tuples are immutable – this will raise an error:
# point[0] = 100       # TypeError: 'tuple' object does not support item assignment

# Real‑world example: returning multiple values from a function
def get_user_info():
    name = "Alice"
    age = 30
    city = "New York"
    return name, age, city   # Returns a tuple (name, age, city)

user_data = get_user_info()
print(user_data)             # ('Alice', 30, 'New York')
name, age, city = user_data  # Tuple unpacking
print(f"{name} is {age} years old from {city}")
```

---

## Slide 4: Sets – Unordered Unique Collections

- Unordered collection of unique elements (no duplicates)
- Created with curly braces: `{1, 2, 3}` or `set()`
- Mutable: can add/remove elements
- Mathematical set operations: union, intersection, difference
- Use cases: removing duplicates, membership testing, mathematical operations

**Speaker Notes:**
Sets are perfect when you need to ensure uniqueness or perform set‑theoretic operations. They're unordered, so you cannot access elements by index. Sets are implemented using hash tables, making membership tests (`element in set`) extremely fast—O(1) on average. We'll explore common set operations and when to prefer sets over lists.

```python
# Creating sets
unique_numbers = {1, 2, 3, 4, 5}
duplicate_list = [1, 2, 2, 3, 3, 3]
unique_from_list = set(duplicate_list)  # {1, 2, 3}
empty_set = set()                       # NOT {} (that's an empty dict)

# Set operations
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A | B)   # Union: {1, 2, 3, 4, 5, 6}
print(A & B)   # Intersection: {3, 4}
print(A - B)   # Difference (in A but not B): {1, 2}
print(A ^ B)   # Symmetric difference (elements in either but not both): {1, 2, 5, 6}

# Practical example: removing duplicates from a list
emails = ["alice@example.com", "bob@example.com", "alice@example.com", "charlie@example.com"]
unique_emails = list(set(emails))  # Convert to set and back to list
print(unique_emails)               # Order may change (sets are unordered)

# Membership test (fast!)
if "alice@example.com" in set(emails):
    print("Alice is in the list")
```

---

## Slide 5: Dictionaries – Key‑Value Mapping

- Unordered collection of key‑value pairs
- Created with curly braces and colons: `{"key": "value"}` or `dict()`
- Keys must be immutable (strings, numbers, tuples); values can be anything
- Fast lookups by key (O(1) average)
- Methods: `.keys()`, `.values()`, `.items()`, `.get()`, `.update()`

**Speaker Notes:**
Dictionaries are Python's implementation of hash tables. They map unique keys to values, allowing you to retrieve a value instantly if you know its key. Dictionaries are ubiquitous in Python—they're used for configuration, JSON data, caches, and more. We'll learn how to create, iterate, and manipulate dictionaries effectively.

```python
# Creating dictionaries
person = {"name": "Alice", "age": 30, "city": "New York"}
empty_dict = {}
from_pairs = dict([("name", "Bob"), ("age", 25)])  # {'name': 'Bob', 'age': 25}

# Accessing values
print(person["name"])          # Alice
print(person.get("age"))       # 30
print(person.get("country", "USA"))  # USA (default if key missing)

# Adding/updating
person["email"] = "alice@example.com"   # Add new key
person["age"] = 31                      # Update existing key

# Iterating
for key in person:
    print(key, person[key])

for key, value in person.items():
    print(f"{key}: {value}")

# Real‑world example: counting word frequencies
text = "apple banana apple orange banana apple"
words = text.split()
word_count = {}
for word in words:
    word_count[word] = word_count.get(word, 0) + 1
print(word_count)  # {'apple': 3, 'banana': 2, 'orange': 1}
```

---

## Slide 6: Mutability vs Immutability Deep Dive

- Mutable objects can be changed after creation (lists, dicts, sets)
- Immutable objects cannot be changed (ints, floats, strings, tuples)
- Implications for assignment, function arguments, and memory
- Python's memory model: variables as references
- `id()` function reveals object identity

**Speaker Notes:**
Understanding mutability is critical for writing correct Python code. Mutable objects can lead to unexpected side‑effects when shared between variables or passed to functions. Immutable objects are safe to share because they cannot be altered. We'll examine Python's memory model with diagrams and see how mutability affects common operations.

```python
# Immutable example: integers
a = 10
b = a          # b references the same 10
print(id(a), id(b))  # Same id
a = 20         # a now references a new object 20
print(a, b)    # 20, 10 (b unchanged)

# Mutable example: lists
list1 = [1, 2, 3]
list2 = list1   # list2 references the same list object
list1.append(4)
print(list2)    # [1, 2, 3, 4] (list2 sees the change!)

# Function arguments: mutable vs immutable
def modify_immutable(x):
    x = x + 1   # Creates a new integer
    print("Inside function:", x)

def modify_mutable(lst):
    lst.append(99)
    print("Inside function:", lst)

num = 5
modify_immutable(num)
print("Outside:", num)   # Still 5

my_list = [1, 2]
modify_mutable(my_list)
print("Outside:", my_list)  # [1, 2, 99] (changed!)

# Safe practice: create copies
list3 = [1, 2, 3]
list4 = list3.copy()      # Shallow copy
list3.append(4)
print(list3, list4)       # [1, 2, 3, 4] vs [1, 2, 3]
```

---

## Slide 7: Comprehensions – Elegant Data Transformation

- List comprehensions: `[expression for item in iterable if condition]`
- Dictionary comprehensions: `{key: value for item in iterable}`
- Set comprehensions: `{expression for item in iterable}`
- More readable and often faster than explicit loops
- Can be nested for multi‑dimensional transformations

**Speaker Notes:**
Comprehensions are a Pythonic way to create new collections by transforming or filtering existing ones. They're concise, expressive, and often more efficient than equivalent `for` loops. We'll start with simple comprehensions and gradually build to more complex ones, showing how they replace common loop patterns.

```python
# List comprehension: squares of even numbers
numbers = [1, 2, 3, 4, 5, 6]
squares = [n**2 for n in numbers if n % 2 == 0]
print(squares)  # [4, 16, 36]

# Equivalent loop:
squares_loop = []
for n in numbers:
    if n % 2 == 0:
        squares_loop.append(n**2)

# Dictionary comprehension: mapping names to lengths
names = ["Alice", "Bob", "Charlie"]
name_lengths = {name: len(name) for name in names}
print(name_lengths)  # {'Alice': 5, 'Bob': 3, 'Charlie': 7}

# Set comprehension: unique first letters
first_letters = {name[0] for name in names}
print(first_letters)  # {'A', 'B', 'C'}

# Nested comprehension: matrix flattening
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [num for row in matrix for num in row]
print(flattened)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Real‑world example: filtering data
temperatures = [22.5, 18.0, 25.5, 30.0, 15.5, 28.0]
hot_days = [temp for temp in temperatures if temp > 25]
print(f"Hot days: {hot_days}")  # [25.5, 30.0, 28.0]
```

---

## Slide 8: Nested Data Structures

- Lists of lists (2D arrays), lists of dicts, dicts of lists, etc.
- Representing complex real‑world data (JSON‑like structures)
- Accessing nested elements with multiple indices/keys
- Modifying nested mutable objects requires careful reference handling
- Common patterns: configuration trees, hierarchical data, matrices

**Speaker Notes:**
Real‑world data is rarely flat. You'll often encounter lists containing dictionaries, dictionaries containing lists, and deeper nesting. Understanding how to navigate and modify these structures is essential for working with APIs, configuration files, and complex algorithms. We'll practice with examples inspired by real applications.

```python
# List of dictionaries (common in JSON APIs)
students = [
    {"name": "Alice", "grades": [85, 90, 88]},
    {"name": "Bob", "grades": [78, 82, 80]},
    {"name": "Charlie", "grades": [92, 95, 90]}
]

# Accessing nested data
alice_grades = students[0]["grades"]
print(alice_grades)          # [85, 90, 88]
print(alice_grades[1])       # 90

# Modifying nested structures
students[1]["grades"].append(85)  # Add a new grade for Bob
print(students[1])

# Dictionary of lists
classroom = {
    "math": ["Alice", "Bob"],
    "science": ["Charlie", "Alice"],
    "history": ["Bob", "Charlie"]
}

# Adding a student to math class
classroom["math"].append("Diana")

# Complex nesting: company organizational chart
company = {
    "name": "TechCorp",
    "departments": {
        "engineering": {
            "manager": "Alice",
            "employees": ["Bob", "Charlie", "Diana"]
        },
        "sales": {
            "manager": "Eve",
            "employees": ["Frank", "Grace"]
        }
    }
}

# Access deep nested value
eng_employees = company["departments"]["engineering"]["employees"]
print(eng_employees)  # ['Bob', 'Charlie', 'Diana']

# Real‑world example: processing nested JSON‑like data
for dept_name, dept_info in company["departments"].items():
    print(f"{dept_name}: {len(dept_info['employees'])} employees")
```

---

## Slide 9: Common Mistakes with Data Structures

- Modifying a list while iterating over it
- Using mutable default arguments in functions
- Confusing `==` with `is` for identity comparison
- Assuming dictionary order (pre‑Python 3.7)
- Forgetting that sets are unordered and cannot contain mutable items
- Shallow vs deep copy confusion

**Speaker Notes:**
Even experienced developers make these mistakes. Recognizing them early will save you hours of debugging. We'll examine each pitfall, understand why it happens, and learn the correct approach. We'll also discuss Pythonic solutions and best practices to avoid these issues.

```python
# Mistake 1: Modifying list while iterating
numbers = [1, 2, 3, 4, 5]
# WRONG:
# for num in numbers:
#     if num % 2 == 0:
#         numbers.remove(num)  # Changes list size during iteration
# CORRECT:
numbers = [num for num in numbers if num % 2 != 0]  # Use comprehension
print(numbers)  # [1, 3, 5]

# Mistake 2: Mutable default argument
def add_item(item, lst=[]):   # DANGER: default list is shared!
    lst.append(item)
    return lst

print(add_item(1))  # [1]
print(add_item(2))  # [1, 2] (unexpected!)

# FIX: Use None as default
def add_item_safe(item, lst=None):
    if lst is None:
        lst = []
    lst.append(item)
    return lst

# Mistake 3: == vs is
a = [1, 2, 3]
b = [1, 2, 3]
print(a == b)   # True (same values)
print(a is b)   # False (different objects)

# Mistake 4: Assuming dictionary order (only guaranteed from Python 3.7+)
# If you need ordered dict, use collections.OrderedDict

# Mistake 5: Trying to put mutable items in a set
# my_set = {[1, 2]}  # TypeError: unhashable type: 'list'

# Mistake 6: Shallow copy vs deep copy
import copy
original = [[1, 2], [3, 4]]
shallow = original.copy()
deep = copy.deepcopy(original)

original[0].append(99)
print("Original:", original)   # [[1, 2, 99], [3, 4]]
print("Shallow:", shallow)     # [[1, 2, 99], [3, 4]] (affected!)
print("Deep:", deep)           # [[1, 2], [3, 4]] (unchanged)
```

---

## Slide 10: Functions Recap – Functional Mindset

- Functions as first‑class objects: can be assigned, passed as arguments, returned
- Pure functions: no side‑effects, same input → same output
- Higher‑order functions: accept or return other functions
- Recursion as an alternative to iteration
- Functional programming emphasizes immutability and declarative style

**Speaker Notes:**
In Part 1, we learned function syntax. Now we shift perspective: think of functions as values, not just code blocks. This functional mindset leads to more modular, testable code. Pure functions are easier to reason about because they don't depend on or modify external state. Higher‑order functions enable powerful patterns like decorators and callbacks. We'll revisit functions with this new lens.

```python
# Functions as first‑class objects
def greet(name):
    return f"Hello, {name}!"

# Assign function to a variable
my_func = greet
print(my_func("Alice"))  # Hello, Alice!

# Pass function as argument
def apply_twice(func, value):
    return func(func(value))

def add_exclamation(text):
    return text + "!"

print(apply_twice(add_exclamation, "Hi"))  # Hi!!

# Return function from function
def make_multiplier(factor):
    def multiplier(x):
        return x * factor
    return multiplier

double = make_multiplier(2)
triple = make_multiplier(3)
print(double(5))   # 10
print(triple(5))   # 15

# Pure function example (no side‑effects)
def pure_add(a, b):
    return a + b   # Only depends on inputs, no external state

# Impure function (has side‑effect)
total = 0
def impure_add(a):
    global total
    total += a     # Modifies external variable
    return total
```

---

## Slide 11: Lambda Functions – Anonymous One‑Liners

- Lambda functions are small, anonymous functions defined with `lambda`
- Syntax: `lambda arguments: expression`
- Limited to a single expression (no statements, no `return` keyword)
- Often used with `map()`, `filter()`, `sorted()` for concise transformations
- Best for simple operations; use `def` for complex logic

**Speaker Notes:**
Lambda functions are Python's way of creating quick, throw‑away functions without the ceremony of `def`. They're perfect when you need a simple function for a short period, like as an argument to `sorted()`. However, they can become hard to read if overused. We'll see practical examples and learn when to prefer lambdas over regular functions.

```python
# Basic lambda
add = lambda x, y: x + y
print(add(3, 5))   # 8

# Equivalent regular function
def add_regular(x, y):
    return x + y

# Common use: sorting with a custom key
students = [
    {"name": "Alice", "grade": 85},
    {"name": "Bob", "grade": 92},
    {"name": "Charlie", "grade": 78}
]

# Sort by grade (ascending)
students_sorted = sorted(students, key=lambda s: s["grade"])
print([s["name"] for s in students_sorted])  # ['Charlie', 'Alice', 'Bob']

# Sort by name length
students_sorted_by_len = sorted(students, key=lambda s: len(s["name"]))
print([s["name"] for s in students_sorted_by_len])  # ['Bob', 'Alice', 'Charlie']

# Use with map() and filter()
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # [1, 4, 9, 16, 25]

evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)    # [2, 4]

# When NOT to use lambda (complex logic)
# BAD: lambda x: (x**2 if x > 0 else 0) + (x*2 if x < 10 else x)
# GOOD: Use a regular function with clear logic
```

---

## Slide 12: map(), filter(), reduce() – Functional Tools

- `map(function, iterable)`: applies function to each item, returns iterator
- `filter(function, iterable)`: keeps items where function returns `True`
- `reduce(function, iterable)`: cumulatively applies function (from `functools`)
- These are functional programming staples that avoid explicit loops
- Often combined with lambda functions for concise code

**Speaker Notes:**
`map`, `filter`, and `reduce` come from functional programming languages. They encourage thinking in terms of transformations and filters rather than step‑by‑step loops. While list comprehensions often achieve the same result more Pythonically, understanding these functions is valuable for reading other people's code and for situations where lazy evaluation matters.

```python
from functools import reduce

# map() – transform each element
numbers = [1, 2, 3, 4]
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)  # [2, 4, 6, 8]

# Equivalent list comprehension
doubled_comp = [x * 2 for x in numbers]

# filter() – select elements meeting a condition
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)    # [2, 4]

# Equivalent list comprehension
evens_comp = [x for x in numbers if x % 2 == 0]

# reduce() – cumulative operation
sum_all = reduce(lambda acc, x: acc + x, numbers, 0)
print(sum_all)  # 10 (1+2+3+4)

product = reduce(lambda acc, x: acc * x, numbers, 1)
print(product)  # 24 (1*2*3*4)

# Real‑world example: processing data pipeline
data = [10, 15, 20, 25, 30]
# Step 1: filter values > 15
filtered = filter(lambda x: x > 15, data)
# Step 2: map to percentage
percentages = map(lambda x: x / 100, filtered)
# Step 3: reduce to average
from functools import reduce
avg = reduce(lambda acc, x: acc + x, percentages, 0) / len(list(percentages))
# Note: careful with iterator consumption!

# Modern Python often uses comprehensions instead
filtered_comp = [x for x in data if x > 15]
percentages_comp = [x/100 for x in filtered_comp]
avg_comp = sum(percentages_comp) / len(percentages_comp)
```

---

## Slide 13: Error Handling – try, except, finally

- `try` block contains code that might raise an exception
- `except` catches specific exceptions and handles them
- `else` runs if no exception occurred (optional)
- `finally` always executes, used for cleanup (closing files, releasing resources)
- Built‑in exception hierarchy: `BaseException` ← `Exception` ← more specific types

**Speaker Notes:**
Exceptions are Python's way of signaling errors. Instead of letting your program crash, you can catch exceptions and handle them gracefully. The `try‑except` construct is fundamental to robust code. We'll learn how to catch specific exceptions, create custom error messages, and ensure cleanup with `finally`. Proper error handling separates amateur code from professional code.

```python
# Basic try‑except
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")

# Multiple except blocks
try:
    value = int("not_a_number")
    result = 10 / value
except ValueError:
    print("Invalid integer conversion")
except ZeroDivisionError:
    print("Division by zero")
except Exception as e:  # Catch any other exception
    print(f"Unexpected error: {e}")

# else and finally
def divide(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        print("Division by zero attempted")
        return None
    else:
        print(f"Division successful: {result}")
        return result
    finally:
        print("This always runs, even after return")

print(divide(10, 2))   # Successful case
print(divide(10, 0))   # Error case

# Real‑world example: file operations with error handling
def read_file_safely(filename):
    try:
        with open(filename, 'r') as f:
            content = f.read()
    except FileNotFoundError:
        print(f"File {filename} not found")
        return ""
    except PermissionError:
        print(f"No permission to read {filename}")
        return ""
    except Exception as e:
        print(f"Unexpected error reading file: {e}")
        return ""
    else:
        print(f"Successfully read {len(content)} characters")
        return content
    finally:
        print(f"Attempted to read {filename}")

# Using the function
data = read_file_safely("example.txt")
```

---

## Slide 14: Custom Exceptions – Domain‑Specific Errors

- Create custom exception classes by inheriting from `Exception`
- Add custom attributes and methods for richer error information
- Raise custom exceptions with `raise CustomException("message")`
- Organize exceptions in a hierarchy for granular catching
- Document custom exceptions in docstrings and module documentation

**Speaker Notes:**
Built‑in exceptions cover general errors, but your application may have domain‑specific errors. Creating custom exceptions makes your code more expressive and easier to debug. For example, a banking app might have `InsufficientFundsError` or a web scraper might have `PageNotFoundError`. We'll design a custom exception hierarchy and see how to use it effectively.

```python
# Basic custom exception
class ValidationError(Exception):
    """Raised when input validation fails."""
    pass

# Custom exception with additional attributes
class AccountError(Exception):
    """Base class for account‑related errors."""
    pass

class InsufficientFundsError(AccountError):
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount
        message = f"Insufficient funds: ${balance} available, tried to withdraw ${amount}"
        super().__init__(message)

class AccountClosedError(AccountError):
    pass

# Using custom exceptions
class BankAccount:
    def __init__(self, balance):
        self.balance = balance
        self.is_open = True
    
    def withdraw(self, amount):
        if not self.is_open:
            raise AccountClosedError("Cannot withdraw from closed account")
        if amount > self.balance:
            raise InsufficientFundsError(self.balance, amount)
        self.balance -= amount
        return self.balance

# Client code with proper error handling
account = BankAccount(100)
try:
    account.withdraw(150)
except InsufficientFundsError as e:
    print(f"Withdrawal failed: {e}")
    print(f"Balance was ${e.balance}, tried to withdraw ${e.amount}")
except AccountClosedError:
    print("Account is closed")
except AccountError:
    print("Some other account error occurred")

# Real‑world example: API client with custom exceptions
class APIError(Exception):
    """Base exception for API‑related errors."""
    def __init__(self, status_code, message):
        self.status_code = status_code
        self.message = message
        super().__init__(f"API Error {status_code}: {message}")

class NotFoundError(APIError):
    """Raised when resource is not found (404)."""
    pass

class RateLimitError(APIError):
    """Raised when rate limit is exceeded (429)."""
    pass

def fetch_user_data(user_id):
    # Simulate API call
    if user_id == 999:
        raise NotFoundError(404, f"User {user_id} not found")
    elif user_id == 777:
        raise RateLimitError(429, "Too many requests")
    return {"id": user_id, "name": "Alice"}
```

---

## Slide 15: File Handling – Working with Text Files

- `open()` function returns a file object with read/write methods
- Modes: `'r'` read, `'w'` write (overwrites), `'a'` append, `'x'` exclusive create
- Text mode (default) vs binary mode (`'rb'`, `'wb'`)
- Always close files or use `with` statement for automatic cleanup
- Common methods: `.read()`, `.readline()`, `.readlines()`, `.write()`, `.writelines()`

**Speaker Notes:**
Reading and writing files is essential for persistent data storage. Python's file API is straightforward but has nuances. The `with` statement is your best friend—it ensures files are closed properly even if an error occurs. We'll practice reading files line by line (memory‑efficient for large files) and writing data in various formats.

```python
# Writing to a file
with open("example.txt", "w") as f:
    f.write("Hello, World!\n")
    f.write("This is line two.\n")
    lines = ["Line three\n", "Line four\n"]
    f.writelines(lines)

# Reading entire file
with open("example.txt", "r") as f:
    content = f.read()
    print("Full content:")
    print(content)

# Reading line by line (memory‑efficient for large files)
with open("example.txt", "r") as f:
    print("\nLine by line:")
    for line_num, line in enumerate(f, 1):
        print(f"{line_num}: {line.rstrip()}")  # rstrip removes trailing newline

# Reading all lines into a list
with open("example.txt", "r") as f:
    lines = f.readlines()
    print(f"\nTotal lines: {len(lines)}")

# Appending to a file
with open("example.txt", "a") as f:
    f.write("Appended line.\n")

# Real‑world example: processing a log file
def analyze_log_file(filename):
    error_count = 0
    warning_count = 0
    with open(filename, "r") as log:
        for line in log:
            if "ERROR" in line:
                error_count += 1
            elif "WARNING" in line:
                warning_count += 1
    return error_count, warning_count

# Simulate log file creation
with open("app.log", "w") as log:
    log.write("2024‑01‑01 INFO: Application started\n")
    log.write("2024‑01‑01 WARNING: High memory usage\n")
    log.write("2024‑01‑01 ERROR: Database connection failed\n")
    log.write("2024‑01‑01 INFO: Retrying connection\n")

errors, warnings = analyze_log_file("app.log")
print(f"\nLog analysis: {errors} errors, {warnings} warnings")

# File existence check (using os.path)
import os
if os.path.exists("example.txt"):
    print("File exists")
else:
    print("File does not exist")
```

---

## Slide 16: Working with CSV and JSON

- CSV (Comma‑Separated Values): tabular data format
- Use `csv` module for reading/writing CSV files
- JSON (JavaScript Object Notation): hierarchical data format
- Use `json` module for parsing and serializing JSON
- Both are standard formats for data exchange between systems

**Speaker Notes:**
CSV and JSON are the workhorses of data interchange. CSV is great for
spreadsheet‑like data, while JSON excels at nested, hierarchical data (like API responses). Python's standard library includes excellent modules for both. We'll learn how to read, write, and manipulate these formats with practical examples.

```python
import csv
import json

# CSV Writing
data = [
    ["Name", "Age", "City"],
    ["Alice", 30, "New York"],
    ["Bob", 25, "London"],
    ["Charlie", 35, "Paris"]
]

with open("people.csv", "w", newline="") as csvfile:
    writer = csv.writer(csvfile)
    writer.writerows(data)

# CSV Reading
with open("people.csv", "r") as csvfile:
    reader = csv.reader(csvfile)
    print("CSV Contents:")
    for row in reader:
        print(row)

# CSV with DictReader/DictWriter (more convenient)
with open("people.csv", "r") as csvfile:
    reader = csv.DictReader(csvfile)
    print("\nCSV as dictionaries:")
    for row in reader:
        print(f"{row['Name']} is {row['Age']} years old in {row['City']}")

# JSON Writing
person = {
    "name": "Alice",
    "age": 30,
    "city": "New York",
    "hobbies": ["reading", "hiking", "coding"],
    "employed": True
}

with open("person.json", "w") as jsonfile:
    json.dump(person, jsonfile, indent=2)

# JSON Reading
with open("person.json", "r") as jsonfile:
    loaded_person = json.load(jsonfile)
    print("\nJSON Contents:")
    print(json.dumps(loaded_person, indent=2))

# Real‑world example: processing API response
api_response = '''
{
    "status": "success",
    "data": {
        "users": [
            {"id": 1, "name": "Alice", "email": "alice@example.com"},
            {"id": 2, "name": "Bob", "email": "bob@example.com"}
        ],
        "total": 2
    }
}
'''

# Parse JSON string
response_data = json.loads(api_response)
print(f"\nAPI Status: {response_data['status']}")
print(f"Total users: {response_data['data']['total']}")
for user in response_data['data']['users']:
    print(f"  - {user['name']} ({user['email']})")
```

---

## Slide 17: Context Managers – The `with` Statement

- Context managers manage resources (files, locks, connections) with setup/teardown
- The `with` statement ensures proper acquisition and release
- Built‑in context managers: `open()`, `threading.Lock()`, `socket.create_connection()`
- Create custom context managers using classes (`__enter__`, `__exit__`) or `contextlib`
- Prevents resource leaks and makes code cleaner

**Speaker Notes:**
Context managers are Python's elegant solution to resource management. Instead of manually opening and closing files (and forgetting to close them), you use `with open(...) as f`. The context manager guarantees that `__exit__` is called, even if an exception occurs. We'll explore built‑in context managers and learn how to create our own for custom resources.

```python
# Built‑in context manager: file handling
with open("example.txt", "w") as f:
    f.write("Using context manager ensures file is closed automatically")

# Custom context manager using class
class Timer:
    def __enter__(self):
        import time
        self.start = time.time()
        print("Timer started")
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        import time
        self.end = time.time()
        print(f"Timer stopped. Elapsed: {self.end - self.start:.2f} seconds")
        # Return False to propagate exceptions, True to suppress them
        return False

# Using custom context manager
with Timer() as t:
    import time
    time.sleep(1.5)
    print("Inside the block")

# Context manager for database connections (conceptual)
class DatabaseConnection:
    def __init__(self, connection_string):
        self.conn_string = connection_string
        self.connection = None
    
    def __enter__(self):
        import sqlite3  # example
        self.connection = sqlite3.connect(self.conn_string)
        print("Database connection opened")
        return self.connection
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.connection:
            self.connection.close()
            print("Database connection closed")
        return False

# Using the database context manager
# with DatabaseConnection("example.db") as conn:
#     cursor = conn.cursor()
#     cursor.execute("SELECT * FROM users")

# Using contextlib for simpler context managers
from contextlib import contextmanager

@contextmanager
def temporary_change(obj, attr, new_value):
    """Temporarily change an attribute, then restore it."""
    old_value = getattr(obj, attr)
    setattr(obj, attr, new_value)
    try:
        yield
    finally:
        setattr(obj, attr, old_value)

class Config:
    debug = False

config = Config()
print(f"Before: debug = {config.debug}")
with temporary_change(config, "debug", True):
    print(f"During: debug = {config.debug}")
print(f"After: debug = {config.debug}")
```

---

## Slide 18: Best Practices and Patterns

- Write readable, maintainable code with meaningful names
- Follow PEP 8 style guide (indentation, naming, line length)
- Use type hints for better documentation and IDE support
- Write docstrings for modules, classes, and functions
- Prefer composition over inheritance where appropriate
- Use logging instead of `print()` for production code
- Write tests (unit, integration) to ensure correctness
- Profile and optimize only after identifying bottlenecks

**Speaker Notes:**
Good Python code isn't just about making it work—it's about making it understandable, maintainable, and robust. We'll review essential best practices that separate beginner code from professional code. These patterns will help you write code that your future self (and your teammates) will thank you for.

```python
# Best Practice 1: Meaningful names
# BAD:
def p(d):
    return d * 3.14159

# GOOD:
def calculate_circumference(diameter):
    return diameter * 3.14159

# Best Practice 2: Type hints
from typing import List, Dict, Optional

def process_users(users: List[Dict[str, str]]) -> Optional[int]:
    """Process a list of user dictionaries.
    
    Args:
        users: List of dictionaries with 'name' and 'email' keys.
    
    Returns:
        Number of processed users, or None if input is empty.
    """
    if not users:
        return None
    return len(users)

# Best Practice 3: Use logging
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

def risky_operation():
    try:
        result = 10 / 0
    except ZeroDivisionError as e:
        logger.error("Division by zero attempted: %s", e)
        raise

# Best Practice 4: Use enumerate() for index‑value pairs
names = ["Alice", "Bob", "Charlie"]
for i, name in enumerate(names, start=1):
    print(f"{i}. {name}")

# Best Practice 5: Use zip() to iterate over multiple sequences
ages = [30, 25, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old")

# Best Practice 6: Use collections.defaultdict for missing keys
from collections import defaultdict
word_counts = defaultdict(int)
for word in ["apple", "banana", "apple", "orange"]:
    word_counts[word] += 1  # No need to check if key exists

# Best Practice 7: Use `if __name__ == "__main__":` for script execution
def main():
    print("This runs only when script is executed directly")

if __name__ == "__main__":
    main()

# Best Practice 8: Use virtual environments for dependency isolation
# Run: python -m venv venv
# Then: source venv/bin/activate (or venv\Scripts\activate on Windows)

# Best Practice 9: Write comprehensive docstrings
def calculate_statistics(data: List[float]) -> Dict[str, float]:
    """Calculate basic statistics from a list of numbers.
    
    Args:
        data: List of numerical values.
    
    Returns:
        Dictionary with keys 'mean', 'median', 'std_dev'.
    
    Raises:
        ValueError: If data list is empty.
    """
    if not data:
        raise ValueError("Data list cannot be empty")
    
    import statistics
    return {
        "mean": statistics.mean(data),
        "median": statistics.median(data),
        "std_dev": statistics.stdev(data) if len(data) > 1 else 0.0
    }

# Best Practice 10: Keep functions small and focused (Single Responsibility Principle)
```

---

## Course Wrap‑Up & Next Steps

- You've mastered Python's core data structures: lists, tuples, sets, dictionaries
- You understand mutability, comprehensions, and nested structures
- You've embraced functional programming with lambdas, map, filter, reduce
- You can handle errors gracefully and create custom exceptions
- You can work with files, CSV, JSON, and context managers
- You know best practices for writing professional Python code

**Next Steps:**
- Practice with real‑world projects (data analysis, web scraping, APIs)
- Explore advanced topics: decorators, generators, async/await
- Dive into data science (pandas, NumPy, matplotlib)
- Learn web frameworks (Flask, Django, FastAPI)
- Contribute to open‑source Python projects
- Never stop learning and building!

**Speaker Notes:**
Congratulations on completing Part 2! You now have a solid intermediate understanding of Python. Remember that mastery comes through practice—build projects, solve problems, and read other people's code. Python's ecosystem is vast and welcoming. Join the community, attend meetups or conferences, and keep pushing your skills forward. Thank you for learning with us!

---

## Appendix: Google Colab Quick Start for Part 2

- Open [colab.research.google.com](https://colab.research.google.com)
- Create a new notebook or upload this tutorial
- Install required packages: `!pip install pandas numpy matplotlib`
- Use `%%writefile` to create example files in Colab's virtual filesystem
- Remember: Colab sessions are temporary; download important files

**Speaker Notes:**
For hands‑on practice with the examples in this tutorial, Google Colab provides a ready‑to‑use Python environment. You can run each code cell independently. Here's a starter cell to get you going:

```python
# Colab starter cell
!pip install pandas numpy  # Install packages if needed

import json
import csv
from functools import reduce

# Create a sample file
with open("sample.json", "w") as f:
    json.dump({"test": "data"}, f)

print("Ready to practice Python Data Structures & Functional Programming!")
```

---

*End of Part 2 – Python Data Structures & Functional Programming*
spreadsheet‑like data, while JSON excels at nested, hierarchical data (like API responses). Python's standard library includes excellent modules for both. We'll learn how to read, write, and manipulate these formats with practical examples.

```python
import csv
import json

# CSV Writing
data = [
    ["Name", "Age", "City"],
    ["Alice", 30, "New York"],
    ["Bob", 25, "London"],
    ["Charlie", 35, "Paris"]
]

with open("people.csv", "w", newline="") as csvfile:
    writer = csv.writer(csvfile)
    writer.writerows(data)

# CSV Reading
with open("people.csv", "r") as csvfile:
    reader = csv.reader(csvfile)
    print("CSV Contents:")
    for row in reader:
        print(row)

# CSV with DictReader/DictWriter (more convenient)
with open("people.csv", "r") as csvfile:
    reader = csv.DictReader(csvfile)
    print("\nCSV as dictionaries:")
    for row in reader:
        print(f"{row['Name']} is {row['Age']} years old in {row['City']}")

# JSON Writing
person = {
    "name": "Alice",
    "age": 30,
    "city": "New York",
    "hobbies": ["reading", "hiking", "coding"],
    "employed": True
}

with open("person.json", "w") as jsonfile:
    json.dump(person, jsonfile, indent=2)

# JSON Reading
with open("person.json", "r") as jsonfile:
    loaded_person = json.load(jsonfile)
    print("\nJSON Contents:")
    print(json.dumps(loaded_person, indent=2))

# Real‑world example: processing API response
api_response = '''
{
    "status": "success",
    "data": {
        "users": [
            {"id": 1, "name": "Alice", "email": "alice@example.com"},
            {"id": 2, "name": "Bob", "email": "bob@example.com"}
        ],
        "total": 2
    }
}
'''

# Parse JSON string
response_data = json.loads(api_response)
print(f"\nAPI Status: {response_data['status']}")
print(f"Total users: {response_data['data']['total']}")
for user in response_data['data']['users']:
    print(f"  - {user['name']} ({user['email']})")
```

---

## Slide 17: Context Managers – The `with` Statement

- Context managers manage resources (files, locks, connections) with setup/teardown
- The `with` statement ensures proper acquisition and release
- Built‑in context managers: `open()`, `threading.Lock()`, `socket.create_connection()`
- Create custom context managers using classes (`__enter__`, `__exit__`) or `contextlib`
- Prevents resource leaks and makes code cleaner

**Speaker Notes:**
Context managers are Python's elegant solution to resource management. Instead of manually opening and closing files (and forgetting to close them), you use `with open(...) as f`. The context manager guarantees that `__exit__` is called, even if an exception occurs. We'll explore built‑in context managers and learn how to create our own for custom resources.

```python
# Built‑in context manager: file handling
with open("example.txt", "w") as f:
    f.write("Using context manager ensures file is closed automatically")

# Custom context manager using class
class Timer:
    def __enter__(self):
        import time
        self.start = time.time()
        print("Timer started")
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        import time
        self.end = time.time()
        print(f"Timer stopped. Elapsed: {self.end - self.start:.2f} seconds")
        # Return False to propagate exceptions, True to suppress them
        return False

# Using custom context manager
with Timer() as t:
    import time
    time.sleep(1.5)
    print("Inside the block")

# Context manager for database connections (conceptual)
class DatabaseConnection:
    def __init__(self, connection_string):
        self.conn_string = connection_string
        self.connection = None
    
    def __enter__(self):
        import sqlite3  # example
        self.connection = sqlite3.connect(self.conn_string)
        print("Database connection opened")
        return self.connection
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.connection:
            self.connection.close()
            print("Database connection closed")
        return False

# Using the database context manager
# with DatabaseConnection("example.db") as conn:
#     cursor = conn.cursor()
#     cursor.execute("SELECT * FROM users")

# Using contextlib for simpler context managers
from contextlib import contextmanager

@contextmanager
def temporary_change(obj, attr, new_value):
    """Temporarily change an attribute, then restore it."""
    old_value = getattr(obj, attr)
    setattr(obj, attr, new_value)
    try:
        yield
    finally:
        setattr(obj, attr, old_value)

class Config:
    debug = False

config = Config()
print(f"Before: debug = {config.debug}")
with temporary_change(config, "debug", True):
    print(f"During: debug = {config.debug}")
print(f"After: debug = {config.debug}")
```

---

## Slide 18: Best Practices and Patterns

- Write readable, maintainable code with meaningful names
- Follow PEP 8 style guide (indentation, naming, line length)
- Use type hints for better documentation and IDE support
- Write docstrings for modules, classes, and functions
- Prefer composition over inheritance where appropriate
- Use logging instead of `print()` for production code
- Write tests (unit, integration) to ensure correctness
- Profile and optimize only after identifying bottlenecks

**Speaker Notes:**
Good Python code isn't just about making it work—it's about making it understandable, maintainable, and robust. We'll review essential best practices that separate beginner code from professional code. These patterns will help you write code that your future self (and your teammates) will thank you for.

```python
# Best Practice 1: Meaningful names
# BAD:
def p(d):
    return d * 3.14159

# GOOD:
def calculate_circumference(diameter):
    return diameter * 3.14159

# Best Practice 2: Type hints
from typing import List, Dict, Optional

def process_users(users: List[Dict[str, str]]) -> Optional[int]:
    """Process a list of user dictionaries.
    
    Args:
        users: List of dictionaries with 'name' and 'email' keys.
    
    Returns:
        Number of processed users, or None if input is empty.
    """
    if not users:
        return None
    return len(users)

# Best Practice 3: Use logging
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

def risky_operation():
    try:
        result = 10 / 0
    except ZeroDivisionError as e:
        logger.error("Division by zero attempted: %s", e)
        raise

# Best Practice 4: Use enumerate() for index‑value pairs
names = ["Alice", "Bob", "Charlie"]
for i, name in enumerate(names, start=1):
    print(f"{i}. {name}")

# Best Practice 5: Use zip() to iterate over multiple sequences
ages = [30, 25, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old")

# Best Practice 6: Use collections.defaultdict for missing keys
from collections import defaultdict
word_counts = defaultdict(int)
for word in ["apple", "banana", "apple", "orange"]:
    word_counts[word] += 1  # No need to check if key exists

# Best Practice 7: Use `if __name__ == "__main__":` for script execution
def main():
    print("This runs only when script is executed directly")

if __name__ == "__main__":
    main()

# Best Practice 8: Use virtual environments for dependency isolation
# Run: python -m venv venv
# Then: source venv/bin/activate (or venv\Scripts\activate on Windows)

# Best Practice 9: Write comprehensive docstrings
def calculate_statistics(data: List[float]) -> Dict[str, float]:
    """Calculate basic statistics from a list of numbers.
    
    Args:
        data: List of numerical values.
    
    Returns:
        Dictionary with keys 'mean', 'median', 'std_dev'.
    
    Raises:
        ValueError: If data list is empty.
    """
    if not data:
        raise ValueError("Data list cannot be empty")
    
    import statistics
    return {
        "mean": statistics.mean(data),
        "median": statistics.median(data),
        "std_dev": statistics.stdev(data) if len(data) > 1 else 0.0
    }

# Best Practice 10: Keep functions small and focused (Single Responsibility Principle)
```

---

## Course Wrap‑Up & Next Steps

- You've mastered Python's core data structures: lists, tuples, sets, dictionaries
- You understand mutability, comprehensions, and nested structures
- You've embraced functional programming with lambdas, map, filter, reduce
- You can handle errors gracefully and create custom exceptions
- You can work with files, CSV, JSON, and context managers
- You know best practices for writing professional Python code

**Next Steps:**
- Practice with real‑world projects (data analysis, web scraping, APIs)
- Explore advanced topics: decorators, generators, async/await
- Dive into data science (pandas, NumPy, matplotlib)
- Learn web frameworks (Flask, Django, FastAPI)
- Contribute to open‑source Python projects
- Never stop learning and building!

**Speaker Notes:**
Congratulations on completing Part 2! You now have a solid intermediate understanding of Python. Remember that mastery comes through practice—build projects, solve problems, and read other people's code. Python's ecosystem is vast and welcoming. Join the community, attend meetups or conferences, and keep pushing your skills forward. Thank you for learning with us!

---

## Appendix: Google Colab Quick Start for Part 2

- Open [colab.research.google.com](https://colab.research.google.com)
- Create a new notebook or upload this tutorial
- Install required packages: `!pip install pandas numpy matplotlib`
- Use `%%writefile` to create example files in Colab's virtual filesystem
- Remember: Colab sessions are temporary; download important files

**Speaker Notes:**
For hands‑on practice with the examples in this tutorial, Google Colab provides a ready‑to‑use Python environment. You can run each code cell independently. Here's a starter cell to get you going:

```python
# Colab starter cell
!pip install pandas numpy  # Install packages if needed

import json
import csv
from functools import reduce

# Create a sample file
with open("sample.json", "w") as f:
    json.dump({"test": "data"}, f)

print("Ready to practice Python Data Structures & Functional Programming!")
```

---

*End of Part 2 – Python Data Structures & Functional Programming*
