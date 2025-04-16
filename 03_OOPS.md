## 🐍 Python: Object-Oriented & Functional Programming Notes

---

### 1. 🔶 Object-Oriented Programming (OOP) Basics

- **Object**: A real-world entity (e.g., `car`, `user`, `order`).
- **Class Loader**: JVM component responsible for dynamically loading classes into memory (Java-specific).
- **Memory Considerations**:
  - Avoid unnecessary memory usage.
  - `static` members are shared across all instances—can save memory but act like globals and may lead to tight coupling.
- **Key Point**: In OOP, **objects** are the main actors that hold state and behavior.

---

### 2. 🔄 Transition to Functional Programming (FP)

- **Core Idea**: Treat **functions** as first-class citizens (i.e., functions are objects).
- **Memory Impact**:
  - Each function exists once in memory, similar to a single global object.
- **Characteristics of FP**:
  1. **Higher-order functions**: Can accept functions as parameters.
  2. **Function returns**: Can return another function (not multiple values; use tuples or other structures if needed).
  3. **Immutability**: Data (e.g., lists) passed by reference; do not modify original data in-place when possible.

**✨ Benefits of FP**:
- Faster execution in certain scenarios (less boilerplate).
- Increased modularity: easy to pass and compose behaviors.
- More concise code: focus on _what_ rather than _how_.

---

### 3. 🔧 FP Features & Examples in Python

#### 3.1 ⚙️ Higher-Order Functions

```python
# Function that takes another function as argument
def apply_twice(func, value):
    return func(func(value))

# Example usage
result = apply_twice(lambda x: x + 3, 7)
print(result)  # Output: 13
```

#### 3.2 🔄 Functions Returning Functions

```python
# Function returning a function (closure)
def make_multiplier(n):
    def multiplier(x):
        return x * n
    return multiplier

times_5 = make_multiplier(5)
print(times_5(4))  # Output: 20
```

#### 3.3 🛠️ Built-in FP Tools

- `map(func, iterable)` → Applies `func` to each item.
- `filter(func, iterable)` → Filters items where `func(item)` is `True`.
- `reduce(func, iterable)` (from `functools`) → Reduces iterable to a single value using `func`.

```python
from functools import reduce
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, nums))
print(squared)              # Output: [1, 4, 9, 16]

evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)               # Output: [2, 4]

total = reduce(lambda a, b: a + b, nums)
print(total)               # Output: 10
```

---

### 4. 🌐 Languages & FP Support

| 🌐 Language     | 🚀 FP Features                     |
|-----------------|------------------------------------|
| Python          | First-class functions, lambdas, built-ins (`map`, `filter`, `reduce`) |
| JavaScript      | First-class functions, arrow functions (no true multithreading) |
| Java (>=8)      | Lambdas, `Stream` API              |
| C++             | Limited FP (function pointers, lambdas) but not a "pure" FP language |

---

### 5. 💡 Best Practices & Community

1. **Start with strong OOP fundamentals** before diving into FP.
2. Use FP to **reduce boilerplate** and **increase readability**, but avoid overuse.
3. Prefer **built-in libraries** (e.g., `itertools`, `functools`) for efficiency.
4. Engage with communities (e.g., Python's FP-focused forums) to learn idiomatic patterns.

---

*Keep these notes for quick revision and refer back to code examples when practicing.*

---

### 6. 🏛️ Deep Dive: Object-Oriented Programming (OOP)

#### 6.1 🛠️ OOP Languages

- **Popular OOP Languages**: C++, Java, Python, JavaScript, Go, Scala.
- **Why OOP?**
  - Emphasizes objects—real-world entities with encapsulated state and behavior.
  - Promotes modularity, reusability, and maintainability.

#### 6.2 ⚙️ Classes vs. Objects

- **Class**: A blueprint or template defining attributes and methods.
- **Object**: An instance of a class—a concrete entity in memory.
  - Example: `class Car:` defines structure; `my_car = Car()` creates an object.

#### 6.3 🔎 What Is an Object?

An object has four pillars:
1. **State**: Current values of its attributes (e.g., size, color, weight, name, price).
2. **Behavior**: Actions and reactions (e.g., `drive()`, `stop()`).
3. **Identity**: Unique identification (e.g., a VIN for a car).
4. **Responsibility**: Role or goal it fulfills (e.g., `PaymentProcessor` processes payments).

> Note: Behavior (methods) implement responsibilities (higher-level tasks).

#### 6.4 🔐 Four Pillars of OOP

1. **Encapsulation**
   - Bundle code and data; control access with access specifiers (`private`, `protected`, `public`).
   - Hides sensitive data; use getters/setters for controlled access.
   - **Real-World**: ATM card (object) hides account details; you use PIN (getter) to access.

2. **Abstraction**
   - Simplify complexity by exposing only necessary details.
   - Focus on *what* an object does, not *how*.
   - **Example**: Driving a car—driver uses `accelerator`, `brake`, without knowing engine internals.

3. **Inheritance**
   - Enables one class (`Child`) to acquire properties of another (`Parent`).
   - Represents an **“is-a”** relationship (e.g., `Sedan` is a `Car`).
   - Constructor chaining: `super()` invokes parent constructor first.

4. **Polymorphism**
   - Objects behave differently under the same interface.
   - **Runtime (Overriding)**: Child class redefines parent methods (true polymorphism).
   - **Compile-time (Overloading)**: Same method name, different parameters (partial polymorphism).

#### 6.5 🔗 Relationships: IS-A vs. HAS-A

- **IS-A**: Inheritance/subtyping (e.g., `Alto` **is-a** `Car`).
- **HAS-A**: Composition/aggregation (e.g., `Car` **has-a** `Engine`, `Computer` **has-a** `HardDisk`).

#### 6.6 ⚙️ Procedural vs. OOP

- **Procedural Programming**:
  - Focus on functions and sequence of actions.
  - Code can be lengthy; reusability via functions, but less modular.
- **OOP**:
  - Focus on objects and their interactions.
  - Promotes reusability, maintainability, and cleaner code structure.

---*

Here’s a refined, well-structured version of your Python OOP notes in markdown format. The goal is to make them clearer, more organized, and easier for future revision. I've preserved your original examples and outputs while enhancing the formatting, explanations, and readability.

---


## 🔹 What is a Class?

- A **Class** is a blueprint for creating objects (a particular data structure).
- The term comes from **Classification** — grouping similar objects.
- It bundles **attributes** (variables) and **methods** (functions) that operate on those attributes.

---

## 🔹 First OOP Program

```python
class Employee:
    empid = 1
    ename = ""
    salary = 0
    
    def __init__(self, empid, ename, salary):  # Parameterized Constructor
        self.empid = empid
        self.ename = ename
        self.salary = salary
    
    def printEmp(self):  # Acts like 'this' in other languages
        print(f"EMPID: {self.empid}")
        print(f"EMAIL: {self.ename}")
        print(f"SALARY: {self.salary}")

e = Employee(1, "abc", 99000)
e.printEmp()
```

### ✅ Output:
```
EMPID: 1
EMAIL: abc
SALARY: 99000
```

---

## 🔹 Inheritance in Python

```python
class Employee:
    def __init__(self, empid, ename, salary):
        self.empid = empid
        self.ename = ename
        self.salary = salary
    
    def printEmp(self):
        print(f"EMPID: {self.empid}")
        print(f"EMAIL: {self.ename}")
        print(f"SALARY: {self.salary}")

class Developer(Employee):  # Inherits Employee
    def __init__(self, empid, ename, salary, devAllowance):
        super().__init__(empid, ename, salary)  # Reuse parent constructor
        self.devAllowance = devAllowance
    
    def printEmp(self):
        super().printEmp()  # Call parent method
        print("ALLOWANCE: ", self.devAllowance)

e = Employee(7, "james", 11000)
e.printEmp()

print("------------------------------")

d = Developer(1, "abc", 99000, 11000)
d.printEmp()
```

### ✅ Output:
```
EMPID: 7
EMAIL: james
SALARY: 11000
------------------------------
EMPID: 1
EMAIL: abc
SALARY: 99000
ALLOWANCE:  11000
```

---

## 📝 Assignment 1: Basic Calculator Class

```python
class Calculator:
    def __init__(self, num1, num2):
        self.num1 = num1
        self.num2 = num2

    def add(self):
        print(f"Addition: {self.num1 + self.num2}")
    def sub(self):
        print(f"Subtraction: {self.num1 - self.num2}")
    def multiply(self):
        print(f"Multiplication: {self.num1 * self.num2}")
    def divide(self):
        print(f"Division: {self.num1 // self.num2}")

c = Calculator(40, 20)
c.add()
c.sub()
c.multiply()
c.divide()
```

### ✅ Output:
```
Addition: 60
Subtraction: 20
Multiplication: 800
Division: 2
```

---

## 📝 Assignment 2: Advanced Calculator with Inheritance + Polymorphism

```python
class Calculator:
    def __init__(self, num1, num2=1):
        self.num1 = num1
        self.num2 = num2

    def add(self):
        print(f"Addition: {self.num1 + self.num2}")
    def sub(self):
        print(f"Subtraction: {self.num1 - self.num2}")
    def multiply(self):
        print(f"Multiplication: {self.num1 * self.num2}")
    def divide(self):
        print(f"Division: {self.num1 // self.num2}")

class advanceCalculator(Calculator):  # Inherits Calculator
    def __init__(self, num1, num2, power):
        super().__init__(num1, num2)
        self.power = power

    def exponentiation(self):
        super().add()
        super().sub()
        super().multiply()
        super().divide()
        print(f"Exponentiation: {pow(self.num1, self.power)}")

a = advanceCalculator(2, 3, 4)
a.exponentiation()
```

### ✅ Output:
```
Addition: 5
Subtraction: -1
Multiplication: 6
Division: 0
Exponentiation: 16
```

---

## 🔍 Scope of Variables in OOP

| Scope      | Description |
|------------|-------------|
| **Static** | Belongs to class, not instance. Shared among all objects. Access via class name. |
| **Instance** | Belongs to individual object (self). Unique per object. Access via object name. |
| **Local** | Declared inside a method. Accessible only within that method. |

---

## 🔁 Function Overloading in Python

- Python **does not support traditional function overloading** like C++ or Java.
- Same function name can be reused, but the latest definition **overwrites** previous ones.
- You can mimic overloading using:
  - Default arguments
  - Variable-length arguments (`*args`, `**kwargs`)
  - Type-checking (with `isinstance()`)

---

## 📌 Important Concepts

- `self`: Refers to the **current object** of the class (like `this` in Java/C++).
- Reference variable:
  ```python
  p = Person("Arya", 1234567890)
  ```
  - Here, `p` is a **reference variable** pointing to a `Person` object.
- Python supports **pointers internally**, but direct pointer manipulation is not allowed.

---

# 🧾 OOP: Employee, Manager, MarketingExecutive — Salary Calculation

## 🔹 Class `Employee`

- Attributes:
  - `empid`, `ename`, `basicSalary`
  - `pf`: 12% of basic salary
  - `pt`: ₹200 (fixed)
  - `hra`: 50% of basic salary
- Methods:
  - `grossSalary()` = `basicSalary + hra + pf + pt`
  - `netSalary()` = `grossSalary - pf - pt`
  - `printSalary()` → prints gross and net salary

```python
class Employee:
    
    def __init__(self, empid, ename, basicSalary):
        self.empid = empid
        self.ename = ename
        self.basicSalary = basicSalary
        self.pf = 0.12 * self.basicSalary
        self.pt = 200
        self.hra = 0.5 * self.basicSalary
        
    def grossSalary(self):
        return self.basicSalary + self.hra + self.pf + self.pt
        
    def netSalary(self):
        return self.grossSalary() - self.pf - self.pt
    
    def printSalary(self):
        print(f"Gross Salary: {self.grossSalary()}")
        print(f"Net Salary: {self.netSalary()}")
```

---

## 🔹 Subclass `Manager` (Inherits `Employee`)

- Additional Allowances:
  - Manager Allowance: 10% of basic salary
  - Food Allowance: 8% of basic salary
  - Other Allowance: 3% of basic salary
- Overrides `grossSalary()` to include new allowances

```python
class Manager(Employee):
    
    def __init__(self, empid, ename, basicSalary):
        super().__init__(empid, ename, basicSalary)
        self.managerAllowance = 0.1 * self.basicSalary
        self.foodAllowance = 0.08 * self.basicSalary
        self.otherAllowance = 0.03 * self.basicSalary
        
    def grossSalary(self):
        return super().grossSalary() + self.managerAllowance + self.foodAllowance + self.otherAllowance
```

---

## 🔹 Subclass `MarketingExecutive` (Inherits `Employee`)

- Additional Attributes:
  - Phone Allowance: ₹1500 (fixed)
  - Travel Allowance: ₹5 per km
- Takes additional parameter: `kmsTravelled`

```python
class MarketingExecutive(Employee):
    
    def __init__(self, empid, ename, basicSalary, kmsTravelled):
        super().__init__(empid, ename, basicSalary)
        self.phoneAllowance = 1500
        self.kmsTravelled = kmsTravelled
        self.travelAllowance = 5 * self.kmsTravelled
        
    def grossSalary(self):
        return super().grossSalary() + self.phoneAllowance + self.travelAllowance
```

---

## 🔍 Output Example

```python
print("Employee Details:")
employee = Employee(123, "Arya", 100000)
employee.printSalary()

print("\nManager Details:")
manager = Manager(123, "Arya", 100000)
manager.printSalary()

print("\nMarketing Executive Details:")
me = MarketingExecutive(123, "Arya", 100000, 56)
me.printSalary()
```

### ✅ Output:
```
Employee Details:
Gross Salary: 162200.0
Net Salary: 162000.0

Manager Details:
Gross Salary: 193000.0
Net Salary: 192800.0

Marketing Executive Details:
Gross Salary: 165480.0
Net Salary: 165280.0
```

---

# 👤 OOP: Class `Person` and Object Comparison

## 🔹 Example: Class with `__init__()` and `printPerson()`

```python
class Person:
    def __init__(self, personname, phone):
        self.personname = personname
        self.phone = phone
        
    def printPerson(self):
        print(f"Person Name: {self.personname}")
        print(f"Phone Number: {self.phone}")
```

## 🔹 Example with Default Constructor

```python
class Person:
    def __init__(self):
        self.personname = "Arya"
        self.phone = 1234567890
```

---

## 🔹 Using `__repr__()` for Displaying Objects

```python
class Person:
    def __init__(self, personname, phone):
        self.personname = personname
        self.phone = phone
        
    def __repr__(self):
        return "Person Name: " + self.personname + " Phone Number: " + str(self.phone)
```

---

## 🔹 Operator Overloading

```python
    def __eq__(self, other):
        return self.phone == other.phone
    
    # For sorting support, define __lt__ or __gt__
    # def __lt__(self, other):
    #     return self.phone < other.phone
```

---

## 🔍 List of Objects & Sorting

```python
p1 = [Person("abc", 123), Person("abc", 999), Person("aaa", 111)]

print("\nOriginal List:")
for person in p1:
    person.printPerson()

print("\nSorted List:")
# p1.sort()  # Uncomment __lt__ or __gt__ to enable sorting
print(p1)

print("\nComparing Objects:")
# print(p1[0] == p1[1])  # Uses __eq__
# print(p1[0] < p1[1])   # Uses __lt__
# print(p1[0] > p1[1])   # Uses __gt__
```

---
