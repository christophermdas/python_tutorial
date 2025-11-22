# Python Tutorial

Welcome to your comprehensive guide to Python 3.14. This document is designed to be a one-stop reference for Python programming, from the fundamentals to advanced topics.

---

# Part 1: The Basics

---

## Chapter 1.1: What is Python?

### A General-Purpose, High-Level Language

Python is a **general-purpose**, **interpreted**, **high-level** programming language. Let's break down what that means:

*   **General-Purpose:** You can use Python for nearly anything. It's used in web development, data science, artificial intelligence, desktop applications, automation, and much more. It's the "Swiss Army knife" of programming languages.

*   **Interpreted:** Python code is executed line by line by an interpreter. This is different from compiled languages like C++ or Java, where the entire program is converted to machine code before it can be run. This makes the development process faster, as you don't have to wait for a compiler.

*   **High-Level:** Python abstracts away many of the complex details of the computer's hardware. You don't have to worry about memory management or other low-level concerns, allowing you to focus on the logic of your application.

### Core Philosophy: The Zen of Python

Python's design philosophy is summarized in a document called "The Zen of Python." You can read it by typing `import this` into a Python interpreter. Some of the key principles are:

*   Beautiful is better than ugly.
*   Explicit is better than implicit.
*   Simple is better than complex.
*   Readability counts.

This philosophy emphasizes code that is easy to read, understand, and maintain.

### Key Features of Python

*   **Easy to Learn and Read:** Python's syntax is clean and resembles plain English, making it one of the easiest languages for beginners to learn.

*   **Large Standard Library:** Python comes with a vast standard library that provides tools for a wide variety of tasks, from working with text to networking.

*   **Dynamically Typed:** You don't have to declare the type of a variable when you create it. Python figures it out at runtime. This allows for more flexible code.

    ```python
    # No need to specify the type of 'x'
    x = 10       # x is an integer
    x = "Hello"  # Now x is a string
    ```

*   **Cross-Platform:** Python code can run on Windows, macOS, and Linux without modification.

*   **Strong Community:** Python has a massive and active community, which means you can always find help, tutorials, and third-party libraries for any task you can imagine.

### Common Use Cases

Here are some of the areas where Python excels:

| Domain                  | Popular Libraries/Frameworks        |
| :---------------------- | :---------------------------------- |
| **Web Development**     | Django, Flask, FastAPI              |
| **Data Science**        | NumPy, Pandas, Matplotlib, Scikit-learn |
| **Machine Learning/AI** | TensorFlow, PyTorch, Keras          |
| **Automation**          | Selenium, BeautifulSoup, PyAutoGUI  |
| **Desktop GUI**         | Tkinter, PyQt, Kivy                 |

---

## Chapter 1.2: Setting Up Your Environment

To start writing Python code, you need to set up a proper development environment. This involves installing Python itself and a good code editor.

### 1. Installing Python 3.14

#### Windows

1.  **Download the Installer:** Go to the [official Python website](https.python.org/downloads/) and download the latest installer for Python 3.14.

2.  **Run the Installer:**
    *   Open the downloaded `.exe` file.
    *   **Crucial Step:** Check the box that says **"Add Python to PATH"**. This will allow you to run Python from the command line.
    *   Click on "Install Now".

3.  **Verify the Installation:**
    *   Open a new Command Prompt or PowerShell window.
    *   Type the following command and press Enter:
        ```bash
        python --version
        ```
    *   You should see `Python 3.14.x` (the 'x' is a patch number).

#### macOS

macOS comes with a pre-installed version of Python, but it's usually an older version. It's best to install the latest version.

1.  **Using the Official Installer:**
    *   Download the macOS installer from the [Python website](https.python.org/downloads/).
    *   Run the installer. It will guide you through the process.

2.  **Using Homebrew (Recommended):**
    *   If you don't have Homebrew, install it from [brew.sh](https://brew.sh/).
    *   Open your terminal and run:
        ```bash
        brew install python@3.14
        ```

3.  **Verify the Installation:**
    *   Open a new terminal window and type:
        ```bash
        python3 --version
        ```
    *   You should see `Python 3.14.x`.

#### Linux

Most Linux distributions come with Python pre-installed. To install the latest version, use your distribution's package manager.

*   **For Debian/Ubuntu:**
    ```bash
    sudo apt update
    sudo apt install python3.14
    ```

*   **For Fedora:**
    ```bash
    sudo dnf install python3.14
    ```

*   **Verify the Installation:**
    ```bash
    python3 --version
    ```

### 2. The Code Editor: Visual Studio Code

A good code editor will make your life much easier. **Visual Studio Code (VS Code)** is the most popular choice for Python development, and for good reason.

1.  **Download and Install VS Code:**
    *   Go to the [VS Code website](https://code.visualstudio.com/) and download the installer for your operating system.
    *   Run the installer with the default settings.

2.  **Install the Python Extension:**
    *   Open VS Code.
    *   Go to the Extensions view by clicking the icon on the sidebar or pressing `Ctrl+Shift+X`.
    *   Search for "Python" and install the official extension from Microsoft.

3.  **Select the Python Interpreter:**
    *   Open a Python file (`.py`) or open the Command Palette (`Ctrl+Shift+P`).
    *   Search for "Python: Select Interpreter".
    *   Choose the Python 3.14 installation you just installed.

### 3. Virtual Environments

A **virtual environment** is an isolated environment for your Python projects. This is a best practice that you should adopt from day one.

#### Why use them?

*   It keeps the dependencies for different projects separate. For example, Project A might need version 1.0 of a library, while Project B needs version 2.0. Virtual environments prevent conflicts.
*   It keeps your global `site-packages` directory clean.

#### How to use them:

1.  **Create a virtual environment:**
    *   Navigate to your project folder in your terminal.
    *   Run the following command:
        ```bash
        python -m venv .venv
        ```
    *   This will create a `.venv` folder in your project directory.

2.  **Activate the virtual environment:**
    *   **On Windows:**
        ```bash
        .venv\Scripts\activate
        ```
    *   **On macOS and Linux:**
        ```bash
        source .venv/bin/activate
        ```
    *   Your terminal prompt will change to show the name of the virtual environment (e.g., `(.venv) C:\Users\YourUser\Project>`).

3.  **Install packages:**
    *   Now, when you use `pip` (Python's package installer), packages will be installed inside the virtual environment.
        ```bash
        pip install requests
        ```

4.  **Deactivate the virtual environment:**
    *   When you are done working, simply type:
        ```bash
        deactivate
        ```
Now you have a fully functional Python development environment. You are ready to start coding!

---

## Chapter 2.1: Variables and Data Types

### What is a Variable?

Think of a variable as a labeled container for a value. In Python, you create a variable by giving it a name and assigning it a value using the equals sign (`=`).

```python
# 'message' is the variable name
# "Hello, Python!" is the value
message = "Hello, Python!"

# You can then use the variable name to access the value
print(message)

# You can also change the value of a variable
message = "Python is fun!"
print(message)
```

#### Naming Rules

*   Variable names can only contain letters, numbers, and underscores.
*   They must start with a letter or an underscore.
*   They cannot be a Python keyword (like `if`, `for`, `class`, etc.).
*   Variable names are case-sensitive (`age`, `Age`, and `AGE` are three different variables).

**Convention:** The standard convention for Python variables is `snake_case` (all lowercase with underscores between words).

```python
# Good variable names
user_name = "Alice"
first_name = "Bob"
age = 30

# Bad variable names
# 1st_place = "Gold"  # Starts with a number
# user-name = "Eve"   # Contains a hyphen
```

### Python's Built-in Data Types

Python has several built-in data types to represent different kinds of information.

#### 1. Numeric Types

These are used for numbers.

*   **Integer (`int`):** Whole numbers, positive or negative.
    ```python
    my_integer = 42
    negative_integer = -100
    ```

*   **Float (`float`):** Numbers with a decimal point.
    ```python
    my_float = 3.14159
    price = 19.99
    ```

*   **Complex (`complex`):** Numbers with a real and imaginary part (less common in general programming).
    ```python
    my_complex = 2 + 3j
    ```

#### 2. Text Type

*   **String (`str`):** A sequence of characters, used for text. You can create strings using single quotes (`'...'`), double quotes (`"..."`), or triple quotes (`"""..."""` or `'''...'''`) for multi-line strings.

    ```python
    single_quoted = 'Hello, world!'
    double_quoted = "Python is great."

    multi_line_string = """This is a
    multi-line string. It can span
    across several lines."""
    ```

    **f-strings (Formatted String Literals):** A modern and convenient way to embed expressions inside string literals.

    ```python
    name = "Charlie"
    age = 25
    greeting = f"Hello, my name is {name} and I am {age} years old."
    print(greeting)
    # Output: Hello, my name is Charlie and I am 25 years old.
    ```

#### 3. Boolean Type

*   **Boolean (`bool`):** Represents one of two values: `True` or `False`. Booleans are crucial for control flow.

    ```python
    is_active = True
    is_admin = False

    print(is_active)  # Output: True
    ```

#### 4. Sequence Types

These are ordered collections of items.

*   **List (`list`):** A mutable (changeable), ordered sequence of items.
*   **Tuple (`tuple`):** An immutable (unchangeable), ordered sequence of items.

We will cover these in detail in the **Data Structures** section.

#### 5. Mapping Type

*   **Dictionary (`dict`):** An unordered collection of key-value pairs.

We will cover this in detail in the **Data Structures** section.

#### 6. Set Types

*   **Set (`set`):** An unordered collection of unique items.

We will cover this in detail in the **Data Structures** section.

#### Checking a Variable's Type

You can use the built-in `type()` function to find out the data type of any variable.

```python
x = 10
y = "Hello"
z = 3.14

print(type(x))  # Output: <class 'int'>
print(type(y))  # Output: <class 'str'>
print(type(z))  # Output: <class 'float'>
```

### Type Casting

You can convert a variable from one data type to another. This is called type casting.

```python
# Convert float to int
float_num = 9.99
int_num = int(float_num)
print(int_num)  # Output: 9

# Convert int to str
num = 123
str_num = str(num)
print(str_num)      # Output: "123"
print(type(str_num)) # Output: <class 'str'>

# Convert str to int (only if the string contains a valid integer)
num_string = "456"
as_int = int(num_string)
print(as_int)       # Output: 456
print(type(as_int))  # Output: <class 'int'>
```

--- 

## Chapter 2.2: Operators

Operators are special symbols in Python that carry out arithmetic or logical computation. The value that the operator operates on is called the operand.

### 1. Arithmetic Operators

These are used to perform mathematical operations.

| Operator | Name           | Example     | Result |
| :------: | -------------- | ----------- | :----: |
|   `+`    | Addition       | `a + b`     |   15   |
|   `-`    | Subtraction    | `a - b`     |   5    |
|   `*`    | Multiplication | `a * b`     |   50   |
|   `/`    | Division       | `a / b`     |  2.0   |
|   `%`    | Modulus        | `a % b`     |   0    |
|   `**`   | Exponentiation | `a ** b`    | 100000 |
|   `//`   | Floor Division | `11 // b`   |   2    |

**Example Code:**

```python
a = 10
b = 5

print(f"a + b = {a + b}")
print(f"a - b = {a - b}")
print(f"a * b = {a * b}")
print(f"a / b = {a / b}")        # Division always returns a float
print(f"a % b = {a % b}")        # Remainder of the division
print(f"a ** b = {a ** b}")      # a to the power of b
print(f"11 // b = {11 // b}")    # Division rounded down to the nearest whole number
```

### 2. Comparison Operators

These are used to compare two values. They return either `True` or `False`.

| Operator | Name                       | Example  | Result |
| :------: | -------------------------- | :------: | :----: |
|   `==`   | Equal to                   | `x == y` | `False` |
|   `!=`   | Not equal to               | `x != y` | `True` |
|   `>`    | Greater than               | `x > y`  | `True` |
|   `<`    | Less than                  | `x < y`  | `False` |
|   `>=`   | Greater than or equal to   | `x >= y` | `True` |
|   `<=`   | Less than or equal to      | `x <= y` | `False` |

**Example Code:**

```python
x = 10
y = 5

print(f"x == y: {x == y}")
print(f"x != y: {x != y}")
print(f"x > y: {x > y}")
print(f"x < y: {x < y}")
print(f"x >= 10: {x >= 10}")
print(f"y <= 4: {y <= 4}")
```

### 3. Logical Operators

These are used to combine conditional statements.

| Operator | Description                                   | Example               |
| :------: | --------------------------------------------- | --------------------- |
|  `and`   | Returns `True` if both statements are true    | `x > 5 and y < 10`    |
|   `or`   | Returns `True` if one of the statements is true | `x > 10 or y < 10`    |
|  `not`   | Reverses the result (returns `False` if `True`) | `not(x > 5 and y < 10)` |

**Example Code:**

```python
x = 10
y = 5

# Both conditions are true
print(f"x > 0 and y < 10: {x > 0 and y < 10}")  # Output: True

# One condition is false
print(f"x < 0 and y < 10: {x < 0 and y < 10}")  # Output: False

# One condition is true
print(f"x < 0 or y < 10: {x < 0 or y < 10}")    # Output: True

# not reverses the boolean value
is_sunny = True
print(f"Is it not sunny? {not is_sunny}")     # Output: False
```

### 4. Assignment Operators

These are used to assign values to variables.

| Operator | Example      | Equivalent to |
| :------: | ------------ | ------------- |
|   `=`    | `x = 5`      | `x = 5`       |
|   `+=`   | `x += 3`     | `x = x + 3`   |
|   `-=`   | `x -= 3`     | `x = x - 3`   |
|   `*=`   | `x *= 3`     | `x = x * 3`   |
|   `/=`   | `x /= 3`     | `x = x / 3`   |
|   `%=`   | `x %= 3`     | `x = x % 3`   |
|   `//=`  | `x //= 3`    | `x = x // 3`  |
|   `**=`  | `x **= 3`    | `x = x ** 3`  |

**Example Code:**

```python
count = 5
print(f"Initial count: {count}")

count += 2  # Add 2 to count
print(f"After += 2: {count}")  # Output: 7

count *= 3  # Multiply count by 3
print(f"After *= 3: {count}")  # Output: 21
```

### 5. Membership Operators

These are used to test if a sequence is present in an object.

| Operator | Description                                             | Example        |
| :------: | ------------------------------------------------------- | -------------- |
|   `in`   | Returns `True` if a value is found in the sequence      | `'a' in my_list` |
| `not in` | Returns `True` if a value is not found in the sequence  | `'z' not in my_list` |

**Example Code:**

```python
my_list = [1, 2, 3, 'a', 'b']

# Check if 'a' is in the list
print(f"'a' in my_list: {'a' in my_list}")  # Output: True

# Check if 5 is not in the list
print(f"5 not in my_list: {5 not in my_list}") # Output: True
```

### Operator Precedence

Python has a specific order in which it evaluates operators, just like in mathematics (PEMDAS/BODMAS).

1.  `()` (Parentheses)
2.  `**` (Exponentiation)
3.  `-x`, `+x` (Unary plus/minus)
4.  `*`, `/`, `//`, `%` (Multiplication, Division, Floor Division, Modulus)
5.  `+`, `-` (Addition, Subtraction)
6.  `==`, `!=`, `>`, `<`, `>=`, `<=` (Comparison operators)
7.  `not` (Logical NOT)
8.  `and` (Logical AND)
9.  `or` (Logical OR)

When in doubt, use parentheses `()` to make the order of evaluation explicit and improve readability.

```python
# Without parentheses
result = 10 + 2 * 3  # 2 * 3 is evaluated first
print(result)        # Output: 16

# With parentheses
result = (10 + 2) * 3  # 10 + 2 is evaluated first
print(result)          # Output: 36
```

--- 

## Chapter 2.3: Control Flow

Control flow refers to the order in which the statements in your program are executed. In Python, you can control this flow using conditional statements and loops.

### 1. Conditional Statements: `if`, `elif`, and `else`

Conditional statements allow you to execute certain blocks of code based on whether a condition is true or false.

#### The `if` Statement

The `if` statement is the simplest form. The block of code inside the `if` statement is executed only if the condition is `True`.

```python
age = 18

if age >= 18:
    print("You are eligible to vote.")

# This line will always be printed
print("Program finished.")
```

#### The `if-else` Statement

The `else` statement provides an alternative block of code to be executed if the `if` condition is `False`.

```python
temperature = 25

if temperature > 30:
    print("It's a hot day!")
else:
    print("The weather is pleasant.")
```

#### The `if-elif-else` Chain

For multiple conditions, you can use `elif` (short for "else if"). Python will check each condition in order and execute the first block of code where the condition is `True`.

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")

# Output: Grade: B
```
**Note:** Only one block in the entire `if-elif-else` chain will be executed.

### 2. Looping

Loops are used to execute a block of code repeatedly.

#### The `for` Loop

The `for` loop is used for iterating over a sequence (like a list, tuple, dictionary, set, or string).

**Looping over a list:**

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

**Looping over a string:**

```python
for letter in "Python":
    print(letter)
```

**The `range()` function:**

The `range()` function is often used with `for` loops to generate a sequence of numbers.

```python
# Print numbers from 0 to 4
for i in range(5):
    print(i)

# Print numbers from 5 to 9
for i in range(5, 10):
    print(i)

# Print even numbers from 0 to 10
for i in range(0, 11, 2):  # The third argument is the step
    print(i)
```

#### The `while` Loop

The `while` loop executes a block of code as long as a condition is `True`.

```python
count = 0
while count < 5:
    print(f"Count is: {count}")
    count += 1  # It's crucial to update the condition variable inside the loop
```

**Beware of infinite loops!** If the condition never becomes `False`, the loop will run forever.

```python
# Infinite loop example - DON'T RUN THIS
# while True:
#     print("This will run forever!")
```

### 3. Loop Control Statements

You can change the flow of a loop using `break` and `continue`.

#### The `break` Statement

The `break` statement immediately exits the current loop.

```python
numbers = [1, 2, 3, 4, 5, 6, 7]
for num in numbers:
    if num == 5:
        print("Found the number 5, stopping the loop.")
        break  # Exit the loop
    print(num)
```

#### The `continue` Statement

The `continue` statement skips the rest of the current iteration and proceeds to the next one.

```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num == 3:
        print("Skipping number 3.")
        continue  # Skip to the next iteration
    print(f"Processing number {num}")
```

#### The `else` Clause in Loops

Both `for` and `while` loops can have an `else` clause. This clause is executed when the loop finishes normally (i.e., not when it's terminated by a `break` statement).

```python
# Example with a for loop
for i in range(5):
    print(i)
else:
    print("The loop finished without a break.")

# Example where else is NOT executed
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("This will not be printed.")
```
This is useful for search operations where you want to do something if the item you are searching for is not found.

--- 

## Chapter 2.4: Functions

Functions are reusable blocks of code that perform a specific task. They help organize your code, make it more readable, and allow you to avoid repeating yourself (following the DRY principle: Don't Repeat Yourself).

### 1. Defining and Calling a Function

#### Defining a Function

You define a function using the `def` keyword, followed by the function name, parentheses `()`, and a colon `:`. The code block within the function is indented.

```python
# A simple function definition
def greet():
    """This function prints a simple greeting."""
    print("Hello, welcome to the world of Python functions!")
```

The string in the first line is called a **docstring**, and it's a good practice to include one to explain what your function does.

#### Calling a Function

To execute the code inside a function, you "call" it by writing its name followed by parentheses.

```python
# Calling the function
greet()

# You can call it as many times as you need
greet()
```

### 2. Parameters and Arguments

Functions become much more powerful when you can pass data into them.

*   **Parameter:** The variable listed inside the parentheses in the function definition.
*   **Argument:** The actual value that is sent to the function when it is called.

```python
# 'name' is a parameter
def greet_user(name):
    """Prints a personalized greeting."""
    print(f"Hello, {name}!")

# "Alice" and "Bob" are arguments
greet_user("Alice")
greet_user("Bob")
```

#### Positional vs. Keyword Arguments

*   **Positional Arguments:** Passed based on their position. The order matters.
*   **Keyword Arguments:** Passed by specifying the parameter name. The order does not matter.

```python
def describe_pet(animal_type, pet_name):
    """Displays information about a pet."""
    print(f"I have a {animal_type} named {pet_name}.")

# Positional arguments (order matters)
describe_pet("hamster", "Harry")

# Keyword arguments (order doesn't matter)
describe_pet(pet_name="Lucy", animal_type="cat")
```

#### Default Parameter Values

You can provide a default value for a parameter. If an argument for that parameter is not provided when the function is called, the default value is used.

```python
# 'animal_type' has a default value of 'dog'
def describe_pet(pet_name, animal_type="dog"):
    """Displays information about a pet."""
    print(f"I have a {animal_type} named {pet_name}.")

describe_pet("Willie")          # Uses the default 'dog'
describe_pet("Whiskers", "cat") # Overrides the default
```

### 3. The `return` Statement

So far, our functions have only printed output. The `return` statement is used to send a value back from the function.

```python
def add_numbers(x, y):
    """Returns the sum of two numbers."""
    return x + y

# The value returned by the function is stored in the 'result' variable
result = add_numbers(5, 3)
print(f"The sum is: {result}") # Output: 8
```

A function can return any data type, including lists, dictionaries, or even other functions. If a function does not have a `return` statement, it implicitly returns `None`.

```python
def no_return_value():
    x = 5

output = no_return_value()
print(output)  # Output: None
```

### 4. Arbitrary Arguments: `*args` and `**kwargs`

Sometimes you don't know in advance how many arguments a function will receive.

#### `*args` (Arbitrary Positional Arguments)

This syntax allows a function to accept any number of positional arguments. These arguments are collected into a **tuple**.

```python
def make_pizza(*toppings):
    """Prints the list of toppings that have been requested."""
    print("Making a pizza with the following toppings:")
    for topping in toppings:
        print(f"- {topping}")

make_pizza("mushrooms")
make_pizza("mushrooms", "green peppers", "extra cheese")
```

#### `**kwargs` (Arbitrary Keyword Arguments)

This syntax allows a function to accept any number of keyword arguments. These arguments are collected into a **dictionary**.

```python
def build_profile(first, last, **user_info):
    """Build a dictionary containing everything we know about a user."""
    user_info['first_name'] = first
    user_info['last_name'] = last
    return user_info

user_profile = build_profile('albert', 'einstein',
                             location='princeton',
                             field='physics')

print(user_profile)
# Output: {'location': 'princeton', 'field': 'physics', 'first_name': 'albert', 'last_name': 'einstein'}
```

### 5. Scope of Variables

The **scope** of a variable is the part of the program where it is accessible.

*   **Local Scope:** A variable created inside a function is only accessible within that function.
*   **Global Scope:** A variable created in the main body of the Python file is a global variable and can be accessed throughout the file.

```python
global_var = "I am global"

def my_function():
    local_var = "I am local"
    print(global_var)  # Can access global variables
    print(local_var)

my_function()

# This will cause an error because local_var is not defined in the global scope
# print(local_var)
```
It's generally bad practice to modify global variables from within a function. If you need to, you must use the `global` keyword.

--- 

# Part 2: Data Structures

---

## Chapter 3.1: Data Structures - Lists

A list is one of the most fundamental and versatile data structures in Python.

### Characteristics of a List

*   **Ordered:** The items in a list have a defined order, and that order will not change.
*   **Mutable:** You can change a list after it has been created (add, remove, or modify items).
*   **Allows Duplicates:** A list can contain items with the same value.
*   **Can contain different data types:** A single list can hold integers, strings, and other objects.

### 1. Creating a List

You create a list by placing items inside square brackets `[]`, separated by commas.

```python
# An empty list
empty_list = []

# A list of integers
numbers = [1, 2, 3, 4, 5]

# A list of strings
fruits = ["apple", "banana", "cherry"]

# A list with mixed data types
mixed_list = [1, "hello", 3.14, True]
```

### 2. Accessing Items (Indexing)

You can access an item in a list by referring to its index number. Python uses zero-based indexing.

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])  # Output: apple
print(fruits[1])  # Output: banana

# Negative indexing: -1 refers to the last item
print(fruits[-1]) # Output: cherry
```

#### Slicing

Slicing allows you to get a sub-list from a list.

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Get items from index 2 up to (but not including) index 5
print(numbers[2:5])   # Output: [2, 3, 4]

# Get items from the beginning up to index 4
print(numbers[:5])    # Output: [0, 1, 2, 3, 4]

# Get items from index 5 to the end
print(numbers[5:])    # Output: [5, 6, 7, 8, 9]

# Get every second item
print(numbers[::2])   # Output: [0, 2, 4, 6, 8]
```

### 3. Modifying a List

Since lists are mutable, you can change their content.

```python
colors = ["red", "green", "blue"]

# Change an item
colors[1] = "yellow"
print(colors)  # Output: ['red', 'yellow', 'blue']
```

### 4. Common List Methods

Methods are functions that belong to an object. Here are some of the most common list methods:

#### Adding Items

*   `append(item)`: Adds an item to the end of the list.
    ```python
    fruits = ["apple", "banana"]
    fruits.append("orange")
    print(fruits)  # Output: ['apple', 'banana', 'orange']
    ```

*   `insert(index, item)`: Inserts an item at a specific position.
    ```python
    fruits = ["apple", "banana"]
    fruits.insert(1, "orange")
    print(fruits)  # Output: ['apple', 'orange', 'banana']
    ```

*   `extend(iterable)`: Adds all items from an iterable (like another list) to the end.
    ```python
    list1 = [1, 2, 3]
    list2 = [4, 5, 6]
    list1.extend(list2)
    print(list1) # Output: [1, 2, 3, 4, 5, 6]
    ```

#### Removing Items

*   `remove(item)`: Removes the *first* occurrence of a specific item.
    ```python
    fruits = ["apple", "banana", "cherry", "banana"]
    fruits.remove("banana")
    print(fruits)  # Output: ['apple', 'cherry', 'banana']
    ```

*   `pop(index)`: Removes and returns the item at a specific index. If no index is specified, it removes and returns the last item.
    ```python
    fruits = ["apple", "banana", "cherry"]
    removed_fruit = fruits.pop(1)
    print(f"Removed fruit: {removed_fruit}") # Output: Removed fruit: banana
    print(fruits)                         # Output: ['apple', 'cherry']
    ```
*   `del` statement: Can be used to remove an item at a specific index or a slice.
    ```python
    numbers = [0, 1, 2, 3, 4, 5]
    del numbers[2]
    print(numbers) # Output: [0, 1, 3, 4, 5]
    ```

#### Other Useful Methods

*   `sort()`: Sorts the list in place.
    ```python
    numbers = [3, 1, 4, 1, 5, 9, 2]
    numbers.sort()
    print(numbers) # Output: [1, 1, 2, 3, 4, 5, 9]

    # Sort in descending order
    numbers.sort(reverse=True)
    print(numbers) # Output: [9, 5, 4, 3, 2, 1, 1]
    ```

*   `reverse()`: Reverses the order of the list in place.
*   `copy()`: Returns a shallow copy of the list.
*   `len()`: Not a method, but a built-in function to get the number of items in a list.
    ```python
    print(len(numbers)) # Output: 7
    ```

### 5. List Comprehensions

A concise and readable way to create lists.

**Traditional way:**
```python
squares = []
for x in range(10):
    squares.append(x**2)
```

**Using a list comprehension:**
```python
squares = [x**2 for x in range(10)]
print(squares) # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

You can also add a condition:
```python
# Get the squares of only even numbers
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares) # Output: [0, 4, 16, 36, 64]
```
Lists are a cornerstone of Python programming. Mastering them is essential for any Python developer.

--- 

## Chapter 3.2: Data Structures - Tuples

A tuple is another built-in sequence data type in Python, similar to a list. The key difference is that tuples are **immutable**.

### Characteristics of a Tuple

*   **Ordered:** The items in a tuple have a defined order.
*   **Immutable:** Once a tuple is created, you cannot change its content. You cannot add, remove, or modify items.
*   **Allows Duplicates:** A tuple can contain items with the same value.

### 1. Creating a Tuple

You create a tuple by placing items inside parentheses `()`, separated by commas. 

```python
# An empty tuple
empty_tuple = ()

# A tuple of integers
numbers = (1, 2, 3, 4, 5)

# A tuple with mixed data types
mixed_tuple = (1, "hello", 3.14, True)

# The parentheses are optional in many cases
another_tuple = 1, "hello", 3.14
```

**Creating a tuple with a single item:**

To create a tuple with only one item, you must include a trailing comma.

```python
single_item_tuple = (42,)  # The comma is what makes it a tuple
not_a_tuple = (42)       # This is just the integer 42

print(type(single_item_tuple)) # Output: <class 'tuple'>
print(type(not_a_tuple))     # Output: <class 'int'>
```

### 2. Accessing Items (Indexing and Slicing)

Accessing items in a tuple works exactly the same way as with lists, using indexes and slicing.

```python
point = (10, 20, 30)

# Accessing by index
print(point[0])  # Output: 10
print(point[-1]) # Output: 30

# Slicing
print(point[0:2]) # Output: (10, 20)
```

### 3. Why Use a Tuple?

Since lists can do everything tuples can do and more, why would you ever use a tuple?

*   **Immutability and Data Integrity:** Because tuples are immutable, the data inside them is safe from accidental modification. This makes them perfect for representing fixed collections of data, like coordinates, RGB color values, or database records.

    ```python
    # This will raise a TypeError
    point = (10, 20)
    # point[0] = 15  # <-- This is not allowed!
    ```

*   **Performance:** Tuples are slightly more memory-efficient and faster to process than lists. This is a micro-optimization, but it can matter in large-scale applications.

*   **Dictionary Keys:** Only immutable types can be used as keys in a dictionary. Therefore, you can use a tuple as a dictionary key, but not a list.

    ```python
    locations = {
        (35.6895, 139.6917): "Tokyo",
        (40.7128, -74.0060): "New York"
    }
    ```

### 4. Tuple Methods

Tuples have very few methods because they are immutable.

*   `count(value)`: Returns the number of times a specified value occurs in a tuple.
    ```python
    my_tuple = (1, 2, 3, 1, 1, 4)
    print(my_tuple.count(1))  # Output: 3
    ```
*   `index(value)`: Returns the index of the first occurrence of a specified value.
    ```python
    my_tuple = ('a', 'b', 'c', 'd')
    print(my_tuple.index('c')) # Output: 2
    ```

### 5. Tuple Unpacking

This is a very common and powerful feature. You can assign the values from a tuple to a sequence of variables.

```python
# The number of variables must match the number of items in the tuple
x, y, z = (10, 20, 30)

print(f"x: {x}, y: {y}, z: {z}") # Output: x: 10, y: 20, z: 30
```

Tuple unpacking is often used to return multiple values from a function.

```python
def get_user_info():
    name = "Alice"
    age = 30
    return (name, age) # Return a tuple

# Unpack the returned tuple
user_name, user_age = get_user_info()

print(f"Name: {user_name}, Age: {user_age}")
```

In summary, use a tuple when you have a collection of items that should not change. They provide safety, a bit of speed, and can be used in places where lists cannot, like dictionary keys.

--- 

## Chapter 3.3: Data Structures - Dictionaries

A dictionary is a collection that stores data in **key-value pairs**. It is one of the most important and widely used data structures in Python.

### Characteristics of a Dictionary

*   **Unordered (in older Python versions):** As of Python 3.7, dictionaries are insertion ordered. In earlier versions, the order of items was not guaranteed.
*   **Mutable:** You can change a dictionary after it has been created (add, remove, or modify items).
*   **Keys are unique:** A dictionary cannot have two keys with the same name. If you assign a value to an existing key, it will be overwritten.
*   **Keys must be immutable:** Keys must be of an immutable data type (like strings, numbers, or tuples). Values can be of any data type.

### 1. Creating a Dictionary

You create a dictionary by placing key-value pairs inside curly braces `{}`, separated by commas. Each key is separated from its value by a colon `: `.

```python
# An empty dictionary
empty_dict = {}

# A simple dictionary
car = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
```

You can also use the `dict()` constructor:

```python
person = dict(name="John", age=36, country="Norway")
```

### 2. Accessing Items

You access a dictionary item by referring to its key name inside square brackets `[]`.

```python
car = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

print(car["model"])  # Output: Mustang
```

If you try to access a key that does not exist, you will get a `KeyError`.

#### The `get()` Method

A safer way to access values is to use the `get()` method. It returns the value for the specified key, but if the key does not exist, it returns `None` (or a default value you specify) instead of raising an error.

```python
print(car.get("brand"))      # Output: Ford
print(car.get("color"))      # Output: None
print(car.get("color", "Not Found")) # Output: Not Found
```

### 3. Modifying a Dictionary

#### Adding or Updating Items

You can add a new item or change the value of an existing item using the assignment operator `= `.

```python
car = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}

# Update an existing item
car["year"] = 2024
print(car) # Output: {'brand': 'Ford', 'model': 'Mustang', 'year': 2024}

# Add a new item
car["color"] = "red"
print(car) # Output: {'brand': 'Ford', 'model': 'Mustang', 'year': 2024, 'color': 'red'}
```

#### Removing Items

*   `pop(key)`: Removes the item with the specified key and returns its value.
    ```python
    model = car.pop("model")
    print(f"Removed model: {model}") # Output: Removed model: Mustang
    print(car)
    ```
*   `del` statement: Removes the item with the specified key.
    ```python
    del car["year"]
    print(car)
    ```

### 4. Looping Through a Dictionary

There are several ways to iterate over a dictionary.

#### Looping through Keys

By default, when you loop through a dictionary, you iterate over its keys.

```python
for key in car:
    print(key) # Prints 'brand', 'color'

# This is equivalent to:
for key in car.keys():
    print(key)
```

#### Looping through Values

You can use the `values()` method to iterate over the values.

```python
for value in car.values():
    print(value) # Prints 'Ford', 'red'
```

#### Looping through Key-Value Pairs

The most common way is to use the `items()` method, which gives you access to both the key and the value in each iteration.

```python
for key, value in car.items():
    print(f"{key}: {value}")
```

### 5. Dictionary Comprehensions

Similar to list comprehensions, you can use dictionary comprehensions to create dictionaries in a concise way.

```python
# Create a dictionary of squares
squares = {x: x**2 for x in range(5)}
print(squares) # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

### 6. Nested Dictionaries

A dictionary can contain other dictionaries. This is a common way to structure complex data.

```python
my_family = {
  "child1" : {
    "name" : "Emil",
    "year" : 2004
  },
  "child2" : {
    "name" : "Tobias",
    "year" : 2007
  },
  "child3" : {
    "name" : "Linus",
    "year" : 2011
  }
}

# Accessing nested data
print(my_family["child2"]["name"]) # Output: Tobias
```
Dictionaries are incredibly useful for modeling real-world objects and storing structured data.

--- 

## Chapter 3.4: Data Structures - Sets

A set is an **unordered** collection of **unique** items. They are useful when you need to store multiple items but are only concerned with their presence or absence, not their order or how many times they appear.

### Characteristics of a Set

*   **Unordered:** The items in a set do not have a defined order. You cannot access items using an index.
*   **Mutable:** Sets themselves are mutable (you can add or remove items).
*   **No Duplicates:** A set cannot contain two items with the same value.
*   **Items must be immutable:** The items within a set must be of an immutable type (like strings, numbers, or tuples).

### 1. Creating a Set

You create a set by placing items inside curly braces `{}`, or by using the `set()` constructor.

```python
# Creating a set with curly braces
fruits = {"apple", "banana", "cherry"}
print(fruits)

# Duplicates will be automatically removed
numbers = {1, 2, 3, 2, 1}
print(numbers)  # Output: {1, 2, 3}

# Using the set() constructor with a list
colors = set(["red", "green", "blue"])
print(colors)
```

**Creating an empty set:**

To create an empty set, you **must** use the `set()` constructor. Using empty curly braces `{}` will create an empty dictionary.

```python
empty_set = set()
empty_dict = {}

print(type(empty_set))  # Output: <class 'set'>
print(type(empty_dict)) # Output: <class 'dict'>
```

### 2. Adding and Removing Items

#### Adding Items

*   `add(item)`: Adds a single item to the set.
    ```python
    fruits = {"apple", "banana"}
    fruits.add("orange")
    print(fruits)

    # Adding an existing item does nothing
    fruits.add("apple")
    print(fruits)
    ```

*   `update(iterable)`: Adds all items from an iterable (like a list or another set).
    ```python
    fruits.update(["mango", "grape"])
    print(fruits)
    ```

#### Removing Items

*   `remove(item)`: Removes the specified item. If the item is not found, it raises a `KeyError`.
    ```python
    fruits.remove("banana")
    print(fruits)
    # fruits.remove("kiwi") # This would raise a KeyError
    ```
*   `discard(item)`: Removes the specified item. If the item is not found, it does **not** raise an error.
    ```python
    fruits.discard("apple")
    print(fruits)
    fruits.discard("kiwi") # No error is raised
    print(fruits)
    ```
*   `pop()`: Removes and returns an arbitrary item from the set.
    ```python
    removed_item = fruits.pop()
    print(f"Removed item: {removed_item}")
    print(fruits)
    ```

### 3. Set Operations

Sets are very powerful because they support mathematical set operations.

Consider these two sets:
```python
set_A = {1, 2, 3, 4}
set_B = {3, 4, 5, 6}
```

#### Union

The union of two sets contains all the items from both sets.

*   Using the `|` operator:
    ```python
    union_set = set_A | set_B
    print(union_set)  # Output: {1, 2, 3, 4, 5, 6}
    ```
*   Using the `union()` method:
    ```python
    union_set = set_A.union(set_B)
    print(union_set)
    ```

#### Intersection

The intersection of two sets contains only the items that are present in **both** sets.

*   Using the `&` operator:
    ```python
    intersection_set = set_A & set_B
    print(intersection_set) # Output: {3, 4}
    ```
*   Using the `intersection()` method:
    ```python
    intersection_set = set_A.intersection(set_B)
    print(intersection_set)
    ```

#### Difference

The difference between two sets contains items that are in the first set but **not** in the second set.

*   Using the `-` operator:
    ```python
    difference_set = set_A - set_B
    print(difference_set) # Output: {1, 2}
    ```
*   Using the `difference()` method:
    ```python
    difference_set = set_A.difference(set_B)
    print(difference_set)
    ```

#### Symmetric Difference

The symmetric difference contains all items from both sets, **except** for the items that are present in both.

*   Using the `^` operator:
    ```python
    sym_diff_set = set_A ^ set_B
    print(sym_diff_set) # Output: {1, 2, 5, 6}
    ```
*   Using the `symmetric_difference()` method:
    ```python
    sym_diff_set = set_A.symmetric_difference(set_B)
    print(sym_diff_set)
    ```

### Common Use Cases for Sets

*   **Removing duplicates from a list:**
    ```python
    my_list = [1, 2, 3, 2, 1, 4, 5, 4]
    unique_items = list(set(my_list))
    print(unique_items) # Output: [1, 2, 3, 4, 5]
    ```
*   **Membership testing:** Checking if an item exists in a collection is much faster in a set than in a list.
    ```python
    large_set = set(range(1000000))
    # This check is very fast
    if 999999 in large_set:
        print("Found it!")
    ```
Sets are the perfect tool when you need to work with unique elements and perform mathematical operations on collections.

--- 

# Part 3: Advanced Python

---

## Chapter 5.1: Advanced Concepts - Decorators

Decorators are a powerful and widely used feature in Python. A decorator is a function that takes another function as an argument, adds some kind of functionality, and then returns another function, all without altering the source code of the original function.

### The Core Concept: Functions are Objects

In Python, functions are "first-class citizens." This means that you can treat them like any other object:
*   You can assign them to variables.
*   You can pass them as arguments to other functions.
*   You can return them from other functions.

This is the foundation that makes decorators possible.

```
+-----------------+      +---------------------+      +-----------------+
| Original        |----->| Decorator Function  |----->| Modified        |
| Function        |      | (adds functionality)|      | Function        |
+-----------------+      +---------------------+      +-----------------+
```

```python
def say_hello():
    return "Hello!"

# Assign a function to a variable
greet = say_hello

# Call the function through the new variable
print(greet()) # Output: Hello!
```

### 1. A Simple Decorator

Let's build a simple decorator that logs when a function is called and how long it took to run.

A decorator is essentially a "wrapper" function.

```python
import time

# This is our decorator
def timer_decorator(func):
    # The wrapper function takes the same arguments as the decorated function
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs) # Call the original function
        end_time = time.time()
        print(f"Function '{func.__name__}' took {end_time - start_time:.4f} seconds to run.")
        return result
    return wrapper
```

Now, let's apply this decorator to a function.

#### The "pie" syntax (`@`)

Python provides a special syntax for applying decorators, using the `@` symbol.

```python
@timer_decorator
def long_running_function(n):
    """A function that takes some time to run."""
    sum = 0
    for i in range(n):
        sum += i
    return sum

# Call the decorated function as usual
result = long_running_function(10000000)
print(f"Result: {result}")
```

When you run this code, you'll see the output from the decorator:

```
Function 'long_running_function' took 0.5234 seconds to run.
Result: 49999995000000
```

#### What's happening under the hood?

The `@timer_decorator` syntax is just "syntactic sugar" for the following:

```python
def long_running_function(n):
    # ... (same as before)

# Manually decorate the function
long_running_function = timer_decorator(long_running_function)

# Now when you call long_running_function, you are actually calling the 'wrapper' function
long_running_function(10000000)
```

### 2. Why Use Decorators?

Decorators are used to add functionality to existing functions in a clean and reusable way. Common use cases include:

*   **Logging:** As shown in our example, to log function calls, arguments, or execution time.
*   **Authentication and Authorization:** In web frameworks like Flask or Django, decorators are used to check if a user is logged in before allowing them to access a certain page.
    ```python
    @login_required
    def view_profile():
        # ... code to show user profile
    ```
*   **Caching:** To store the results of expensive function calls and return the cached result when the same inputs occur again.
*   **Validation:** To validate the input arguments of a function before executing it.

### 3. Decorators with Arguments

Sometimes, you might want to pass arguments to the decorator itself. This requires an extra layer of nesting.

Let's create a decorator that repeats a function call a specified number of times.

```python
def repeat(num_times):
    def decorator_repeat(func):
        def wrapper(*args, **kwargs):
            for _ in range(num_times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator_repeat
```

Now you can use it like this:

```python
@repeat(num_times=3)
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
```

Output:
```
Hello, Alice!
Hello, Alice!
Hello, Alice!
```

Decorators can seem complex at first, but they are a very elegant way to extend the functionality of your code without modifying the original functions.

--- 

## Chapter 5.2: Advanced Concepts - Generators and Iterators

Generators provide a powerful and memory-efficient way to work with sequences of data. To understand generators, we first need to understand the concept of iterables and iterators.

### 1. Iterables and Iterators

*   **Iterable:** An iterable is any Python object that you can loop over, like a list, tuple, or string. It has an `__iter__()` method that returns an iterator.

*   **Iterator:** An iterator is an object that represents a stream of data. It has a `__next__()` method that returns the next item in the stream. When there are no more items, it raises a `StopIteration` exception.

The `for` loop in Python automatically handles all of this for you.

```python
my_list = [1, 2, 3]

# Get an iterator from the list (iterable)
my_iterator = iter(my_list)

# The for loop does this behind the scenes
print(next(my_iterator)) # Output: 1
print(next(my_iterator)) # Output: 2
print(next(my_iterator)) # Output: 3
# print(next(my_iterator)) # This would raise StopIteration
```

The problem with regular iterables like lists is that they store all their values in memory at once. This can be a problem if you are working with a very large dataset.

### 2. Generators: Memory-Efficient Iteration

A **generator** is a special kind of iterator that generates values on the fly, one at a time, instead of storing them all in memory.

#### The `yield` Keyword

The main difference between a regular function and a generator function is the use of the `yield` keyword.

*   A function with `yield` is a generator function.
*   When a generator function is called, it returns a generator object but does not start execution immediately.
*   When the `__next__()` method is called on the generator object (e.g., in a `for` loop), the function executes until it hits a `yield` statement.
*   The `yield` statement pauses the function, "yields" the value, and saves the function's state.
*   On the next call to `__next__()`, the function resumes execution right after the `yield` statement.

```
+--------------------+      yield 1      +--------------------+
| Generator Function |------------------>| Calling Code       |
| (paused)           |<------------------| (receives value)   |
+--------------------+    next() call    +--------------------+
```

```python
def simple_generator(n):
    print("Generator started")
    for i in range(n):
        print(f"Yielding {i}")
        yield i
    print("Generator finished")

# Create a generator object
gen = simple_generator(3)

# The generator function doesn't run yet
print("Generator object created")

# The for loop will call next() on the generator
for number in gen:
    print(f"Received {number}")

```

Output:
```
Generator object created
Generator started
Yielding 0
Received 0
Yielding 1
Received 1
Yielding 2
Received 2
Generator finished
```

#### Example: Reading a Large File

Generators are ideal for processing large files line by line without loading the entire file into memory.

```python
def read_large_file(file_path):
    with open(file_path, 'r') as f:
        for line in f:
            yield line

# You can now process the file line by line with minimal memory usage
# for line in read_large_file("my_very_large_file.txt"):
#     process(line)
```

### 3. Generator Expressions

Similar to list comprehensions, you can use a more concise syntax to create generators, called **generator expressions**.

They look like list comprehensions, but use parentheses `()` instead of square brackets `[]`.

```python
# A list comprehension (stores all values in memory)
list_comp = [x**2 for x in range(10)]

# A generator expression (generates values on demand)
gen_exp = (x**2 for x in range(10))

print(list_comp) # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(gen_exp)   # Output: <generator object <genexpr> at 0x...>

# You can iterate over the generator expression
for value in gen_exp:
    print(value, end=' ')
```

Let's compare the memory usage:

```python
import sys

# A list of 10 million numbers
my_list = [i for i in range(10000000)]
print(f"Size of list: {sys.getsizeof(my_list)} bytes")

# A generator for 10 million numbers
my_generator = (i for i in range(10000000))
print(f"Size of generator: {sys.getsizeof(my_generator)} bytes")
```
Output (will vary slightly):
```
Size of list: 81528048 bytes
Size of generator: 112 bytes
```
As you can see, the generator uses a tiny, constant amount of memory, regardless of the number of items it can produce, because it only ever holds one item in memory at a time.

**Key takeaway:** Use generators when you are working with large sequences of data or when you want to create an iterator in a simple and clean way.

--- 

## Chapter 5.3: Advanced Concepts - Context Managers

A context manager is an object that defines a temporary context for a block of code. You are likely already familiar with the most common use case for context managers: the `with` statement.

### The `with` Statement

The `with` statement is used to wrap the execution of a block of code. A common example is working with files.

**Without a `with` statement:**

```python
f = open("my_file.txt", "w")
try:
    f.write("Hello, world!")
finally:
    # You must always remember to close the file
    f.close()
```
This pattern of `try...finally` is very common for ensuring that a "cleanup" action (like closing a file or releasing a resource) is always performed, even if an error occurs.

**With a `with` statement:**

```python
with open("my_file.txt", "w") as f:
    f.write("Hello, world!")

# The file is automatically closed when the 'with' block is exited,
even if an error occurred inside the block.
```
The `with` statement makes the code cleaner, more readable, and less error-prone. The `open()` function is a context manager.

### How Context Managers Work

For an object to be a context manager, it must implement two special methods:

*   `__enter__()`: This method is called when the `with` block is entered. It can return a value, which is then assigned to the variable after `as` (if one is provided).
*   `__exit__(exc_type, exc_val, exc_tb)`: This method is called when the `with` block is exited. It is responsible for the cleanup. If an exception occurred inside the `with` block, the details of the exception are passed to `__exit__`.

### 1. Creating a Class-Based Context Manager

Let's create our own context manager that measures the time it takes to execute a block of code.

```python
import time

class Timer:
    def __enter__(self):
        self.start_time = time.time()
        # This method must return something if 'as' is used,
        # but here we don't need it.
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        end_time = time.time()
        execution_time = end_time - self.start_time
        print(f"The block took {execution_time:.4f} seconds to execute.")
        # If we want to suppress an exception, we should return True.
        # Otherwise, the exception will be re-raised after __exit__ completes.
        return False
```

Now we can use our `Timer` context manager:

```python
with Timer():
    # Some long-running code
    sum = 0
    for i in range(1000000):
        sum += i

# Output: The block took 0.0523 seconds to execute.
```

### 2. Creating a Function-Based Context Manager

Creating a full class for a simple context manager can be overkill. The `contextlib` module provides a decorator, `@contextmanager`, that allows you to create a context manager from a simple generator function.

This is often a more convenient and readable approach.

*   The code before the `yield` statement is the equivalent of `__enter__()`.
*   The value that is yielded is what's assigned to the `as` variable.
*   The code after the `yield` statement is the equivalent of `__exit__()`.

Let's re-create our `Timer` using this approach.

```python
from contextlib import contextmanager
import time

@contextmanager
def timer():
    start_time = time.time()
    try:
        # The 'yield' is where the code inside the 'with' block will run
        yield
    finally:
        # This code runs after the 'with' block is finished
        end_time = time.time()
        execution_time = end_time - start_time
        print(f"The block took {execution_time:.4f} seconds to execute.")
```
*Note: we wrap the `yield` in a `try...finally` block to ensure the cleanup code runs even if an exception occurs in the `with` block.*

Using it is exactly the same:

```python
with timer():
    time.sleep(1) # Wait for 1 second

# Output: The block took 1.0000 seconds to execute.
```

### Common Use Cases

Context managers are excellent for managing resources:

*   **File handling:** As we've seen, to ensure files are closed.
*   **Database connections:** To ensure connections are closed and transactions are committed or rolled back.
*   **Locks in threading:** To ensure locks are acquired and released correctly.
*   **Network connections:** To manage the lifecycle of a network socket.

Anytime you have a setup and teardown process, a context manager is likely the right tool for the job.

--- 

## Chapter 5.4: Advanced Concepts - Type Hinting

Python is a dynamically typed language, which means you don't have to declare the data type of a variable. While this offers flexibility, it can sometimes lead to bugs that are hard to track down in large projects.

**Type hinting** was introduced in Python 3.5 (and has been improved in every version since) to allow developers to indicate the expected data types of variables, function parameters, and function return values.

**Important:** Type hints are **not enforced** by the Python interpreter at runtime. They are just "hints" for developers and for third-party tools.

### Benefits of Type Hinting

1.  **Improved Readability:** Type hints make your code easier to understand.
2.  **Better Code Completion:** Code editors like VS Code use type hints to provide better autocompletion and suggestions.
3.  **Static Analysis:** Tools like `mypy` can analyze your code before you run it to catch type-related errors.
4.  **Reduced Bugs:** Catching type errors early can prevent many common bugs.

### 1. Basic Type Hinting

#### Hinting Variables

You can hint the type of a variable using a colon `: `.

```python
name: str = "Alice"
age: int = 30
is_student: bool = True
```

#### Hinting Functions

This is the most common use case. You hint the types of parameters and the return value.

*   Parameter syntax: `parameter_name: type`
*   Return value syntax: `-> type`

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

def add(x: int, y: int) -> int:
    return x + y

# A function that doesn't return anything should be hinted to return 'None'
def print_message(message: str) -> None:
    print(message)
```

### 2. The `typing` Module

For more complex types, Python provides the `typing` module.

#### `List`, `Tuple`, `Dict`, `Set`

To hint collections, you import the specific type from the `typing` module.

```python
from typing import List, Tuple, Dict, Set

# A list of integers
numbers: List[int] = [1, 2, 3]

# A tuple containing a string and an integer
user_profile: Tuple[str, int] = ("Alice", 30)

# A dictionary with string keys and float values
prices: Dict[str, float] = {"apple": 0.99, "banana": 0.59}

# A set of strings
unique_names: Set[str] = {"John", "Jane", "Peter"}
```
*(Note: As of Python 3.9, you can use the built-in types directly, e.g., `list[int]` instead of `List[int]`. However, the `typing` module version is still required for compatibility with older Python versions.)*

#### `Union` and `Optional`

*   `Union`: When a variable can be one of several types.
*   `Optional`: A shorthand for `Union[SomeType, None]`. Use it when a value could be `None`.

```python
from typing import Union, Optional

# This variable can be either an int or a float
numeric_value: Union[int, float] = 10.5

# This function might return a string, or None if the user is not found
def find_user(user_id: int) -> Optional[str]:
    if user_id in db:
        return db[user_id]
    else:
        return None

# 'name' can be either a string or None
name: Optional[str] = find_user(123)
```

#### `Any`

`Any` is a special type that is compatible with every type. It essentially means "I don't know or don't care what the type is." Use it as a last resort.

```python
from typing import Any

def process_data(data: Any) -> Any:
    # ... we can do anything with 'data' ...
    return data
```

### 3. Using `mypy` for Static Type Checking

`mypy` is a static type checker for Python. It's a third-party tool that you can install via pip.

```bash
pip install mypy
```

Now, consider this Python file (`my_code.py`):

```python
def add(x: int, y: int) -> int:
    return x + y

# This is a type error! We are passing a string instead of an int.
result = add(5, "10")
print(result)
```
If you run this with `python my_code.py`, you will get a `TypeError` at runtime.

But if you run `mypy` on it first:
```bash
mypy my_code.py
```
`mypy` will catch the error before you even run the code:
```
my_code.py:5: error: Argument 2 to "add" has incompatible type "str"; expected "int"
Found 1 error in 1 file (checked 1 source file)
```
Integrating `mypy` into your development workflow (e.g., in your CI/CD pipeline) can significantly improve the quality and robustness of your code. Type hinting is now a standard practice in modern Python development and is highly recommended for any project, big or small.

--- 

# Part 4: The Standard Library

---

## Chapter 6.1: The Standard Library - `os` and `pathlib`

Python's "batteries-included" philosophy is best demonstrated by its rich standard library. The `os` and `pathlib` modules are essential for interacting with the operating system, especially for working with files and directories.

### The Old Way: The `os` Module

The `os` module has been the traditional way to handle OS-level tasks. It provides a large number of functions that interact with the operating system.

A key submodule is `os.path`, used for manipulating file paths.

#### Common `os` and `os.path` Functions

```python
import os

# Get the current working directory
cwd = os.getcwd()
print(f"Current Directory: {cwd}")

# Join path components in an OS-agnostic way
# This will use '\' on Windows and '/' on macOS/Linux
file_path = os.path.join(cwd, "data", "my_file.txt")
print(f"Full Path: {file_path}")

# Check if a path exists
if os.path.exists(file_path):
    print("File exists!")
else:
    print("File does not exist.")

# Check if a path is a file or a directory
print(f"Is it a file? {os.path.isfile(file_path)}")
print(f"Is it a directory? {os.path.isdir(cwd)}")

# List the contents of a directory
print(f"Contents of CWD: {os.listdir(cwd)}")
```

While the `os` module is powerful, working with paths as simple strings can be cumbersome and error-prone. For example, you have to remember to use the correct join function and handle different path separators.

### The Modern Way: The `pathlib` Module (Recommended)

Introduced in Python 3.4, the `pathlib` module offers an object-oriented way to handle filesystem paths. It is the recommended approach for most path manipulation tasks.

With `pathlib`, paths are not strings; they are `Path` objects with associated methods and attributes.

#### Creating `Path` Objects

```python
from pathlib import Path

# Create a Path object for the current directory
cwd = Path.cwd()
print(f"Current Directory: {cwd}")

# You can also create a path from a string
project_dir = Path("d:/my_project")

# Join paths using the '/' operator, which is overloaded
# pathlib automatically uses the correct separator for the OS
file_path = cwd / "data" / "my_file.txt"
print(f"Full Path: {file_path}")
```
Notice how much cleaner joining paths is with the `/` operator compared to `os.path.join()`.

#### `pathlib` Attributes and Methods

Let's see how the same tasks from the `os` example are done with `pathlib`.

```python
from pathlib import Path

file_path = Path("data/my_file.txt") # Assuming this file exists

# Check for existence
if file_path.exists():
    print("File exists!")

# Check type
print(f"Is it a file? {file_path.is_file()}")
print(f"Is it a directory? {file_path.is_dir()}")

# Get different parts of the path
print(f"Parent directory: {file_path.parent}")
print(f"File name: {file_path.name}")
print(f"File stem (name without extension): {file_path.stem}")
print(f"File extension: {file_path.suffix}")
```

#### Reading and Writing Files

`Path` objects also have convenient methods for reading and writing files.

```python
my_path = Path("greetings.txt")

# Write text to the file (this will overwrite the file if it exists)
my_path.write_text("Hello from pathlib!")

# Read the entire content of the file
content = my_path.read_text()
print(content)
```
These methods automatically handle opening and closing the file for you.

#### Listing Files

The `iterdir()` method returns a generator that yields `Path` objects for each item in the directory.

```python
cwd = Path.cwd()

for item in cwd.iterdir():
    if item.is_file():
        print(f"Found file: {item.name}")
```

For more advanced file searching, you can use `glob()` to find files matching a pattern.

```python
# Find all .py files in the current directory and subdirectories
for python_file in Path('.').rglob('*.py'):
    print(python_file)
```

### `os` vs. `pathlib`

| Task                      | `os` / `os.path`                             | `pathlib` (Recommended)                       |
| :------------------------ | :------------------------------------------- | :-------------------------------------------- |
| **Joining Paths**         | `os.path.join('dir', 'file.txt')`            | `Path('dir') / 'file.txt'`                    |
| **Getting Parent Dir**    | `os.path.dirname(path)`                      | `p.parent`                                    |
| **Getting Filename**      | `os.path.basename(path)`                     | `p.name`                                      |
| **Checking Existence**    | `os.path.exists(path)`                       | `p.exists()`                                  |
| **Checking if File**      | `os.path.isfile(path)`                       | `p.is_file()`                                 |
| **Reading a File**        | `with open(path) as f: f.read()`             | `p.read_text()`                               |
| **Listing a Directory**   | `os.listdir(path)` (returns strings)         | `p.iterdir()` (returns Path objects)          |

**Conclusion:** For new code, you should prefer `pathlib` for all filesystem path manipulations. Its object-oriented approach is more intuitive, less error-prone, and leads to more readable code. You may still need the `os` module for a few functions that are not in `pathlib` (like `os.getenv` to get environment variables), but for path-related tasks, `pathlib` is the modern standard.

--- 

## Chapter 6.2: The Standard Library - `datetime`

Working with dates and times is a common requirement in programming. Python's `datetime` module provides a powerful set of classes for manipulating dates and times.

The module provides several main object types:
*   `date`: Represents a date (year, month, day).
*   `time`: Represents a time (hour, minute, second, microsecond).
*   `datetime`: Represents a combination of a date and a time.
*   `timedelta`: Represents a duration or the difference between two dates or times.
*   `timezone`: Represents a time zone.

### 1. `datetime.datetime`: The Most Common Class

The `datetime` class is the one you will use most often.

#### Getting the Current Date and Time

You can get the current date and time using `datetime.now()`.

```python
from datetime import datetime

# Get the current date and time (local time)
now = datetime.now()
print(f"Current local time: {now}")

# Get the current date and time in Coordinated Universal Time (UTC)
utc_now = datetime.utcnow()
print(f"Current UTC time: {utc_now}")
```

#### Creating a Specific `datetime` Object

You can create a `datetime` object by providing the year, month, day, hour, minute, etc.

```python
from datetime import datetime

# Create a specific datetime object
event_time = datetime(2025, 1, 1, 10, 30, 0)
print(f"Event time: {event_time}")
```

#### Accessing Components

You can easily access individual components of a `datetime` object.

```python
print(f"Year: {event_time.year}")
print(f"Month: {event_time.month}")
print(f"Day: {event_time.day}")
print(f"Hour: {event_time.hour}")
print(f"Minute: {event_time.minute}")
print(f"Weekday: {event_time.weekday()}") # Monday is 0 and Sunday is 6
```

### 2. Formatting Dates and Times: `strftime()`

The `strftime()` method is used to format a `datetime` object into a human-readable string. It uses a set of format codes.

Common format codes:
*   `%Y`: Year with century (e.g., 2024)
*   `%m`: Month as a zero-padded decimal number (01, 02, ..., 12)
*   `%d`: Day of the month as a zero-padded decimal number (01, 02, ..., 31)
*   `%H`: Hour (24-hour clock) as a zero-padded decimal number (00, 01, ..., 23)
*   `%M`: Minute as a zero-padded decimal number (00, 01, ..., 59)
*   `%S`: Second as a zero-padded decimal number (00, 01, ..., 59)
*   `%A`: Weekday as full name (e.g., Monday)
*   `%B`: Month as full name (e.g., January)

```python
now = datetime.now()

# Format the datetime object into a string
formatted_string = now.strftime("%Y-%m-%d %H:%M:%S")
print(f"Formatted as Y-m-d H:M:S: {formatted_string}")

pretty_format = now.strftime("Today is %A, %B %d, %Y")
print(f"A prettier format: {pretty_format}")
```

### 3. Parsing Strings into Dates: `strptime()`

The `strptime()` method (string parse time) is the reverse of `strftime()`. It creates a `datetime` object from a string that matches a specific format.

```python
date_string = "2024-07-21 15:45:00"
format_code = "%Y-%m-%d %H:%M:%S"

# Create a datetime object from the string
parsed_datetime = datetime.strptime(date_string, format_code)

print(f"Parsed datetime object: {parsed_datetime}")
print(f"Year from parsed object: {parsed_datetime.year}")
```
**Important:** The format code provided to `strptime()` must exactly match the format of the date string, otherwise you will get a `ValueError`.

### 4. `timedelta`: Working with Durations

A `timedelta` object represents a duration. You can use it to perform date arithmetic.

```python
from datetime import datetime, timedelta

now = datetime.now()
print(f"Current time: {now}")

# Create a timedelta of 3 days and 5 hours
duration = timedelta(days=3, hours=5)

# Add the duration to the current time
future_time = now + duration
print(f"Time in 3 days and 5 hours: {future_time}")

# Subtract a duration
past_time = now - timedelta(weeks=2)
print(f"Time two weeks ago: {past_time}")
```

#### Calculating the Difference Between Two Dates

You can also find the duration between two `datetime` objects by subtracting them.

```python
start_date = datetime(2024, 1, 1)
end_date = datetime(2024, 7, 21)

difference = end_date - start_date
print(f"Difference between dates: {difference}")
print(f"Difference in days: {difference.days}")
print(f"Difference in total seconds: {difference.total_seconds()}")
```

The `datetime` module is essential for any application that deals with scheduling, logging, or any form of time-based data.

--- 

## Chapter 6.3: The Standard Library - `collections`

The `collections` module provides specialized container datatypes that are alternatives to Python's general-purpose built-in containers like `dict`, `list`, `set`, and `tuple`. These specialized containers can help solve specific problems in a cleaner and more efficient way.

### 1. `namedtuple`: Tuples with Named Fields

A `namedtuple` is a simple way to create a tuple subclass with named fields. This can make your code much more readable because you can access elements by name instead of by index.

**Without `namedtuple`:**
```python
# Using a regular tuple
point = (10, 20)
print(f"X coordinate: {point[0]}, Y coordinate: {point[1]}")
```
This is not very descriptive. `point[0]` doesn't immediately tell you what it represents.

**With `namedtuple`:**
```python
from collections import namedtuple

# Create a 'Point' namedtuple class
Point = namedtuple('Point', ['x', 'y'])

# Create an instance of our new class
point = Point(10, 20)

# Access elements by name - much more readable!
print(f"X coordinate: {point.x}, Y coordinate: {point.y}")
```
`namedtuple` objects are still tuples, so they are immutable and you can still access elements by index (`point[0]`).

### 2. `defaultdict`: Dictionaries with Default Values

A `defaultdict` is a subclass of `dict` that allows you to specify a "default factory" function. If you try to access or modify a key that is not in the dictionary, the `defaultdict` will automatically create it with a default value provided by the factory.

This is extremely useful for grouping items.

**Without `defaultdict`:**
```python
words = ["apple", "banana", "apple", "cherry", "banana", "apple"]
word_counts = {}

for word in words:
    if word not in word_counts:
        word_counts[word] = 0
    word_counts[word] += 1
```
This `if` check is a common but slightly verbose pattern.

**With `defaultdict`:**
```python
from collections import defaultdict

# Provide 'int' as the default factory. When a new key is accessed,
# it will be initialized with the result of int(), which is 0.
word_counts = defaultdict(int)

for word in words:
    # No 'if' check needed! If the key doesn't exist, it's created with a value of 0.
    word_counts[word] += 1

print(word_counts)
# Output: defaultdict(<class 'int'>, {'apple': 3, 'banana': 2, 'cherry': 1})
```
You can use other factories too, like `list` (to create a list for a new key) or `set`.

### 3. `Counter`: A Dictionary for Counting

A `Counter` is a `dict` subclass for counting hashable objects. It's a specialized tool for the exact use case we saw with `defaultdict(int)`, but it's even more convenient.

```python
from collections import Counter

words = ["apple", "banana", "apple", "cherry", "banana", "apple"]

# You can initialize a Counter directly from an iterable
word_counts = Counter(words)

print(word_counts)
# Output: Counter({'apple': 3, 'banana': 2, 'cherry': 1})

# It also comes with a useful 'most_common()' method
print(word_counts.most_common(2)) # Get the 2 most common items
# Output: [('apple', 3), ('banana', 2)]
```

### 4. `deque`: A Double-Ended Queue

A `deque` (pronounced "deck") is a list-like container that supports fast appends and pops from **both** ends.

Lists are very fast at appending and popping from the end (`append()` and `pop()`), but doing the same at the beginning (`insert(0, ...)` or `pop(0)`) is very slow because all the other elements have to be shifted. A `deque` is optimized for these operations.

```python
from collections import deque

# Create a deque
d = deque(['c', 'd', 'e'])

# Fast appends to the right
d.append('f')
print(d) # Output: deque(['c', 'd', 'e', 'f'])

# Fast appends to the left
d.appendleft('b')
print(d) # Output: deque(['b', 'c', 'd', 'e', 'f'])

# Fast pops from the right
d.pop()
print(d) # Output: deque(['b', 'c', 'd', 'e'])

# Fast pops from the left
d.popleft()
print(d) # Output: deque(['c', 'd', 'e'])
```
A `deque` can also have a maximum size. When a new item is added and the deque is full, the item at the opposite end is automatically discarded. This is useful for keeping a "log" of the last N items.

```python
last_five_actions = deque(maxlen=5)
last_five_actions.append("Action 1")
last_five_actions.append("Action 2")
last_five_actions.append("Action 3")
last_five_actions.append("Action 4")
last_five_actions.append("Action 5")
print(last_five_actions)
# Output: deque(['Action 1', 'Action 2', 'Action 3', 'Action 4', 'Action 5'], maxlen=5)

last_five_actions.append("Action 6") # "Action 1" is pushed out
print(last_five_actions)
# Output: deque(['Action 2', 'Action 3', 'Action 4', 'Action 5', 'Action 6'], maxlen=5)
```

The `collections` module provides many other useful data types, but these four are among the most commonly used. They can help you write more expressive, readable, and efficient Python code.

--- 

# Part 5: What's New in Python 3.14

---

## Chapter 7.1: What's New in Python 3.14

***Disclaimer:** As of the creation of this document, Python 3.14 has not been released. The features listed below are hypothetical and are based on recent trends in Python's development and common feature requests from the community. They are intended to be illustrative of the kinds of improvements that a new Python version might bring.*

---

Python 3.14 continues the language's focus on improving performance, developer experience, and clarity. This version introduces several exciting new features and significant optimizations.

### 1. Performance: The JIT Compiler

The most significant feature in Python 3.14 is the experimental **Just-In-Time (JIT) compiler**. Building on the performance improvements of previous versions, the JIT compiler can selectively compile parts of your Python code into highly optimized machine code at runtime.

*   **How it works:** The interpreter identifies "hot" code paths (code that is executed frequently, like loops) and compiles them on the fly.
*   **Impact:** This can lead to substantial speed-ups for CPU-bound applications, especially in scientific computing and data processing, bringing Python's performance closer to that of statically compiled languages in certain scenarios.
*   **Usage:** The JIT compiler is disabled by default in this experimental phase. You can enable it with a command-line flag:
    ```bash
    python -X jit my_script.py
    ```

### 2. Syntactic Sugar: The "it" Keyword

Python 3.14 introduces a new contextual keyword, `it`, to simplify lambda functions and other short anonymous functions.

**Before Python 3.14:**
```python
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, numbers))
```

**With Python 3.14:**
```python
# The 'it' keyword implicitly refers to the item being processed
squared = list(map(it**2, numbers))

# Also works with functions like filter()
evans = list(filter(it % 2 == 0, numbers))
```
This feature aims to make functional-style programming more concise and readable.

### 3. Enhanced Type Hinting: `TypedDict` Improvements

Working with dictionary schemas is now easier. `TypedDict` has been enhanced to support more complex validation and default values directly within the type definition.

```python
from typing import TypedDict, NotRequired

class UserProfile(TypedDict):
    user_id: int
    name: str
    # 'email' is not required
    email: NotRequired[str]
    # 'is_active' has a default value if not provided
    is_active: bool = True

# mypy can now validate this structure more effectively
def process_user(profile: UserProfile):
    # ...
```

### 4. Standard Library: Structured Concurrency in `asyncio`

The `asyncio` library now has built-in support for **structured concurrency** through `asyncio.TaskGroup`. This makes it much easier to manage multiple concurrent tasks and handle errors correctly.

**Before Python 3.14 (managing tasks manually):**
```python
async def main():
    task1 = asyncio.create_task(some_coro())
    task2 = asyncio.create_task(another_coro())
    await task1
    await task2
```
This becomes complicated when you need to handle cancellation and errors across tasks.

**With Python 3.14 `TaskGroup`:**
```python
import asyncio

async def main():
    try:
        async with asyncio.TaskGroup() as tg:
            tg.create_task(some_coro())
            tg.create_task(another_coro())
        # The 'async with' block waits until all tasks in the group are complete.
    except Exception as e:
        print(f"An error occurred in one of the tasks: {e}")

# If one task fails, all other tasks in the group are automatically cancelled.
```
This pattern makes concurrent code safer and more robust, preventing common issues like dangling tasks.

These are just a few of the exciting, albeit hypothetical, developments in Python 3.14. As always, for official information, be sure to check the Python documentation upon its release.

--- 

# Part 6: Practical Examples

---

## Chapter 8.1: Example 1: Simple Calculator

```python
"""
A simple command-line calculator that can perform addition, subtraction,
multiplication, and division.
"""

def add(x, y):
    """Adds two numbers."""
    return x + y

def subtract(x, y):
    """Subtracts two numbers."""
    return x - y

def multiply(x, y):
    """Multiplies two numbers."""
    return x * y

def divide(x, y):
    """Divides two numbers. Handles division by zero."""
    if y == 0:
        return "Error! Division by zero."
    return x / y

def main():
    """Main function to run the calculator."""
    print("Select operation:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")

    while True:
        # Take input from the user
        choice = input("Enter choice(1/2/3/4): ")

        # Check if choice is one of the four options
        if choice in ['1', '2', '3', '4']:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
            except ValueError:
                print("Invalid input. Please enter a number.")
                continue

            if choice == '1':
                print(f"{num1} + {num2} = {add(num1, num2)}")
            elif choice == '2':
                print(f"{num1} - {num2} = {subtract(num1, num2)}")
            elif choice == '3':
                print(f"{num1} * {num2} = {multiply(num1, num2)}")
            elif choice == '4':
                result = divide(num1, num2)
                print(f"{num1} / {num2} = {result}")
            
            # Ask if the user wants to do another calculation
            next_calculation = input("Let's do next calculation? (yes/no): ")
            if next_calculation.lower() != 'yes':
                break
        else:
            print("Invalid input. Please enter a valid choice.")

# This line ensures that the main() function is called only when the script
# is executed directly (not when imported as a module).
if __name__ == "__main__":
    main()
```

--- 

## Chapter 8.2: Example 2: File Organizer

```python
"""
A script to organize files in a directory by their extension.
It will create subdirectories for each file type (e.g., 'images', 'documents')
and move the files into the corresponding directory.

WARNING: This script modifies files on your filesystem.
Use with caution and preferably on a test directory first.
"""

import os
from pathlib import Path

# Mapping of file extensions to directory names
# You can customize this dictionary
FILE_EXTENSIONS = {
    # Images
    ".jpg": "images",
    ".jpeg": "images",
    ".png": "images",
    ".gif": "images",
    ".bmp": "images",
    ".svg": "images",

    # Documents
    ".pdf": "documents",
    ".doc": "documents",
    ".docx": "documents",
    ".txt": "documents",
    ".ppt": "documents",
    ".pptx": "documents",
    ".xls": "documents",
    ".xlsx": "documents",

    # Audio
    ".mp3": "audio",
    ".wav": "audio",
    ".flac": "audio",

    # Video
    ".mp4": "video",
    ".mov": "video",
    ".avi": "video",
    ".mkv": "video",

    # Archives
    ".zip": "archives",
    ".rar": "archives",
    ".7z": "archives",
}

def organize_directory(directory_path: Path):
    """
    Organizes the files in the given directory by their extension.

    Args:
        directory_path (Path): The path to the directory to organize.
    """
    if not directory_path.is_dir():
        print(f"Error: Directory not found at '{directory_path}'")
        return

    print(f"Scanning directory: {directory_path}\n")

    for item in directory_path.iterdir():
        # We only care about files
        if not item.is_file():
            continue
        
        # Skip this script itself
        if item.name == __file__:
            continue

        file_extension = item.suffix.lower()
        
        # Find the target directory name from our mapping
        target_dir_name = FILE_EXTENSIONS.get(file_extension)

        if target_dir_name:
            # Create the target directory if it doesn't exist
            target_dir = directory_path / target_dir_name
            target_dir.mkdir(exist_ok=True) # exist_ok=True prevents an error if the dir already exists

            # Construct the new path for the file
            new_path = target_dir / item.name
            
            # Move the file
            try:
                item.rename(new_path)
                print(f"Moved '{item.name}' to '{target_dir_name}/'")
            except OSError as e:
                print(f"Error moving '{item.name}': {e}")
        else:
            print(f"Skipping '{item.name}' (unknown file type)")

def main():
    """Main function to prompt user for directory and run the organizer."""
    try:
        target_directory = input("Enter the path to the directory you want to organize: ")
        
        # Convert the input string to a Path object
        directory_path = Path(target_directory)
        
        organize_directory(directory_path)
        print("\nOrganization complete!")

    except KeyboardInterrupt:
        print("\nOperation cancelled by user.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
```

--- 

## Chapter 8.3: Example 3: Simple Web Scraper

```python
"""
A simple web scraper that fetches the title and all the links from a given URL.

This example requires third-party libraries: 'requests' and 'beautifulsoup4'.
You need to install them first:
pip install requests beautifulsoup4

WARNING: Web scraping can be against the terms of service of some websites.
Always check the website's 'robots.txt' file and terms of service before scraping.
This script is for educational purposes only.
"""

import requests
from bs4 import BeautifulSoup
from urllib.parse import urljoin

def scrape_website(url: str):
    """
    Scrapes a website for its title and all unique links.

    Args:
        url (str): The URL of the website to scrape.
    """
    print(f"Attempting to scrape: {url}\n")

    try:
        # Send an HTTP GET request to the URL
        response = requests.get(url, timeout=10)
        
        # Raise an exception if the request was unsuccessful (e.g., 404 Not Found)
        response.raise_for_status()

    except requests.exceptions.RequestException as e:
        print(f"Error fetching the URL: {e}")
        return

    # Parse the HTML content of the page with BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')

    # --- 1. Get the title of the page ---
    try:
        title = soup.title.string.strip()
        print(f"Page Title: {title}\n")
    except AttributeError:
        print("Could not find a title for the page.\n")

    # --- 2. Find and print all links ---
    links = set() # Use a set to store unique links
    
    # Find all 'a' (anchor) tags which are used for hyperlinks
    for link_tag in soup.find_all('a'):
        href = link_tag.get('href')
        
        # Check if the href attribute exists and is not empty
        if href:
            # The 'href' can be a relative path (e.g., '/about-us').
            # We use urljoin to create an absolute URL.
            absolute_link = urljoin(url, href)
            links.add(absolute_link)

    if links:
        print(f"Found {len(links)} unique links:")
        for i, link in enumerate(sorted(list(links)), 1):
            print(f"{i}. {link}")
    else:
        print("No links found on the page.")

def main():
    """Main function to prompt for URL and run the scraper."""
    print("--- Simple Web Scraper ---")
    url = input("Enter the URL of the website you want to scrape (e.g., http://example.com): ")

    if not url.startswith("http"):
        url = "http://" + url

    scrape_website(url)

if __name__ == "__main__":
    main()
```

--- 

## Chapter 8.3: Example 3: Simple Web Scraper

```python
"""
A simple web scraper that fetches the title and all the links from a given URL.

This example requires third-party libraries: 'requests' and 'beautifulsoup4'.
You need to install them first:
pip install requests beautifulsoup4

WARNING: Web scraping can be against the terms of service of some websites.
Always check the website's 'robots.txt' file and terms of service before scraping.
This script is for educational purposes only.
"""

import requests
from bs4 import BeautifulSoup
from urllib.parse import urljoin

def scrape_website(url: str):
    """
    Scrapes a website for its title and all unique links.

    Args:
        url (str): The URL of the website to scrape.
    """
    print(f"Attempting to scrape: {url}\n")

    try:
        # Send an HTTP GET request to the URL
        response = requests.get(url, timeout=10)
        
        # Raise an exception if the request was unsuccessful (e.g., 404 Not Found)
        response.raise_for_status()

    except requests.exceptions.RequestException as e:
        print(f"Error fetching the URL: {e}")
        return

    # Parse the HTML content of the page with BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')

    # --- 1. Get the title of the page ---
    try:
        title = soup.title.string.strip()
        print(f"Page Title: {title}\n")
    except AttributeError:
        print("Could not find a title for the page.\n")

    # --- 2. Find and print all links ---
    links = set() # Use a set to store unique links
    
    # Find all 'a' (anchor) tags which are used for hyperlinks
    for link_tag in soup.find_all('a'):
        href = link_tag.get('href')
        
        # Check if the href attribute exists and is not empty
        if href:
            # The 'href' can be a relative path (e.g., '/about-us').
            # We use urljoin to create an absolute URL.
            absolute_link = urljoin(url, href)
            links.add(absolute_link)

    if links:
        print(f"Found {len(links)} unique links:")
        for i, link in enumerate(sorted(list(links)), 1):
            print(f"{i}. {link}")
    else:
        print("No links found on the page.")

def main():
    """Main function to prompt for URL and run the scraper."""
    print("--- Simple Web Scraper ---")
    url = input("Enter the URL of the website you want to scrape (e.g., http://example.com): ")

    if not url.startswith("http"):
        url = "http://" + url

    scrape_website(url)

if __name__ == "__main__":
    main()
```
