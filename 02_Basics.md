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

Day 02

Looping Statements

To avoid repetitive work, to avoid time spending again and again, we can use Loops.
 There are two types of loops in Python:
 - while Loop
 - for Loop

Example of while loop:

i = 1
 while i<11 :
 print(i)
 i=i+1

 
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

—


 i = 10

while i > 0:
 print(i)
 i = i - 1

 
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

WAP to add all the numbers from 1 to 10
 

i = 1
 sum = 0
 while(i < 11):
 sum += i
 i += 1

 
 print(f"Sum of numbers from 1 to 10 is: {sum}")
 Sum of numbers from 1 to 10 is: 55
 

while-else in while loop:
 

ans = 0
 i = 1
 while i < 11:
 ans += i
 i += 1
 else:
 print("Ans is: ", ans)

 
 Ans is: 55

You cannot add a string and a number.

print("hello + ans)
It will throw error.

One way is to convert the data type of the ans to string.

```python
print("hello " + str(ans))
```

```
hello 55
```
```python
print("hello", ans)
hello 55

i = 1
while i<11:
    if i%2 ==0:
        print(i)
    i=i+1

    
2
4
6
8
10

```python

# Calculate factorial of given number
#5 = 5*4*3*2*1

n = int(input("Enter a number: "))
num = n
fact = 1
while(n > 1):
    fact *= n
    n -= 1

    
print(f"\nFactorial of {num} is: {fact}")
```

```

Enter a number: 5

Factorial of 5 is: 120

Enter a number: 6

Factorial of 6 is: 720

Enter a number: 20

Factorial of 20 is: 2432902008176640000
```

Using for loop:

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
    i+=1
```

Output:
```bash
Enter a number: 5

Factorial of 1 is: 1

Factorial of 2 is: 2

Factorial of 3 is: 6

Factorial of 4 is: 24

Factorial of 5 is: 120
```

WAP to print all numbers from 1 to 10.
```python
for i in range(1, 11):
    print(i)
```

WAP to print above numbers in reverse order.
```python
for i in range(10, 0, -1):
    print(i)
```

WAP to add numbers from 1 to 10
```python
sum = 0

for i in range(1, 11):
    sum += i
print(sum)
```

WAP to print all odd numbers from 1 to 10
```python
for i in range(1, 11):
    if (i % 2 != 0):
        print(i)
```
Alternate Method:
```
for i in range(1, 11, 2):
    print(i)
```

WAP to print factorial of given number
```python
num = int(input("Enter a number: "))
n = num

for i in range(1, n+1):
    num = i
    fact = 1

    for j in range(1, num+1):
        fact *= j

    print(fact)
```
