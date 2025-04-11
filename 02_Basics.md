# 📘 Python Module Notes - Day 1

## ✅ Topics to be Covered

- Basics  
- Data Structures  
- Dictionary, Strings, List Comprehensions  
- Functions, Modules, OOP  
- Numpy, Pandas, Matplotlib, Requests  
- Assignments, Case Studies, Thought Processes, MongoDB  

---

## 🐍 What is Python?

Python is a **high-level, interpreted** programming language that is widely used in software development, data science, automation, artificial intelligence, and more.

### ✨ Key Features of Python

- **Interpreted Language**  
  Python executes code **line-by-line**, meaning there's no need to compile the code before running it. This makes debugging and development faster and easier.
  - ⚠️ Drawback: Because of its interpreted nature, Python can be **slightly slower** compared to compiled languages due to additional overhead like **jump instructions**.

- **Ease of Writing Code**  
  Python's syntax is simple, readable, and concise, which reduces development time and makes it beginner-friendly.

- **Multithreading Support**  
  Python supports multithreading, although it's **~25% slower than Java** due to the **Global Interpreter Lock (GIL)**.  

  #### What is Multithreading?  
  Multithreading allows multiple threads (smaller units of a process) to run concurrently. This is especially useful for **I/O-bound tasks**, like reading files or sending network requests.

- **Easy to Learn**  
  Python is one of the easiest programming languages to learn due to its minimalistic syntax and extensive documentation/community support.

- **High-Level Language**  
  Python abstracts away most of the low-level operations (like memory management), allowing developers to focus on the logic and structure of the code.

- **Platform Independent**  
  Python code can run on different platforms (Windows, Linux, macOS) without modification, as long as the Python interpreter is installed.

- **Dynamically Typed**  
  You **don't need to declare variable types** explicitly. Python figures it out at runtime.
  ```python
  x = 10       # x is an integer
  x = "hello"  # now x is a string

## 🧱 Object-Oriented Programming Language

Python supports the four core **OOP principles**:

- **Inheritance**  
  Enables one class to inherit properties and behaviors from another.

- **Polymorphism**  
  Allows different classes to be treated as instances of the same class through a common interface.

- **Encapsulation**  
  Keeps data safe from outside interference and misuse by restricting access to internal components.

- **Abstraction**  
  Hides complex implementation details and shows only the essential features of the object.

---

## ⚙️ Scripting Language

Python can be used as a **scripting language** to:

- Automate repetitive tasks  
- Write small utility programs  
- Glue together components from other programs

### 📌 What is a Scripting Language?

A scripting language is designed to write **small programs (scripts)** to automate tasks such as:

- File manipulation
- Web scraping
- Data parsing
- Task scheduling

> 💡 You can create mini-projects using Python in **script mode** for automation, bots, file operations, and more!

---

## 💬 Interactive Language

Python allows you to write and execute code **interactively** using the **REPL (Read-Evaluate-Print Loop)**:

```bash
$ python
>>> print("Hello")
Hello
```

This makes Python great for quick testing and learning on the go!

---

## 🆓 Open Source and Free to Use

Python is **free to download, use, and distribute**. It’s backed by a **large and active open-source community**, with thousands of libraries and frameworks contributed by developers around the world.

---

## 🧠 Functional Programming Language

Python supports **functional programming** paradigms:

- Functions are **first-class citizens** (can be passed as arguments, returned from other functions, etc.)
- Supports **higher-order functions**
- Includes **lambda expressions** (anonymous functions)
- Encourages the use of **immutable data structures**

---

## 🧩 Methods vs Functions

- A **function inside a class** is called a **method**.
- A **function outside any class** is a **regular (native) function**.

```python
def greet():       # Function
    print("Hello")

class A:
    def greet(self):  # Method
        print("Hi")
```

> 💡 **Tip for Revision**:  
Break each topic into small subtopics, use lots of examples, and revisit by building **mini-scripts** or experimenting in the **REPL shell**.

## 🕰️ History of Python

- **Invented** in the **Netherlands** in the early 1990s by **Guido van Rossum**
- Named after the comedy group **"Monty Python"**, not the snake 🐍
- **Open-sourced** from the beginning
- Originally considered a **scripting language**, but now is much more:
  - **Scalable** and used in enterprise-grade applications
  - **Versatile** — supports procedural, object-oriented, and functional programming
  - **Cross-platform** — runs on Windows, Linux, macOS
  - Used in **web development**, **data science**, **AI/ML**, **automation**, **IoT**, and more
- Backed by a strong community and **rich ecosystem** of libraries and frameworks (like Django, Flask, NumPy, Pandas)

---

## 📦 Python Release Timeline

| Date               | Version     | Notes                               |
|--------------------|-------------|-------------------------------------|
| **Dec 1989**       | Start       | Implementation began                |
| **1990**           | Internal    | First internal release at CWI       |
| **Jan 26, 1994**   | 1.0.0       | First official public release       |
| **Oct 16, 2000**   | 2.0         | Added garbage collection, Unicode support |
| **Dec 3, 2008**    | 3.0         | Major overhaul (not backward compatible) |
| **Dec 30, 2015**   | 3.6         | Introduced f-strings, type hints, etc. |

> 🔁 **Python 3 introduced syntactical changes**, making it incompatible with Python 2 in many ways (e.g., `print` is now a function: `print("Hello")`)

---

> 💡 Python continues to evolve with regular updates improving performance, syntax, and developer experience.


## 🆚 What to Choose: Python or Java?

Both **Python** and **Java** are powerful, widely-used languages — but they serve different needs depending on the project.

### ✅ Why Choose Python?

- **Ease of Use**: Python is known for its clean, readable syntax — ideal for beginners and rapid development.
- **Quick Development**: Fewer lines of code needed compared to Java.
- **Platform Ready**:  
  - **Pre-installed in Linux/macOS** (just open terminal and use it)
  - On **Windows**, you need to **manually install Python**
- **Dynamic Typing**: No need to declare variable types.
- **Great for Scripting & Automation**
- Strong libraries for:
  - **Data Science** (Pandas, NumPy, SciPy)
  - **Web Development** (Django, Flask)
  - **Automation**, **AI**, **Machine Learning**, **DevOps**

### 🤔 Why Choose Java?

- **Speed**: Java tends to run faster than Python due to its compiled nature and multithreading support.
- **Static Typing**: Useful in large codebases for type safety.
- **Robust Tools**: Enterprise-level applications and large-scale systems.
- **Strong OOP model**
- Better performance in **multi-threaded environments** and **Android development**.

> 💡 **Choose Python** for faster prototyping, data-driven projects, automation, and when ease of development matters more than raw speed.  
> **Choose Java** for performance-intensive enterprise apps, Android development, or large-scale systems where static typing is a must.

---

## 🐍 Python's "Benevolent Dictator For Life"

> *"Python is an experiment in how much freedom programmers need.  
Too much freedom and nobody can read another's code; too little and expressiveness suffers."*  
> — **Guido van Rossum**, Creator of Python

This quote reflects Python’s balance between **flexibility** and **readability**, allowing developers to write expressive code while maintaining clarity.


## ▶️ Executing Python

To start using Python on your system (especially on **Windows**), you need to check if it's already installed. Use the **Command Prompt (CMD)** for this.

---

### 🔍 Check Installation via CMD (Windows)

Open **Command Prompt** and run the following commands:

#### ✅ Check Python
```bash
python --version
```

If installed, you'll see something like:

```nginx
Python 3.x.x
```

### ✅ Check `conda` (if using Anaconda distribution)

```bash
conda --version
```

If installed:

```nginx
conda x.x.x
```

### ❌ Not Installed?

If any of the above commands are not recognized, you'll get an error like:

```kotlin
'python' is not recognized as an internal or external command
```

### 👉 Solution:

Go to the official Python website:  
[https://www.python.org/downloads/](https://www.python.org/downloads/)

Download the latest stable version for **Windows**.

During installation, make sure to check the box:  
✅ *“Add Python to PATH”*  
*(This ensures Python is accessible from anywhere in the terminal)*

---

> 💡 **Tip**:  
If you're working with **Data Science** or **Machine Learning**, consider installing the **Anaconda distribution**, which includes:

- Python  
- pip  
- conda  
- Popular libraries like **NumPy**, **Pandas**, and **Jupyter Notebook**


## 🧪 First Python Program

The simplest way to get started with Python is by printing something to the console.

```python
print("Hello World")
```

🖨️ This will output:

```nginx
Hello World
```

✅ This is your first step into **Python programming!**

## 🌟 Why Python is Easy, Beautiful, and Beginner-Friendly

Python is often considered one of the most beginner-friendly programming languages because of its **commonsense syntax**. It feels like writing English!

For example, in Python's **IDLE** or interactive mode (REPL), you can simply write:

```python
"Hello World"
```

🔁 And it will immediately **output**:
```bash
'Hello World'
```

(Behind the scenes, Python automatically wraps this as a `print()` operation in interactive mode.)

This makes Python **interactive**, **fun**, and great for learning quickly.

---

## 🧠 What are Variables?

A **variable** is a name that refers to a **memory location** which stores data.  
These names are also called **identifiers**.

```python
x = 10
name = "Alice"
```

Here:

- `x` is a variable storing the integer `10`
- `name` is a variable storing the string `"Alice"`

---

## 🧾 Naming Conventions for Variables in Python

### ✅ Valid Names:

- Must start with a **letter (a-z, A-Z)** or **underscore (_)**
- Can contain **letters, digits (0–9)**, and underscores
- Are **case-sensitive** (`Name` and `name` are different)
- Should **not be Python keywords** (like `for`, `if`, `class`, etc.)

```python
_valid_name = "Okay"
user1 = "Valid"
UserName = "Also valid"
```

### ❌ Invalid Names:

```python
1user = "Starts with a digit"     # ❌
user-name = "Hyphens not allowed" # ❌
class = "Keyword"                 # ❌
```

> 💡 **Tip:**  
Use **descriptive variable names** for better readability.

```python
score = 95
student_name = "Rahul"
```

Python is all about **clarity** and **simplicity** — that’s why it’s so beautiful to use 💖

## 🌀 Dynamically Typed Language

In Python, you don’t need to declare the data type of a variable explicitly.  
The interpreter automatically understands the type at runtime.

```python
a = 10
print(type(a))   # <class 'int'>

a = "Hello World"
print(type(a))   # <class 'str'>
```

This flexibility is why Python is called a **dynamically typed language**.

✅ **Benefit**:  
You can reassign different types of values to the same variable without errors.  
Great for quick scripting, prototyping, and high-precision tasks.

---

💡 **Precision Advantage over Java**:  
In Java, data types (like `int`, `long`) have fixed sizes and overflow if exceeded.

**For example:**

```java
long big = 9223372036854775807L; // Max value of long
System.out.println(big * big);   // Will overflow and give unexpected result
```

But in **Python**, integers have **arbitrary precision**:

```python
big = 9223372036854775807
print(big * big)  # No overflow, prints full result accurately
```

✅ **Python handles large integers internally using big integers**,  
while Java throws overflow or truncates the result.

---

🧪 **Checking the Data Type**  
Use the built-in `type()` function:

```python
x = 3.14
print(type(x))   # <class 'float'>
```

🧱 **No Primitive Data Types**  
Unlike Java (which has primitive types like `int`, `float`, `boolean`),  
**Python treats everything as an object**, even basic types like numbers and strings.

```python
n = 5
print(type(n))         # <class 'int'>
print(n.bit_length())  # Objects have methods
```

💬 **Python’s simplicity, dynamic typing, and object-oriented nature**  
make it **powerful** yet **beginner-friendly** 🚀

## ✅ Boolean Values in Python

In Python, Boolean values represent truth values: `True` and `False`.

```python
a = True
b = False
```

## ✅ Boolean Values in Python

These are the only two Boolean literals in Python:

- `True`
- `False`

🔹 **Boolean values are case-sensitive** — use `True` and `False` with capital first letters.

🔹 **Internally**, Python treats:
- `True` as `1`
- `False` as `0`

So you can even perform arithmetic with them:

```python
print(True + True)   # 2
print(False + 5)     # 5
```

💡 **Tip:**  
Use Boolean values for condition checking, comparisons, and control flow:

```python
x = 10
print(x > 5)    # True
print(x == 20)  # False
```

**🧠 Booleans are a key part of decision-making in Python programming.**

🧾 **Multiple Variable Assignment in One Line**

You can initialize multiple variables in a single line:

```python
a, b, c = 1, 2, 3
```

✅ This is a neat and Pythonic way to assign values, especially when dealing with related data.

🧮 **Program to Swap Two Numbers in Python**

Let’s say:

```python
a = 10
b = 20
```

✅ **Method 1: Using a Temporary Variable**
```python
c = a
a = b
b = c
print(a, b)  # Output: 20 10
```

✅ **Method 2: Using Arithmetic Operations**
```python
a = a + b
b = a - b
a = a - b
print(a, b)  # Output: 20 10
```

✅ **Method 3: Pythonic Way using Tuple Unpacking**
```python
a, b = b, a
print(a, b)  # Output: 20 10
```

💡 Python’s multiple assignment feature makes swapping values super easy and elegant!

# 🔢 Arithmetic Operators in Python

Python supports the following arithmetic operators:

| Operator | Description          | Example         | Output |
|----------|----------------------|-----------------|--------|
| `+`      | Addition              | `10 + 5`        | `15`   |
| `-`      | Subtraction           | `10 - 5`        | `5`    |
| `*`      | Multiplication        | `10 * 5`        | `50`   |
| `/`      | Division (float)      | `10 / 5`        | `2.0`  |
| `//`     | Floor Division        | `10 // 3`       | `3`    |
| `%`      | Modulus (remainder)   | `10 % 3`        | `1`    |
| `**`     | Exponentiation        | `2 ** 3`        | `8`    |

---

### ✅ Examples with Code and Output:

```python
a = 10
b = 3

print("Addition:", a + b)        # Output: 13
print("Subtraction:", a - b)     # Output: 7
print("Multiplication:", a * b)  # Output: 30
print("Division:", a / b)        # Output: 3.333...
print("Floor Division:", a // b) # Output: 3
print("Modulus:", a % b)         # Output: 1
print("Exponentiation:", a ** b) # Output: 1000
```

💡 **Tip:**

- Use `//` when you want **integer division**.
- Use `%` to check if a number is **even** or **divisible** by another.

```python
num = 6
print(num % 2 == 0)  # True (Even number)
```

🐍 Python makes math clean, simple, and intuitive! 🚀

# 🧘‍♂️ The Zen of Python by Tim Peters

The **Zen of Python** is a collection of guiding principles for writing computer programs in Python.  
Authored by **Tim Peters**, it reflects the **philosophy** and **design mindset** behind the Python language.

### 🧩 How to View It in Python:
You can view the Zen directly in Python by typing:

```python
import this
```

## 📜 The Zen of Python:

```vbnet
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

### 💬 Why It Matters:

These principles are not strict rules, but they offer insight into **Pythonic thinking**.

They emphasize **readability**, **simplicity**, and **clarity** — all core strengths of Python.

📌 **Keep them in mind** as you write your code — they’ll help you write **cleaner and more maintainable** programs!

## 🔁 Relational (Comparison) Operators in Python

Relational operators are used to compare two values. They return a Boolean value (`True` or `False`).

| Operator | Description             | Example           | Output  |
|----------|-------------------------|-------------------|---------|
| `==`     | Equal to                | `5 == 5`          | `True`  |
| `!=`     | Not equal to            | `5 != 3`          | `True`  |
| `>`      | Greater than            | `7 > 5`           | `True`  |
| `<`      | Less than               | `3 < 2`           | `False` |
| `>=`     | Greater than or equal   | `4 >= 4`          | `True`  |
| `<=`     | Less than or equal      | `2 <= 5`          | `True`  |

### 📌 Example Code:

```python
a = 10
b = 20

print(a == b)   # False
print(a != b)   # True
print(a > b)    # False
print(a < b)    # True
print(a >= 10)  # True
print(b <= 15)  # False
```

💡 **Tip:**

Relational operators are often used in conditions, such as `if`, `while`, and `for` statements.

```python
if a < b:
    print("a is less than b")
```

📘 Relational operators help drive **decision-making** in your programs!

📝 **Comments in Python**

Comments are lines in your code that are **ignored during execution**.

They are used to explain code, improve readability, and help future you (or others) understand what’s happening.

---

✅ **Single-line Comment**

Use the `#` symbol to write single-line comments.

```python
# This is a comment
x = 5  # This is also a comment
```

✅ **Multi-line Comments (Technically strings)**

Python doesn’t have a specific multi-line comment syntax, but you can use triple quotes (`'''` or `"""`) as a workaround.

```python
'''
This is a multi-line comment
explaining the logic below
'''
x = 10 * 2
```

💡 **Note:** Triple-quoted strings do **not** create actual comments, but are often used for multi-line descriptions **if not assigned to any variable**.

---

📘 **Why use comments?**

- Explain complex logic  
- Temporarily disable code  
- Improve maintainability  
- Clarify function purpose  

✨ *Clean code = Clear comments (not too many, not too few)*

🧮 **WAP to print sum of digits of 539 without using if-else or loops**

We can use modulo `%` and division `//` operators multiple times to extract each digit.

```python
num = 539
digit1 = num % 10        # 9
digit2 = (num // 10) % 10  # 3
digit3 = (num // 100) % 10 # 5

total = digit1 + digit2 + digit3
print(total)  # Output: 17
```

✅ **No loops or conditionals used!**

📌 This approach works well for fixed-digit numbers.

### 🗣️ Why Can't We Use Spoken Language as a Programming Language?

Spoken language is **ambiguous** — the same sentence can have multiple interpretations depending on context, tone, or even the person.

#### ⚠️ Example:

> "Put the book on the table in the kitchen."

This sentence could mean:
- Put the book **on the table that is in the kitchen**.
- Take the book that is **on the table** and put it **into the kitchen**.

In programming, **clarity and precision** are essential. Computers need exact instructions — there's no room for interpretation or guessing.

✅ That’s why programming languages are designed to be:
- Unambiguous
- Structured
- Consistent

💡 The goal: one instruction → one clear meaning.

# 🔁 Conditional Statements in Python

Python supports several types of conditional statements to control the flow of execution based on conditions.

---

## ✅ `if` Statement

Executes a block of code **only if** the condition is `True`.

```python
x = 10
if x > 5:
    print("x is greater than 5")
```

📌 **Output:**

```csharp
x is greater than 5
```

## ✅ if-else Statement
Provides an alternative block if the condition is False.

```python
x = 3
if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")
```

📌 **Output:**

```csharp
x is not greater than 5
```

## ✅ if-elif-else Statement
Checks multiple conditions one by one.

```python
x = 0
if x > 0:
    print("Positive")
elif x < 0:
    print("Negative")
else:
    print("Zero")
```

📌 **Output:**

```nginx
Zero
```

## ✅ Nested if Statements
You can nest one `if` inside another.

```python
x = 15
if x > 10:
    if x < 20:
        print("x is between 10 and 20")
```

📌 **Output:**

```pgsql
x is between 10 and 20
```

💡 **Tip**:  
Indentation is crucial in Python.  

Each block under `if`, `else`, or `elif` must be **indented consistently**.

---

📘 **Why Use Conditionals?**
- To control the flow of logic  
- To make decisions  
- To handle multiple execution paths  

✨ They help your code **think and respond** to different situations dynamically!

📌 **No Curly Braces in Python**

Unlike languages like C, C++, or Java which use `{}` to define code blocks,  
**Python uses indentation** to indicate a block of code.

```python
# Example:
if x > 0:
    print("Positive number")  # Indented block
```

✅ **Indentation improves readability** and enforces clean, structured code.  
⚠️ **Incorrect or inconsistent indentation will raise an `IndentationError`.**

```python
# Correct indentation
x = 5
if x > 0:
    print("Positive number")

# Incorrect indentation (will raise an error)
x = 5
if x > 0:
print("Positive number")  # ❌ IndentationError
```

🧠 Always ensure your indentation is consistent — use either **spaces** or **tabs**, not both.

# 🔗 Logical Operators in Python

Logical operators are used to combine conditional statements. Python supports three logical operators:

---

## ✅ `and` Operator
Returns `True` if **both** statements are true.

```python
x = 5
print(x > 2 and x < 10)   # True
print(x > 10 and x < 20)  # False
```

📌 **Output:**

```graphql
True
False
```

## ✅ `or` Operator
Returns `True` if **at least one** statement is true.

```python
x = 5
print(x > 2 or x > 10)   # True
print(x < 1 or x > 10)   # False
```

📌 **Output:**

```graphql
True
False
```

## ✅ `not` Operator

Reverses the result — returns `False` if the condition is `True`, and `True` if the condition is `False`.

```python
x = 5
print(not(x > 3))    # False
print(not(x > 10))   # True
```

📌 **Output:**

```graphql
False
True
```

💡 **Tip:** Logical operators are commonly used in conditions with `if`, `while`, or `assert`.

---

🧠 **Why Use Logical Operators?**

- To check multiple conditions at once  
- To simplify complex decision-making  
- To make your code more readable and expressive

## 📝 WAP to Assign Grades Based on Marks

This program assigns grades depending on the score provided by the user.

```python
# Taking input from the user
marks = int(input("Enter your marks: "))

# Grading system
if marks >= 90:
    print("Grade: A")
elif marks >= 80:
    print("Grade: B")
elif marks >= 70:
    print("Grade: C")
elif marks >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

📌 Output Example:

```yaml
Enter your marks: 85  
Grade: B
```

# 🌀 Day 02

## Looping Statements

To avoid repetitive work and save time, we use **loops**.

Python provides two primary types of loops:
- `while` Loop
- `for` Loop

---

### 🔁 Example of `while` loop (1 to 10):

```python
i = 1
while i < 11:
    print(i)
    i = i + 1
```

📌 Output:
```
1
2
3
4
5
6
7
8
9
10
```

### 🔁 Example of `while` loop (10 to 1):

```python
i = 10
while i > 0:
    print(i)
    i = i - 1
```

📌 Output:
```
10  
9  
8  
7  
6  
5  
4  
3  
2  
1
```

💡 **Tip:** Loops are extremely helpful in automating repetitive tasks and reducing lines of code!

### ✅ WAP to Add All Numbers from 1 to 10

```python
i = 1
sum = 0
while(i < 11):
    sum += i
    i += 1

print(f"Sum of numbers from 1 to 10 is: {sum}")
```

📌 **Output:**
```
Sum of numbers from 1 to 10 is: 55
```
 

### ✅ while-else in Python

The `else` block after a `while` loop runs **only when the loop ends normally** (i.e., not via a `break`).

```python
ans = 0
i = 1
while i < 11:
    ans += i
    i += 1
else:
    print("Ans is:", ans)
```

📌 **Output:**
```bash
Ans is: 55
```

💡 **Note:**  
The `else` block is useful for **post-processing** once the loop completes fully.

✅ It will only run if the loop **was not terminated by a `break`**.

---

### ❌ If a `break` occurs, the `else` block is skipped:

```python
i = 1
while i <= 10:
    if i == 5:
        break
    print(i)
    i += 1
else:
    print("Loop completed without break.")
```

📌 **Output:**
```bash
1
2
3
4
```

🚫 **The `else` block did not run** because the loop was exited with `break`.

✅ Use this structure when you want to **detect early termination** inside loops!

This is particularly useful in search operations, validations, or checking conditions where you want to know whether the loop ran to completion or exited midway.

🚫 You cannot add a string and a number directly in Python:

```python
print("hello" + ans)
```

🚫 This will throw a `TypeError` because Python doesn't allow concatenation of a string with an integer.

---

✅ **Solution**: Convert the number to a string using `str()`:

```python
ans = 55
print("hello " + str(ans))
```

```nginx
hello 55
```

✅ **Alternative**: Use a comma `,` which automatically adds a space and handles type conversion:

```python
print("hello", ans)
```
```nginx
hello 55
```

### ✅ Program to Print Even Numbers from 1 to 10 using `while` loop

```python
i = 1
while i < 11:
    if i % 2 == 0:
        print(i)
    i = i + 1
```

📌 **Output:**
```
2
4
6
8
10
```

💡 **Tip**: You can also start from `2` and increment by `2` to optimize it.

```python
# Calculate factorial of given number
# 5! = 5 * 4 * 3 * 2 * 1

n = int(input("Enter a number: "))
num = n
fact = 1
while(n > 1):
    fact *= n
    n -= 1

print(f"\nFactorial of {num} is: {fact}")
```

```yaml
Enter a number: 5
Factorial of 5 is: 120

Enter a number: 6
Factorial of 6 is: 720

Enter a number: 20
Factorial of 20 is: 2432902008176640000
```

### 🧮 Factorial of Numbers from 1 to n using while loop

```python
n = int(input("Enter a number: "))

i = 1

while(i < n+1):
    num = i
    fact = 1
    while(num >= 1):
        fact *= num
        num -= 1
    print(f"\nFactorial of {i} is: {fact}")
    i += 1
```

### 📌 Output Example:

```bash
Enter a number: 5

Factorial of 1 is: 1

Factorial of 2 is: 2

Factorial of 3 is: 6

Factorial of 4 is: 24

Factorial of 5 is: 120
```

## 🔁 `for` Loop in Python

The `for` loop in Python is commonly used with the `range()` function.

### 🧱 Syntax:
```python
range(start, stop, step)
```

### 🔍 Understanding `range(start, stop, step)` in Python

- **start** → Starting number (**inclusive**)
- **stop** → Ending number (**exclusive**)
- **step** → Increment/Decrement (default is `1`)

---

### ✅ Examples:

```python
# Prints numbers from 1 to 10
for i in range(1, 11, 1):
    print(i)
```

```python
# Prints numbers from 10 to 1 in reverse
for i in range(10, 0, -1):
    print(i)
```

### ✅ WAP to print all numbers from 1 to 10

```python
for i in range(1, 11):
    print(i)
```

📌 **Output:**
```bash
1
2
3
4
5
6
7
8
9
10
```

### 🔁 WAP to print numbers from 10 to 1 (Reverse Order)

```python
for i in range(10, 0, -1):
    print(i)
```

📌 **Output:**
```bash
10
9
8
7
6
5
4
3
2
1
```

### ➕ WAP to Add Numbers from 1 to 10

```python
sum = 0

for i in range(1, 11):
    sum += i
print(sum)
```

📌 **Output:**
```bash
55
```

💡 **Tip:** `sum += i` is shorthand for `sum = sum + i`, which adds each number to the total.

## ✅ Why Prefer `for` Loop Over `while` Loop?

`for` loops are generally preferred when:

1. **You Know the Number of Iterations**  
   - Example: Printing numbers from 1 to 100  
   - `for` loops are cleaner and more readable for such cases.

2. **Automatic Counter Handling**  
   - The `for` loop internally manages loop variables (like `i` in `range()`), reducing the chance of infinite loops due to forgetting `i += 1`.

3. **Compact Syntax**  
   - Everything (initialization, condition, increment) is handled in one line using `range()`.

4. **Better for Iterating Over Collections**  
   - Perfect for iterating over lists, tuples, dictionaries, etc.

---

### 🔁 Example: Print 1 to 5

Using `for` loop:
```python
for i in range(1, 6):
    print(i)
```

## 🔁 Using `while` Loop

```python
i = 1
while i < 6:
    print(i)
    i += 1
```

## 📌 Conclusion

✅ Use **for loops** when the **iteration count is known** or you're working with **sequences** (like lists, ranges, strings).

✅ Use **while loops** when you need to **loop based on a condition** rather than a fixed count  
(e.g., waiting for user input, looping until a certain state is reached).

### ✅ WAP to Print All Odd Numbers from 1 to 10

```python
for i in range(1, 11):
    if i % 2 != 0:
        print(i)
```

📌 **Output:**
```bash
1
3
5
7
9
```

💡 **Tip:** `%` is the **modulus operator** — it gives the **remainder**.  
Odd numbers have a remainder of `1` when divided by `2`.


### ✅ WAP to Print Factorial of Given Number Using Nested for Loops

```python
num = int(input("Enter a number: "))
n = num

for i in range(1, n+1):
    num = i
    fact = 1

    for j in range(1, num+1):
        fact *= j

    print(f"Factorial of {num} is: {fact}")
```

📌 **Sample Output:**
```bash
Enter a number: 5
Factorial of 1 is: 1
Factorial of 2 is: 2
Factorial of 3 is: 6
Factorial of 4 is: 24
Factorial of 5 is: 120
```

💡 **Tip:** Use nested loops to calculate factorials for a series of numbers from `1` to `n`.

### ✅ WAP to Check if a Number is a Prime Number

```python
flag = 1
num = int(input("Enter a number: "))
for i in range(2, num):
    if (num % i == 0):
        print(f"\n{num} is not a prime number")
        flag = 0
        break

if flag and num >= 2:
    print(f"\n{num} is a prime number")
```

📌 **Output:**
```bash
Enter a number: 5

5 is a prime number
```

💡 **Tip:**

- A **prime number** has only two factors — `1` and **itself**.
- The loop checks for any **divisors** between `2` and `num - 1`.
- If a divisor is found, the number is **not prime** and the loop exits using `break`.

## ✅ WAP to print all prime numbers from 1 to 100

```python
for i in range(1, 101):
    flag = 1
    for j in range(2, i):
        if (i % j == 0):
            flag = 0
            break

    if flag and i >= 2:
        print(f"\n{i} is a prime number")
```

📌 **Output:**
```bash
2 is a prime number

3 is a prime number

5 is a prime number

7 is a prime number

11 is a prime number

13 is a prime number

17 is a prime number

19 is a prime number

23 is a prime number

29 is a prime number

31 is a prime number

37 is a prime number

41 is a prime number

43 is a prime number

47 is a prime number

53 is a prime number

59 is a prime number

61 is a prime number

67 is a prime number

71 is a prime number

73 is a prime number

79 is a prime number

83 is a prime number

89 is a prime number

97 is a prime number
```

💡 **Tip:** This approach uses **nested loops** — the outer loop checks each number from 1 to 100, and the inner loop checks if it's divisible by any number other than 1 and itself.

# 🔁 Loop Control Statements in Python

Python provides three loop control statements that can change the flow of loops:

---

## ✅ 1. break Statement
Used to **exit the loop immediately**, even if the condition is still True.

```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```

📌 **Output:**

```bash
1
2
3
4
```

## ✅ 2. continue Statement
Used to **skip the current iteration** and continue with the next one.

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

📌 **Output:**
```python
1
2
4
5
```

## ✅ 3. `pass` Statement

The `pass` statement is used as a placeholder to indicate that a block of code is intentionally left blank — typically because you'll add logic there in the future.

```python
for i in range(1, 4):
    if i == 2:
        pass  # Intention of writing something in future
    print(i)
```

📌 **Output:**
```bash
1
2
3
```

## 💡 Use Case Summary

- `break` → Exit the loop early  
- `continue` → Skip the current iteration  
- `pass` → Placeholder for future code (no action)

✨ These help you control your loop’s flow effectively!

### 🧠 Why Use Lists in Python?

Imagine storing data in **100 variables** — that would be highly inconvenient and messy!  
✅ Python provides **lists** to store multiple items in a single variable.

---

### ❓ Why No Traditional Arrays in Python?

- Traditional arrays (like in C or Java) store **homogeneous data** (all elements of the same type).
- Python is a **dynamically-typed** language — data types can change at runtime.
- Hence, Python lists are more flexible — they can store **heterogeneous data** (mixed types).

---

### ✅ Advantages of Lists:
- **Single name access**: You can access all data using one list name.
- **Dynamic typing**: Store integers, strings, and even other lists — all in one list.
- **Dynamic size**: No need to define size beforehand.

```python
data = [10, "hello", 3.14, True]
print(data[1])  # Output: hello
```

# 🧺 Python Collections

Python offers several **built-in collection data types** to store groups of items.  
Each has different **features and use cases**.

---

## 1. 📋 List
- **Ordered**, **mutable**, allows **duplicates**
- Can store **heterogeneous** data

```python
my_list = [1, "apple", 3.14, True]
```

## 2. 🔐 Tuple

- **Ordered**
- **Immutable**
- Allows **duplicates**
- Slightly **faster than lists** due to immutability

```python
my_tuple = (1, "banana", 3.14)
print(my_tuple[1])  # Output: banana
```

💡 **Tuples** are great for data that shouldn't change — like **days of the week** or **coordinates**.

### 3. 🔁 Set
- **Unordered**, **mutable**, **no duplicates** allowed  
- Useful for **membership testing** and **eliminating duplicates**

```python
my_set = {1, 2, 3, 2}
print(my_set)  # Output: {1, 2, 3}
```

💡 **Tip:** Sets are ideal for storing unique values and performing operations like **union**, **intersection**, and **difference**.

---

### 4. 📖 Dictionary
- **Key-value pairs**
- **Unordered** (in older Python versions), **mutable**, **no duplicate keys**

```python
my_dict = {"name": "Alice", "age": 25}
print(my_dict["name"])  # Output: Alice
```

💡 **Tip:** Dictionaries are great when you want to associate values with **labels** or **identifiers**.

---

### 5. 🔤 Strings
- **Immutable**, **ordered sequences** of characters  
- Support **indexing**, **slicing**, and many **built-in functions**

```python
my_str = "Hello, World!"
print(my_str[0])       # Output: H
print(my_str.lower())  # Output: hello, world!
```

💡 **Tip:** Strings are widely used for **text processing**. Since they are **immutable**, every change creates a **new string**.

## 📋 Python Lists

### 🔹 What is a List?
A **List** is an **ordered** and **indexed** collection of items.

- Elements are separated by commas and enclosed in square brackets `[]`.
- Lists are **mutable**, meaning their values can be changed after creation.
- Can store **heterogeneous data types** (`int`, `str`, `float`, etc.)

```python
l = [10, 20, 30, 40, 50]
```

### 🔸 Accessing List Elements
You can access list elements by **indexing**, starting from `0`.

```python
print(l)        # Output: [10, 20, 30, 40, 50]
print(type(l))  # Output: <class 'list'>

print(l[0])     # Output: 10
print(l[1])     # Output: 20
print(l[3])     # Output: 40
print(len(l))   # Output: 5
```

⚠️ **Accessing an invalid index** (like `l[99]`) will throw:

```python
IndexError: list index out of range
```

### 🔁 Negative Indexing
Python supports **negative indexing** to access elements from the end.

```python
print(l[-1])         # Output: 50 (last element)
print(l[-len(l)])    # Output: 10 (first element)
```

📌 `-1` refers to the **last element**, `-2` to the **second last**, and so on.

---

### 💡 Why Use Lists?
- Store multiple values in a single variable  
- Useful when data needs to be **iterated**, **sorted**, **updated**, or **sliced**  
- Can be **nested**, **combined**, and **manipulated** easily  

---

### ✅ Summary Table

| Feature             | List Example        | Description                          |
|---------------------|---------------------|--------------------------------------|
| **Ordered**         | `l = [1, 2, 3]`     | Elements retain insertion order      |
| **Indexed**         | `l[0] → 1`          | Access by position                   |
| **Mutable**         | `l[0] = 10`         | Can change values                    |
| **Heterogeneous**   | `[1, "hi", 3.14]`   | Supports multiple data types         |
| **Negative Indexing** | `l[-1] → Last Item` | Access elements from the end         |

### 🔁 Looping Through Lists in Python

---

#### ✅ Traditional Way Using Indexing
You can loop through a list using `range()` and `len()`:

```python
l = [10, 20, 30, 40, 50]

for i in range(0, len(l)):
    print(l[i])
```

🧠 **What's happening?**

- `range(0, len(l))` generates indices from `0` to `len(l) - 1`  
- `l[i]` accesses the element at each index  

---

### ✅ Pythonic Way (Simpler & Cleaner)

Python allows direct iteration over the list without using indexes:

```python
for i in l:
    print(i)
```

🎉 **Why Python is Easy?**

- You don't need to track indices manually  
- The loop directly gives you each element — no need to write `l[i]`  
- Less code, more readability  

---

### 🆚 Comparison

| Feature        | `using range(len(l))`       | `using for i in l`         |
|----------------|------------------------------|-----------------------------|
| **Code Length** | Longer                       | Short and clean             |
| **Readability** | Medium                       | High                        |
| **Performance** | Slightly slower              | Slightly faster             |
| **Use Case**    | Needed when using index      | Best for simple iteration   |

---

💡 **Tip**  
Use `for i in l` when **index is not required**.  
Use `for i in range(len(l))` if you **need the index** (e.g., to modify elements or track position).

### 📦 Empty List in Python

An empty list can be created in two ways:

```python
a = []
```

or using the `list()` constructor:

```python
a = list()
print(a)  # Output: []
```

💡 **Tip:** Use an empty list when you plan to append elements later.

---

### 📋 List with Elements

```python
a = [10, 20, 30, 40, 50, 10, 10, 2, 6, 23]
print(a)
```

✅ **Characteristics of a List:**

- **Ordered:** Maintains the order of insertion  
- **Allows duplicates:** Values like `10` can appear multiple times  
- **Mutable:** You can change elements  
- **Indexed:** You can access elements using index  

---

### 🧪 List with Multiple Data Types

Python lists can store values of different types due to dynamic typing:

```python
x = [1, 1, 1, True, 1]
print(x)  # Output: [1, 1, 1, True, 1]
```

🧠 **Why does `True` appear as `1`?**

In Python, `True` is internally treated as `1` because **Boolean is a subtype of integer**.

So, the expression `True == 1` returns `True`.

---

### ✅ Summary

| Type           | Example                     | Notes                                      |
|----------------|-----------------------------|--------------------------------------------|
| Empty list     | `[]` or `list()`            | Useful as a placeholder                    |
| Homogeneous    | `[10, 20, 30]`              | All elements of the same type              |
| Heterogeneous  | `[1, 'hello', 3.14, True]`  | Python allows mixed data types in lists    |

### ✂️ List Slicing in Python

Slicing allows you to access a subset of elements from a list using the syntax:

```python
list[start:stop]
```

🧠 **Note:** The stop index is excluded from the result.

---

### 📌 Examples:

```python
a = [10, 20, 30, 40, 50, 60]

a[0:3]  # Output: [10, 20, 30]
# Starts from index 0
# Includes 0, 1, 2 (not 3)

a[2:5]  # Output: [30, 40, 50]
# Starts from index 2
# Includes 2, 3, 4 (not 5)
```

### 📦 Store Sliced List in a New Variable

```python
b = a[0:3]
print(b)  # Output: [10, 20, 30]
```

### ✅ Shortcut Variants

| Syntax | Meaning                     |
|--------|-----------------------------|
| `a[:3]` | From start to index 2       |
| `a[2:]` | From index 2 to end         |
| `a[:]`  | Entire list (makes a copy)  |

---

💡 **Tip:** Slicing is a powerful tool for extracting and copying parts of lists efficiently!

## 🔢 Working with Lists in Python

### ✅ 1. Print Prime Numbers from a List

```python
a = [10, 4, 3, 7, 8, 32, 33, 7, 6, 5, 5, 5, 7, 7]

for i in a:
    flag = 1
    for j in range(2, i):
        if (i % j == 0):
            flag = 0
            break

    if flag and i >= 2:
        print(f"{i} is a prime number")
```

📌 **Output:**
```css
3 is a prime number  
7 is a prime number  
7 is a prime number  
5 is a prime number  
5 is a prime number  
5 is a prime number  
7 is a prime number  
7 is a prime number
```

### 🔶 2. Print Odd Numbers from a List

```python
for i in a:
    if (i % 2 != 0):
        print(i)
```

📌 **Output:**
```
3  
7  
33  
7  
5  
5  
5  
7  
7
```

### ➕ 3. List Concatenation and Element-wise Addition

```python
y = [4, 5, 6]
z = [7, 8, 9]

# Concatenation
result = y + z
print(result)  # Output: [4, 5, 6, 7, 8, 9]
```

```python
# Element-wise addition
for i in range(3):
    print(y[i] + z[i])
```

📌 **Output:**
```
11  
13  
15
```

### 💡 Tips for Remembering

- Use **nested loops** for logic like **prime number checks**.
- `%` (modulus) helps identify **odd numbers** or **check divisibility**.
- `+` with lists is used for **concatenation** (joining two lists).
- To perform **element-wise addition**, loop through positions using `range(len(list))`.

---

# 📅 Day 03

## 🔍 Key Concepts

### ✅ Everything is an Object in Python
- All data structures in Python — such as `list`, `tuple`, `set`, `dict`, and even functions — are **objects**.
- Each object is an instance of a class.

---

### ⚠️ Importance of Reading Error Messages
- Error messages are **helpful clues**, not just blockers.
- They often tell you:
  - What type of error it is (e.g., `TypeError`, `ValueError`)
  - Where it occurred (line number)
  - Why it happened

---

## 📚 List Methods

### 🚫 Not Functions — They’re Methods
- In Python, **methods** are functions **defined inside a class**.
- Since `list` is a class, its operations (like `.append()`, `.remove()`, etc.) are called **methods**.

### 💡 Why It’s Called a Method:
- A **method** has access to the object it belongs to via the special keyword `self`.
- `self` in Python is similar to `this` in other object-oriented languages (like Java, C++).

```python
class MyList:
    def show(self):  # This is a method
        print("Hello from list")
```

## 📌 Static Methods

- If a method is declared with `@staticmethod`, it **doesn’t take `self`**.
- It's just like a **regular function** but is defined **within a class** namespace.
- It **cannot access instance variables or methods** unless explicitly passed.

```python
class Demo:
    @staticmethod
    def greet():
        print("Hello from static method!")

Demo.greet()
```

## 🆚 Function vs Method

| 🔍 Feature        | ✅ Function                             | ✅ Method                                 |
|------------------|-----------------------------------------|-------------------------------------------|
| **Defined in**    | Global scope or inside a class         | Always inside a class                     |
| **Called on**     | Standalone                             | Called on an object                       |
| **Accesses `self`**| No                                     | Yes (unless it's a static method)         |
| **Example**       | `len(list)`                            | `list.append(10)`                         |

---

💡 **Summary:**  
- Use **functions** when you want reusable code that's independent.  
- Use **methods** when you want behavior tied to an object.

## 📝 Copy Command in Python Lists

```python
b = [2, 3, 4, 5, 6, 7]
a = b.copy()   # Creates a shallow copy of b
a              # Output: [2, 3, 4, 5, 6, 7]

c = b          # c and b now refer to the same list

b[0] = 4       # Modify the first element of b

a              # Output: [2, 3, 4, 5, 6, 7] → Unchanged
b              # Output: [4, 3, 4, 5, 6, 7]
c              # Output: [4, 3, 4, 5, 6, 7]
```

## ✅ Key Points about Copying Lists in Python

- `a = b.copy()` creates a **separate list**. Changes in `b` will **not affect** `a`.

- `c = b` creates a **reference** to the same list. Changes in `b` **will reflect** in `c`.

- Use `.copy()` when you need a **new list** with the same values, but without any linkage to the original list.

💡 **Shallow Copy**: The outer list is copied, but if the elements are mutable objects (like other lists), only the **references** are copied — not the actual nested data.


## 🧹 `clear()` Command in Python

```python
b.clear()
print(b)  # Output: []
```

## 🧹 `clear()` Method in Python

This method **removes all items** from the list `b`, making it an **empty list**.

⚠️ Use this command **cautiously**, as it **permanently deletes** the contents of the list.

💡 **Tip:** It's useful when you want to **reset** a list without creating a new one.


## ➕ `append()` Method in Python

Adds an element to the **end** of the list.

```python
a = [2, 3, 4, 5, 6, 7]
a.append(88)
print(a)
# Output: [2, 3, 4, 5, 6, 7, 88]
```
✅ It does **not** ask for a location — it always appends to the **end**.

⚡ It's **faster** than `insert()` since it doesn't involve shifting other elements.


### 📥 `insert()` Command

```python
a = [2, 3, 4, 5, 6, 7, 88]
a.insert(0, 55)
print(a)  # Output: [55, 2, 3, 4, 5, 6, 7, 88]
```

✅ Unlike `append()`, `insert()` requires both a **location (index)** and the **data** to insert.

🔄 Inserting at the **beginning** of a list means **all existing elements are shifted**, which is slower.

💡 **Note:**  
If the list has **3 lakh elements** and you insert something at **index 0**, Python has to **shift all 3 lakh items** one step forward — making it **less efficient than `append()`**.


### 🧯 `pop()` Command

- Opposite of `append()`
- Removes the **last element** from the list (by default)

```python
a = [55, 2, 3, 4, 5, 6, 7, 88]
a.pop()
# Output: 88
```

📝 After popping:

```python
a  # [55, 2, 3, 4, 5, 6, 7]
```

💡 `pop()` can also take an index as an argument to remove a specific item:

### 🧹 `remove()` Method

- Removes a **specific value** from the list.
- If the value appears multiple times, **only the first occurrence** is removed.

```python
a = [55, 2, 3, 4, 5, 6, 7, 88]
a.remove(55)
print(a)
# Output: [2, 3, 4, 5, 6, 7, 88]
```

⚠️ **Note:**

- If the value is **not present**, Python will raise a `ValueError`.
- The `remove()` method **does not return** the removed element.
- It **modifies the list in place**.


### 🔍 `index()` Command

Used to find the **index** of a particular element in a list.

```python
a = [2, 3, 4, 5, 6, 7, 88]
print(a.index(4))  # Output: 2
```
✅ If there are **multiple occurrences** of the element, it will return the **index of the first occurrence**.

⚠️ Raises a `ValueError` if the element is **not found** in the list.


### 🔢 `count()` Method

Returns the **total number of occurrences** of a particular element in the list.

```python
a = [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]
print(a.count(3))  # Output: 6
```

✅ If the element is present, it returns the count.

🔁 If the element appears multiple times, it returns the total number of appearances.

❌ If the element is not present, it returns 0.


### 📌 `extend()` Method

Used to concatenate one list into another.

```python
b = a.copy()
print(b)
# Output: [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]

a.extend(b)
print(a)
# Output: [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3, 2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]
```

✅ `extend()` adds each element of the second list to the end of the first list.

💡 This is more efficient than using `a + b` because `+` creates a new list, while `extend()` modifies the list in place.


### 🔢 `sort()` Method

✅ This function sorts the list **in-place** in ascending order by default.

⚠️ It only works when **all elements are of the same data type** — mixing integers and strings will raise a `TypeError`.

#### Example:
```python
a = [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3, 2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]
a.sort()
print(a)
```

Output:
```csharp
[2, 2, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 4, 4, 5, 5, 5, 5, 6, 6, 7, 7, 7, 7, 88, 88]
```

💡 Use `a.sort(reverse=True)` to sort in descending order.

### 🔽 Descending Order Sorting

By default, `sort()` arranges elements in **ascending** order.

To sort in **descending** order, use the `reverse=True` parameter.

#### Example:
```python
a.sort(reverse=True)
print(a)
```

**Output:**
```csharp
[88, 88, 7, 7, 7, 7, 6, 6, 5, 5, 5, 5, 4, 4, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 2, 2]
```

✅ **Key Point**:  
`a.sort()` → Ascending order (default)  
`a.sort(reverse=True)` → Descending order


### 🔄 reverse()

This function reverses the elements of the list **in-place**.

```python
b = [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]
b.reverse()
print(b)
# Output: [3, 3, 3, 3, 7, 5, 3, 88, 7, 6, 5, 4, 3, 2]
```

### 💡 Alternate Method (Using Slicing)

```python
b[::-1]
# Output: [2, 3, 4, 5, 6, 7, 88, 3, 5, 7, 3, 3, 3, 3]
```

✅ `b.reverse()` modifies the **original list in place**.

✅ `b[::-1]` creates and returns a **new reversed list** without altering the original list.


# 📝 Assignment 1

### ✅ Task:
Create a list of all elements from 1 to 10 using a loop.

### ✅ Code:
```python
l = []
for i in range(1, 11):
    l.append(i)
print(l)
```

✅ **Output:**
```python
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

💡 **Tip:**

- Use `.append()` to add elements to the list.
- `range(1, 11)` generates numbers from 1 to 10 (since 11 is excluded).


# 🚀 Assignment 2: Create a list of odd numbers from 1 to 100

```python
odd_list = []

for i in range(1, 101, 2):
    odd_list.append(i)

print(odd_list)
```

✅ **Output**:

```python
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]
```

💡 **Tip**:

- `range(1, 101, 2)` starts from `1` and goes up to `100` (inclusive), incrementing by `2` — so it picks only **odd numbers**.
- Use `.append()` to add each odd number to the list.


# ✅ Create a list of prime numbers from 1 to 100

```python
prime_list = []

for i in range(2, 101):
    flag = 1
    for j in range(2, i):
        if (i % j == 0):
            flag = 0
            break

    if flag and i >= 2:
        prime_list.append(i)

print(prime_list)
```

📌 **Output:**
```csharp
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]
```

💡 **Tip**:
- A number is **prime** if it has only two divisors: `1` and itself.
- The inner loop checks divisibility from `2` to `(i - 1)`.
- `flag = 1` means it’s considered prime, and the number is added to the list using `.append()`.


# ✅ Task 4: Create a List with Specific Conditions

**Goal:**  
- From **1 to 50**, include only **odd** numbers  
- From **51 to 100**, include only **even** numbers  

---

### 🔹 Code:
```python
even_odd = []

for i in range(1, 101):
    if(i <= 50):
        if(i % 2 != 0):
            even_odd.append(i)
    if(i > 50):
        if(i % 2 == 0):
            even_odd.append(i)

print(even_odd)
```

✅ **Output:**
```python
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 
 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100]
```

🔄 **Alternate Method 1:**

```python
eo = []

for i in range(1, 101):
    if(i <= 50) and (i % 2 != 0):
        eo.append(i)
    if(i > 50) and (i % 2 == 0):
        eo.append(i)

print(eo)
```

🔄 **Alternate Method 2:**
```python
e_o = []

for i in range(1, 101):
    if(i <= 50) and (i % 2 != 0):
        e_o.append(i)
    if(i > 50) and (not(i % 2)):
        e_o.append(i)

print(e_o)
```

💡 **Tip:**

- `(i % 2 != 0)` → Odd number  
- `(i % 2 == 0)` or `not(i % 2)` → Even number  
- All three methods give the same correct result — choose the one you're most comfortable with!

## 🔢 Count of Duplicates in a String (Word Frequency)

```python
text = "Hello bhai kaise ho how are you how are your mom how are your parents where are you from what is your name what is you dob"

words = text.split()
alphastring = []
unique_words = []

for word in words:
    if word not in unique_words:
        unique_words.append(word)
        alphastring.append(f"{word}: {words.count(word)}")

print(alphastring)
```

✅ **Output:**
```python
['Hello: 1', 'bhai: 1', 'kaise: 1', 'ho: 1', 'how: 3', 'are: 3', 'you: 3', 'your: 3', 'mom: 1', 'parents: 1', 'where: 1', 'from: 1', 'what: 2', 'is: 3', 'name: 1', 'dob: 1']
```

## 💡 Tip

- `split()` breaks the string into **individual words**.

- `words.count(word)` counts how many times **each word** appears.

- The `unique_words` list is used to **avoid counting the same word more than once**.



## 📌 Tuple in Python

- A **tuple** is an **indexed**, **ordered** collection of data.
- Elements are separated by commas and enclosed in **round brackets `()`**.

```python
example = (1, 2, 3)
```

## 🔒 Tuple Properties

- ✅ **Indexed**
- ✅ **Ordered**
- ❌ **Immutable** (cannot be changed after creation)

---

## ❌ What You Can't Do with Tuples

- No `sort()`
- No `append()`
- No `pop()`
- No `reverse()`
- No `delete` (individual elements)

---

## ⚠️ Reversing a Tuple (Not Recommended)

If you use slicing to reverse a tuple, it creates a **new tuple**, which is considered **bad practice** for immutable data.

```python
c = (2, 3, 4, 3, 2, 9)
c = c[::-1]
print(c)  # Output: (9, 2, 3, 4, 3, 2)
```

## 🔐 When to Use Tuples?

- When you want your data to be **safe from modification**
- Useful in handling **critical** or **constant** data

---

## 🔁 Converting Tuple to List for Modification

```python
a = (1, 2, 3)
x = list(a)  # Now you can modify x as a list
```

# 🧵 Python Strings

Strings are **one of the most widely used data types in Python**. They are essentially sequences of characters and are used to store text.

---

### 🔹 Creating Strings

Strings can be created using:

```python
s1 = 'Hello'
s2 = "World"
```

### ✅ Single vs Double Quotes

Single quotes (`' '`) and double quotes (`" "`) are treated the **same** in Python.  
Just make sure to **start and end with the same type** of quote.

---

### 🔹 Quotes Inside Quotes

You can use quotes inside strings by alternating quote types:

```python
quote = "It's a sunny day"
dialogue = '"Hello", she said.'
```

Or by escaping the quote:

```python
escaped = 'It\'s a sunny day'
```

### 🔹 Triple Quotes for Multiline Strings

You can use triple quotes (`''' '''` or `""" """`) to create multiline strings:

```python
multiline = """This is
a multiline
string."""
```

## 🔹 String Indexing and Slicing

Strings in Python support indexing and slicing, just like lists:

```python
s = "Hello World"
print(s[1:3])   # Output: 'el'
```

📌 **Indexing starts from 0**, so:

- `s[0] = 'H'`
- `s[1:3] = 'el'` → includes index 1 and 2, but excludes 3

---

### 🔹 Looping Through a String

You can loop through a string using a `for` loop:

```python
s = "Hello World"
for i in s:
    print(i)
```

🖨️ Output:

```nginx
H  
e  
l  
l  
o  

W  
o  
r  
l  
d  
```

💡 Tips for Revision
🔒 Strings are immutable — you cannot change them after creation.

📏 Use len(s) to get the length of the string.

🔧 Common String Methods:
.upper() – Convert to uppercase

.lower() – Convert to lowercase

.replace() – Replace a substring

.find() – Find a substring

.split() – Split string into a list

.strip() – Remove whitespace from both ends

📌 Strings behave like lists for indexing and slicing,
but not for item assignment.


## 🧠 Understanding NULL in Python

### ❓ What is NULL?

- In Python, `None` is used to represent **NULL** (i.e., absence of value).
- It indicates that a variable has been **declared but not assigned any meaningful value** yet.
- `None` is an object of its own datatype — `NoneType`.

---

### 🧵 Example

```python
x = None
print(x)             # Output: None
print(type(x))       # Output: <class 'NoneType'>
```

## 🔎 Key Points

- `None` has **no ASCII value**, which means:
  - It **cannot be compared** with characters or numbers using relational operators.
  - Arithmetic operations like addition, subtraction, or comparison with integers/characters are **not valid**.

```python
x = None
print(x > 5)  # ❌ TypeError: '>' not supported between instances of 'NoneType' and 'int'
```

## 🧠 Understanding `None` in Python

### 📌 Definition
- `None` is used to indicate **absence of a value**.
- It is the **Python equivalent of `NULL`** in other programming languages.
- Data type: `NoneType`

---

### 📘 Common Usage

#### ✅ As a Default Argument in Functions

```python
def greet(name=None):
    if name is None:
        print("Hello, Guest!")
    else:
        print(f"Hello, {name}!")
```

### 🔍 Useful Checks

You can test if a variable is `None` using:

```python
x = None
print(x is None)   # ✅ True
print(x == None)   # ✅ True (though `is` is preferred for identity checks)
```

### 📌 Quick Notes

✅ `None` is the Python equivalent of `NULL`  
✅ Used to indicate **absence of a value**  
✅ Belongs to the **`NoneType`** data type  
🚫 Cannot perform **arithmetic** or **relational comparisons** with `None`

---

### 💡 Real-World Use Cases

- Used as **default values** in function parameters  
- Acts as a **placeholder** for optional or missing return values  
- Represents **missing or undefined data**, e.g.:
  - From **APIs**
  - **User inputs**
  - **Database query results**



### 🔁 Reversing a String using `for` Loop

You can reverse a string by iterating from the last index to the first using `range()`.

```python
s = "Hello World"
x = ""
for i in range(len(s) - 1, -1, -1):
    x = x + s[i]

print(x)  # Output: 'dlroW olleH'
```

### 🧠 Key Concepts

- `len(s)` → Returns the number of characters **including spaces**
- `range(len(s) - 1, -1, -1)` → Iterates from the last index to the first
- `x + s[i]` → Appends characters in reverse order

---

### 🔎 Check Data Type

```python
type(s)
# Output: <class 'str'>
```

This confirms that `s` is a string.


### 🔤 String Methods in Python

```python
s = "hello world"
```

### 🔤 String Case Methods in Python

#### 🔠 `s.capitalize()`
```python
s.capitalize()
# Output: 'Hello world'
```

Capitalizes only the first character of the string.  
All other characters become lowercase.

---

### 🔡 `s.upper()`

```python
s.upper()
# Output: 'HELLO WORLD'
```

Converts the entire string to uppercase.

---

### 🔽 `s.lower()`

```python
s.lower()
# Output: 'hello world'
```

Converts the entire string to lowercase.



### 🔁 `s.casefold()`

```python
s.casefold()
# Output: 'hello world'
```

More aggressive than `.lower()`, used for **case-insensitive matching**, especially in **internationalized text**.

---

🔢 `s.count()`
```python
s.count("h")       # Output: 0  
s.count("world")   # Output: 0
```



s.startswith("h")
False
s
'Hello World'
s.endswith("d")
True
s.replace("H", "*")
'*ello World'
s.replace("l", "L")
'HeLLo WorLd'

Replaces all occurences

s.replace("o", "O", 1)
'HellO World'

Replaces only one occurence.

a = "123"
a.isnumeric()
True
a.isdigit()
True
a = "1.5"
a.isnumeric()
False
a.isdigit()
False
a.isalpha()
False
x = "abc"
x.isalpha()
True
x = "Hello World"
x.isalpha()
False
x = "123abc"
x.isalnum()
True
x.isspace()
True

a="Hello 12 world hi 1 how are 8 you"
b=''
c=''
for i in a:
    if i.isnumeric():
        # b.append(i)
        b += i
    else :
        # c.append(i)
        c += i
print("b:", b)
print("c:", c)
        
a="Hello"
print(a.isnumeric())

sum

a="Hello 12 world hi 1 how are 8 you"
b=''
sum = 0
for i in a:
    if i.isnumeric():
        sum += int(i)
print(sum)

a = "Hello how are you"
a.split(" ")
['Hello', 'how', 'are', 'you']
l = a.split(" ")
len(l)
4
l
['Hello', 'how', 'are', 'you']
" ".join(l)
'Hello how are you'
"*".join(l)
'Hello*how*are*you'

Strings are Immutable.

Strings are mostly used in Big Data where unstructured Data is present.

Question: Separate the words from the string.

Structured Data means the data with rows and columns.
Unstructured Data means the data without any structured. e.g., "hellohowareyou" (text)
Semi-structured data. e.g., "hello#are*you,how@an(I)you"

str = "HELLO BHAI KAISE HO"
sAns = ""
for i in str.split(" "):
    sAns += (i[::-1]) + " "
print(sAns)

#############################

str="Hello bhai kaise ho how are you how is your mom how are your parents where are you from what is your name what is you dob"

words = str.split(" ")
alphastring = []

for i in words:
    # print(f"{i}: {words.count(i)}")
    alphastring.append((f"{i}: {words.count(i)}"))
    
print(alphastring)


i = 0
while i < len(alphastring):
    if alphastring.count(alphastring[i]) > 1:
        alphastring.remove(alphastring[i])
    else:
        i += 1

print(alphastring)


a = "hello*there#how,are(you)where#is@my#car"
s = "hellotherehowareyouwhereismycar"

b = a.split("*")
b = " ".join(b)
b = b.split("#")
b = " ".join(b)
b = b.split(",")
b = " ".join(b)
b = b.split("(")
b = " ".join(b)
b = b.split(")")
b = " ".join(b)
b = b.split("@")
b = " ".join(b)

b =b.split(" ")
print(b)

symbols = ["*", "#", ",", "(", ")", "@"]
b = a

for i in symbols:
    if i in a:
        b = b.split(i)
        b = " ".join(b)
b = b.split(" ")
print(b)

symbols = ["*", "#", ",", "(", ")", "@"]

a = "hello*there#how,are(you)where#is@my#car"

b = a

for i in symbols:
    if i in a:
        b = b.split(i)
        b = " ".join(b)
b = b.split(" ")

print(b.sort())

Day 04

How is memory managed in Java?
How is memory managed in Python?

Employee e = new Employee()
del a
Both have a logic of Reference

Array
Advantage: fast search
Disadvantage: random inserts and delete

LinkedList
Advantage: random insert and delete
Disadvantage: random search (compromise of usage)

Optimal utilisation of free memory in Linked List

So, if we want both the advantages in one entity, then what to do?
Use Hash Table.
which calculates index number dynamically.

We use mod, e.g., 50%5 to store the data.

Python Dictionary is highly modified Hash Table.
Keys are Unique, Values can be duplicated.

Dictionary:
a = {}
Dictionary is a collection of ordered (unindexed) key-value pairs.

a = {}
type(a)
<class 'dict'>
a = {1: "re", 2: "dskjfla", 3: "89r739", 4: "jjj", 7: "aioekod"}
a
{1: 're', 2: 'dskjfla', 3: '89r739', 4: 'jjj', 7: 'aioekod'}
a[7]
'aioekod'
a[8] = "eight"
b = a.copy()
b
{1: 're', 2: 'dskjfla', 3: '89r739', 4: 'jjj', 7: 'aioekod', 8: 'eight'}
b.clear()
b
{}
a.get(7)
'aioekod'
a.values()
dict_values(['re', 'dskjfla', '89r739', 'jjj', 'aioekod', 'eight'])
a.items()
dict_items([(1, 're'), (2, 'dskjfla'), (3, '89r739'), (4, 'jjj'), (7, 'aioekod'), (8, 'eight')])
a.keys()
dict_keys([1, 2, 3, 4, 7, 8])
d = {}
l = [2, 3, 2, 4, 4, 3, 6, 4, 9]
d.fromkeys(l)
{2: None, 3: None, 4: None, 6: None, 9: None}
x = d.fromkeys(l)


x
{2: None, 3: None, 4: None, 6: None, 9: None}
d
{}
d[7] = 'abc'
d[10] = 'abc'
x[10] = 'abc'
x
{2: None, 3: None, 4: None, 6: None, 9: None, 10: 'abc'}
d
{7: 'abc', 10: 'abc'}
a
{1: 're', 2: 'dskjfla', 3: '89r739', 4: 'jjj', 7: 'aioekod', 8: 'eight'}
for i in a:
    print(i)

    
1
2
3
4
7
8
for i in a.values():
    print(i)

    
re
dskjfla
89r739
jjj
aioekod
eight

Keys must be unique
Values can be duplicate

Where do we use dictionary?
Fast random insert, fast random search
Used for complex data

Keys are immutable, values are mutable.
Technically, Dictionaries are Immutable.

If key is not matched,
a[99]
Traceback (most recent call last):
  File "<pyshell#35>", line 1, in <module>
    a[99]
KeyError: 99
a.get(99)
It gives no error.

setdefault():
x
{2: None, 3: None, 4: None, 6: None, 9: None, 10: 'abc'}
x.setdefault(75, "kkk")
'kkk'
x
{2: None, 3: None, 4: None, 6: None, 9: None, 10: 'abc', 75: 'kkk'}
x.setdefault(64)
x
{2: None, 3: None, 4: None, 6: None, 9: None, 10: 'abc', 75: 'kkk', 64: None}
It returns the value or if the given key is not present in dictionary.
If key is present then it updates this value to associated key.

Set:
Set is unordered, unindexed, collection of unique values separated by comma enclosed in curly braces.
tobeList = [10, 10, 10, 20, 20, 30, 30]
m = set(tobeList)
m
{10, 20, 30}

Set is internally stored in the form of dictionary.

m.pop()
10
m
{20, 30}
m.remove(30)
m
{20}
m.add(24)
m
{24, 20}

Keys are internally used in sets.

Difference between Set and Dictionary:

Sets are unordered and Dictionaries are unordered.
Values can be duplicate in Dictionaries.

---

Assignment:

1. Check if given string is pangram:
"The quick brown fox jumps over the lazy frog"

string = "The quick brown fox jumps over the$ lazy dog"
print(string)

flag = 1
for i in string:
   if not((i >= 'a' and i <= 'z') or (i >= 'A' and i <= 'Z') or i == ' '):
        flag = 0
        break

if flag:
    print("Given string is pangram")
else:
    print("Given string is not a pangram.")

Alternate Method:

string = "The quick brown fox jumps over the $lazy dog"
print(string)

flag = 0
for i in string:
    if ((i >= 'a' and i <= 'z') or (i >= 'A' and i <= 'Z') or i == ' '):
        flag = 1
    else:
        flag = 0
        break

if flag:
    print("Given string is pangram")
else:
    print("Given string is not a pangram.")

---

2. In cryptography, a Caesar Cipher is a very simple encryption techniques in which each letter in the plain text is replaced by a letter some fixed number of positions down the alphabet. For example, with a shift of 3, A would be replaced by D, B would become E, and so on. The method is named after Julius Caesar, who used it to communicate with his generals. ROT-13 ("rotate by 13 places") is a widely used example of a Caesar cipher where the shift is 13. In Python, the key for ROT-13 may be represented by means of the following dictionary:


Your task in this exercise is to implement an encoder/decoder of ROT-13. Once you're done, you will be able to read the following secret message:
Pnrfne pvcure? V zhpu cersre Pnrfne fnynq!

Note that since English has 26 characters, your ROT-13 program will be able to both encode and decode texts written in English.

key = {'a': 'n', 'b': 'o', 'c': 'p', 'd': 'q', 'e': 'r', 'f': 's', 'g': 't', 'h': 'u', 'i': 'v', 'j': 'w', 'k': 'x', 'l': 'y', 'm': 'z', 'n': 'a', 'o': 'b', 'p': 'c', 'q': 'd', 'r': 'e', 's': 'f', 't': 'g', 'u': 'h', 'v': 'i', 'w': 'j', 'x': 'k', 'y': 'l', 'z': 'm',
       'A': 'N', 'B': 'O', 'C': 'P', 'D': 'Q', 'E': 'R', 'F': 'S', 'G': 'T', 'H': 'U', 'I': 'V', 'J': 'W', 'K': 'X', 'L': 'Y', 'M': 'Z', 'N': 'A', 'O': 'B', 'P': 'C', 'Q': 'D', 'R': 'E', 'S': 'F', 'T': 'G', 'U': 'H', 'V': 'I', 'W': 'J', 'X': 'K', 'Y': 'L', 'Z': 'M'}

Solution:

key = {'a': 'n', 'b': 'o', 'c': 'p', 'd': 'q', 'e': 'r', 'f': 's', 'g': 't', 'h': 'u', 'i': 'v', 'j': 'w', 'k': 'x', 'l': 'y', 'm': 'z', 'n': 'a', 'o': 'b', 'p': 'c', 'q': 'd', 'r': 'e', 's': 'f', 't': 'g', 'u': 'h', 'v': 'i', 'w': 'j', 'x': 'k', 'y': 'l', 'z': 'm',
       'A': 'N', 'B': 'O', 'C': 'P', 'D': 'Q', 'E': 'R', 'F': 'S', 'G': 'T', 'H': 'U', 'I': 'V', 'J': 'W', 'K': 'X', 'L': 'Y', 'M': 'Z', 'N': 'A', 'O': 'B', 'P': 'C', 'Q': 'D', 'R': 'E', 'S': 'F', 'T': 'G', 'U': 'H', 'V': 'I', 'W': 'J', 'X': 'K', 'Y': 'L', 'Z': 'M'}

string = "Pnrfne pvcure? V zhpu cersre Pnrfne fnynq!"

decode = ""
for i in string:
    if i not in key:
        decode += i
    else:
        decode += key[i]
print(decode)

---

3. Invert dictionary of list

d = {"colours": ["orange", "black", "blue"],
     "fruits": ["apple", "orange", "banana"],
     "vegetables": ["onion", "potato"]}

4. p = ['hi', 'hello', 'oye', 'h', 'world']
   Sort these words by length into dictionary.

5. Merge two lists without duplicates (Do not use sets)

   a = [1, 2, 3, 4]
   b = [4, 5, 6, 7]

   ans = [1, 2, 3, 4, 5, 6, 7]

6. In given string double the occurence of consonants and place "o" in between.
   e.g., "This"
   "ToThohisos"
