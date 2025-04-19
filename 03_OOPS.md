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

# 🐍 Python Abstract Classes & Methods �

## 🌌 Abstract Concepts
- **Virtual**: Exists in effect but not in reality
- **Imaginary**: Conceptual rather than concrete

## 🏗️ Class Types
- **Abstract Class**:
  - May contain both abstract **and** non-abstract methods
  - Requires inheritance to be useful
  - Cannot be instantiated directly
- **Concrete Class**:
  - Fully implemented class
  - Can be instantiated (objects can be created)

## ❓ Why Can't We Instantiate Abstract Classes?
In most programming languages (including Python):
1. Abstract classes are **incomplete** by design
2. They serve as **templates** for other classes
3. Instantiation would lead to undefined behavior (since abstract methods have no implementation)

## 🛠️ Python Implementation
```python
from abc import ABC, abstractmethod  # Required imports

class Animal(ABC):  # Abstract Base Class 🏗️
    @abstractmethod  # Decorator for abstract methods
    def eat(self):
        pass  # No implementation
    
    @abstractmethod
    def walk(self):
        pass
    
    @abstractmethod
    def hello(self):
        print("Hello World")  # Has implementation but will be overridden
```

## 🐱 Concrete Implementation Example
```python
class Cat(Animal):  # Must implement all abstract methods
    def eat(self):
        print("Cat eats...")  # 🐟 Concrete implementation
        
    def walk(self):
        print("Cat walks...")  # 🐾 Concrete implementation
        
    def hello(self):
        print("We are in child class")  # Overrides parent implementation
```

## 🚫 Illegal vs ✅ Legal
```python
# a = Animal()  # ❌ TypeError: Can't instantiate abstract class
c = Cat()       # ✅ Legal - Concrete class
c.eat()         # Output: Cat eats...
c.walk()        # Output: Cat walks...
c.hello()       # Output: We are in child class
```

## 💡 Key Observations from Your Code
1. Even though `hello()` had an implementation in the abstract class, it **must still be overridden** in the concrete class
2. The `@abstractmethod` decorator **forces** implementation in child classes
3. Python's abstraction is more **flexible** than Java's (you can mix abstract/concrete methods)

## � Common Pitfalls
- Forgetting to implement **all** abstract methods → `TypeError`
- Trying to use `super()` in abstract methods without proper implementation
- Assuming abstract methods can't have any implementation (they can, but it's usually overridden)

## 🆚 Java Comparison
| Feature        | Python            | Java               |
|---------------|-------------------|--------------------|
| Annotation    | `@abstractmethod` | `abstract` keyword |
| Base Class    | `ABC`             | `abstract class`   |
| Enforcement   | Runtime           | Compile-time       |


---

# 🔄 **Static Methods in Python**  
### *No Object Needed!*  

### 🎯 **What is a Static Method?**  
- Belongs to the **class**, not instances.  
- Called **without creating an object**.  
- Memory-efficient (**only one copy** exists).  

### 🛠 **Syntax**  
```python
class Demo:
    @staticmethod  # Decorator to define a static method
    def hello():
        print("hello World")
        
Demo.hello()  # No object needed!
```
**Output:**  
```
hello World
```

---

### ❓ **Why Use Static Methods?**  
1. **Memory Efficiency**: Only **one copy** exists (no per-object allocation).  
2. **Utility Functions**: For logic **not dependent on instance data**.  
3. **Namespace Organization**: Group related functions under a class.  

### 📊 **Example: Returning a Value**  
```python
class Demo:
    @staticmethod
    def hello():
        val_pi = 3.1416  # Local variable
        return val_pi
        
print(Demo.hello())  # Access directly via class
```
**Output:**  
```
3.1416
```

---

### 🌍 **Static Method + Class Variables**  
```python
class Demo:
    globalData = 123  # Class variable (shared across all instances)
    
    @staticmethod
    def hello():
        val_pi = 3.1416
        return val_pi

print(Demo.globalData)  # Access class variable
print(Demo.hello())    # Access static method
```
**Output:**  
```
123
3.1416
```

---

# 🎭 **Special Methods: `__str__` vs `__repr__`**  
### *String Representation of Objects*  

### 📜 **`__str__` (Human-Readable)**  
- Used by `print()` and `str()`.  
- Meant for **end-users**.  

### 📜 **`__repr__` (Developer-Friendly)**  
- Used when object is **inspected** (e.g., in REPL).  
- Meant for **debugging**.  

### 🛠 **Example: Employee Class**  
```python
class Employee:
    def __init__(self, empid, ename, salary):
        self.empid = empid
        self.ename = ename
        self.salary = salary
        
    def __str__(self):  # Called by print()/str()
        return self.ename
    
    def __repr__(self):  # Called by repr()/REPL
        return self.ename
        
e1 = Employee(1, 'abc', 100000)
e2 = Employee(2, 'def', 200000)

print(f"Employee: {str(e1)}")  # Uses __str__
print(e1)  # Also uses __str__ (falls back to __repr__ if __str__ missing)
```
**Output:**  
```
Employee: abc
abc
```

---

### 🔍 **Key Differences**  
| Method | Purpose | Called By |
|--------|---------|-----------|
| `__str__` | User-friendly output | `print()`, `str()` |
| `__repr__` | Debugging/REPL | `repr()`, console inspection |  

### 💡 **Best Practice**  
- Always define **`__repr__`** (used as fallback if `__str__` is missing).  
- `__str__` should be **readable**, `__repr__` should be **unambiguous**.  

---

### 🚀 **When to Use Static Methods?**  
✔ **Math utilities** (e.g., `calculate_pi()`).  
✔ **Global configurations** (e.g., `AppConfig.get_version()`).  
✔ **Pure functions** (no instance data needed).

---------------------


# 🧬 **Inheritance in Python: Multiple vs Multi-Level**  

## 🔄 **Multiple Inheritance**  
### *(One child inherits from **multiple parents**)*  

### 🛠 **Syntax & Behavior**  
```python
class Parent1:
    def __init__(self, name):
        self.name = name
        
    def hello1(self):
        print(f"Hello I am Parent 1: {self.name}")

class Parent2:
    def __init__(self, name):
        self.name = name
        
    def hello2(self):
        print(f"Hello I am Parent 2: {self.name}")

class Child(Parent1, Parent2):  # Inherits from both Parent1 and Parent2
    def __init__(self, name):
        self.name = name
        
    def hello(self):
        print(f"Hello I am Child: {self.name}")
        
c = Child("Viraj")
c.hello()  # Calls Child's method
c.hello1() # Calls Parent1's method
c.hello2() # Calls Parent2's method
```
**Output:**  
```
Hello I am Child: Viraj  
Hello I am Parent 1: Viraj  
Hello I am Parent 2: Viraj  
```

### ⚠ **Key Rules**  
1. **Method Resolution Order (MRO)**: Python checks methods left-to-right in inheritance list (`Child(Parent1, Parent2)` → `Parent1` first).  
2. **Same Method Names**: If `Parent1` and `Parent2` have **same method**, the **leftmost parent** wins.  
3. **Child Overrides Parents**: If the child defines the same method, it **overrides** all parents.  

---

### 🔍 **Example: Conflicting Method Names**  
```python
class Parent1:
    def __hello__(self):
        print("I am Parent Class 1")

class Parent2:
    def __hello__(self):
        print("I am Parent Class 2")

class Child(Parent2, Parent1):  # Parent2 comes first!
    pass  # No __hello__ in Child

c = Child("Arya")
c.__hello__()  # Calls Parent2's method
```
**Output:**  
```
I am Parent Class 2: Arya  
```
**Why?**  
- `Parent2` is listed **first** in `Child(Parent2, Parent1)`, so its method is prioritized.  

---

## 📶 **Multi-Level Inheritance**  
### *(Child → Parent → Grandparent)*  

### 🛠 **Syntax & Behavior**  
```python
class Parent1:
    def __init__(self, name):
        self.name = name
        
    def hello1(self):
        print(f"Hello I am Parent 1: {self.name}")

class Parent2(Parent1):  # Parent2 inherits Parent1
    def __init__(self, name):
        self.name = name
        
    def hello2(self):
        print(f"Hello I am Parent 2: {self.name}")

class Child(Parent2):  # Child inherits Parent2 (and indirectly Parent1)
    def __init__(self, name):
        self.name = name
        
    def hello(self):
        print(f"Hello I am Child: {self.name}")
        
c = Child("Viraj")
c.hello()  # Child's method
c.hello1() # Parent1's method (via Parent2)
c.hello2() # Parent2's method
```
**Output:**  
```
Hello I am Child: Viraj  
Hello I am Parent 1: Viraj  
Hello I am Parent 2: Viraj  
```

### ⚠ **Key Rules**  
1. **Inheritance Chain**: `Child → Parent2 → Parent1`.  
2. **Method Lookup**: Python searches up the chain (**child → parent → grandparent**).  

---

## 🎯 **Key Differences**  
| Feature | Multiple Inheritance | Multi-Level Inheritance |  
|---------|----------------------|-------------------------|  
| **Structure** | One child, multiple parents | Child → Parent → Grandparent |  
| **Use Case** | Combine unrelated features | Build hierarchical relationships |  
| **MRO** | Left-to-right priority | Linear (child to ancestor) |  

---

## 💡 **When to Use Which?**  
- **Multiple Inheritance**:  
  - Combine **independent functionalities** (e.g., `LoggedUser`, `AdminUser`).  
  - Risk: **Diamond problem** (complex MRO).  
- **Multi-Level**:  
  - Model **"is-a" hierarchies** (e.g., `Animal → Bird → Sparrow`).  

---

## 🚀 **Best Practices**  
1. Avoid **deep inheritance chains** (hard to debug).  
2. Use **`super()`** for consistent parent initialization.  
3. Prefer **composition over inheritance** for complex cases.  

---

# 🍰 **Dessert Shop Checkout System**  
### *Implementing Inheritance & Abstract Classes*  

## 📝 **Assignment Overview**  
Build a checkout system for a dessert shop that sells:  
- **Candy** (by weight in grams)  
- **Cookies** (by dozen)  
- **Ice Cream** (fixed price)  
- **Sundae** (ice cream + toppings)  

---

## 🏗 **Class Hierarchy**  
### 1. **Abstract Base Class: `DessertItem`**  
```python
from abc import ABC, abstractmethod 

class DessertItem(ABC):
    def __init__(self, item_Name):
        self.item_Name = item_Name

    @abstractmethod
    def itemCost(self):  # Must be implemented by subclasses
        pass
    
    def itemName(self):  # Concrete method
        return self.item_Name
```
**Key Points:**  
- **`@abstractmethod`**: Forces subclasses to implement `itemCost()`.  
- **`itemName()`**: Common logic for all dessert items.  

---

### 2. **Concrete Classes**  

#### 🍬 **Candy (Price by Weight)**  
```python
class Candy(DessertItem):
    def __init__(self, item_Name, weight):
        super().__init__(item_Name)
        self.weight = weight  # Weight in grams
        
    def itemCost(self):
        return (self.weight * 0.1)  # Converts grams to cost (e.g., 200g → 20 Rs)
```
**Example:**  
- `Candy("Fudge", 200)` → Cost = `200 * 0.1 = 20 Rs`.  

#### 🍪 **Cookie (Price by Dozen)**  
```python
class Cookie(DessertItem):
    def __init__(self, item_Name, units):
        super().__init__(item_Name)
        self.units = units  # Number of cookies
        
    def itemCost(self):
        return (self.units * (100 / 12))  # 100 Rs/dozen → 8.33 Rs per cookie
```
**Example:**  
- `Cookie("Chocolate Chip", 4)` → Cost = `4 * (100/12) ≈ 33.33 Rs`.  

#### 🍦 **Ice Cream (Fixed Price)**  
```python
class IceCream(DessertItem):
    def __init__(self, item_Name):
        super().__init__(item_Name)
        
    def itemCost(self):
        return 50  # Flat rate
```

#### 🍨 **Sundae (Ice Cream + Toppings)**  
```python
class Sundae(IceCream):
    def __init__(self, item_Name, toppingsPrice):
        super().__init__(item_Name)
        self.toppingsPrice = toppingsPrice
        
    def itemCost(self):
        return super().itemCost() + self.toppingsPrice  # IceCream cost + toppings
```
**Example:**  
- `Sundae("Vanilla with Sprinkles", 25)` → Cost = `50 (base) + 25 = 75 Rs`.  

---

## � **Checkout System**  
### **`Checkout` Class Features**  
1. **Add items** to cart.  
2. **Clear cart**.  
3. **Get item count**.  
4. **Calculate total cost**.  
5. **Generate invoice**.  

```python
class Checkout():
    def __init__(self):
        self.cashRegister = list()  # Stores DessertItem objects
    
    def addItemToCart(self, *dessertItem):
        for item in dessertItem:
            self.cashRegister.append(item)
    
    def getNoOfItemsInCart(self):
        return len(self.cashRegister)
    
    def getTotalCost(self):
        return sum(item.itemCost() for item in self.cashRegister)
    
    def __repr__(self):  # Invoice generation
        receipt = "\n".join([
            f"{item.itemName()}: {item.itemCost()}"
            for item in self.cashRegister
        ])
        return f"{receipt}\nTotal: {self.getTotalCost()}"
```

---

## 🖥 **Output Example**  
```python
c = Checkout()
ck = Cookie("Chocolate Cookie", 3)
cd = Candy("Orange Candy", 250)
ic = IceCream("Vanilla IceCream")
sd = Sundae("Vanilla with Strawberry", 25)

c.addItemToCart(ck, cd, ic, sd)
print(c.getNoOfItemsInCart())  # Output: 4
print(c.getTotalCost())       # Output: 175.0
print(c)  # Prints invoice
```
**Invoice Output:**  
```
Chocolate Cookie: 25.0  
Orange Candy: 25.0  
Vanilla IceCream: 50  
Vanilla with Strawberry: 75  
Total: 175.0  
```

---

## 🔧 **Areas for Improvement**  
1. **Price Flexibility**:  
   - Add **price per kg/dozen** as instance variables (e.g., `Candy(..., price_per_kg=50)`).  
2. **Menu Class**:  
   - Create a `Menu` class to list available items and prices.  
3. **Error Handling**:  
   - Validate inputs (e.g., negative weight/units).  

---

# 🏗 **Constructor Chaining in Python**  
### *When One Constructor Calls Another*  

### 🔑 **Key Points**  
1. **Inheritance Requires Constructors**:  
   - If a child class doesn’t define `__init__`, it inherits the parent’s constructor.  
   - If both parent and child have `__init__`, the child **must** call the parent’s constructor explicitly using `super()`.  

2. **Constructor Chaining**:  
   - A constructor calling another constructor (e.g., parent → child).  

### 🛠 **Example**  
```python
class Parent:
    def __init__(self, name):
        self.name = name
        print("Parent constructor called")

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Calls Parent's __init__
        self.age = age
        print("Child constructor called")

c = Child("Alice", 10)
```
**Output:**  
```
Parent constructor called  
Child constructor called  
```

---

# 🕶 **Singleton Class**  
### *Only One Instance Allowed*  

### 🔑 **Key Points**  
1. **Singleton Pattern**: Ensures a class has **only one instance** globally.  
2. **Use Cases**:  
   - Database connections.  
   - Configuration managers.  

### 🛠 **Implementation**  
```python
class Singleton:
    __instance = None  # Private class variable

    @staticmethod
    def getInstance():
        if Singleton.__instance is None:
            Singleton()  # Calls __init__ once
        return Singleton.__instance

    def __init__(self):
        if Singleton.__instance is not None:
            raise Exception("Singleton class already initialized!")
        Singleton.__instance = self

# Usage
s1 = Singleton.getInstance()
s2 = Singleton.getInstance()
print(s1 is s2)  # Output: True (same instance)
```

---

# 🔒 **Access Specifiers in Python**  
### *No Strict Privacy, Just Conventions*  

### 🔑 **Key Points**  
1. **Python Uses Naming Conventions**:  
   - **Public**: No prefix (e.g., `name`).  
   - **Protected**: Single underscore `_` (e.g., `_phone`).  
     - Hint: "Should not be accessed outside."  
   - **Private**: Double underscore `__` (e.g., `__phone`).  
     - Name mangling: `__phone` becomes `_Demo__phone`.  

2. **No Enforcement**: Python trusts developers to follow conventions.  

### 🛠 **Example**  
```python
class Demo:
    def __init__(self, name, phone):
        self.name = name          # Public
        self.__phone = phone      # Private (name-mangled)

    def getPhone(self):           # Getter for private attribute
        return self.__phone

d = Demo("abc", 123)
print(d.name)           # Works (public)
print(d.getPhone())     # Works (via getter)
print(d._Demo__phone)   # Works (but don't do this!)
```
**Output:**  
```
abc  
123  
123  
```

### ⚠ **Common Pitfalls**  
- **No True Privacy**: Even "private" attributes can be accessed with name mangling.  
- **Use Getters/Setters**: For controlled access to private data.  

---

## 🎯 **Key Takeaways**  
1. **Constructor Chaining**: Use `super()` to call parent constructors.  
2. **Singleton**: Override `__new__` or use a static method for single-instance control.  
3. **Access Specifiers**:  
   - Public: `var`  
   - Protected: `_var` (convention only)  
   - Private: `__var` (name-mangled)  
---

# **📚 Python Exception Handling Notes**  

## **1. 🚨 Understanding Errors in Python**  
An **error** is any unusual behavior that:  
- ➗ Deviates from expected program output  
- ❌ Causes unexpected results  
- ⚠️ May terminate the program abruptly (crash)  
- 🔧 Can be caused by software or hardware issues  

### **🔑 Key Concepts:**  
- **🌐 Distributed Systems**: Python supports distributed computing (data stored across multiple nodes).  
- **🛡️ Robust Languages**: Python and Java handle errors gracefully (fault-tolerant).  
- **⚡ Fault Tolerance**: Ability to continue running despite human/logical errors.  

---  

## **2. 🛠️ Types of Error Handling**  
### **A. 🔍 Procedural (Conditional) Approach**  
Check for possible errors using `if-else` before execution.  

### **B. 🐍 Exception Handling (Pythonic Way)**  
Use `try-except` blocks to catch and handle runtime errors.  

---  

## **3. 💻 Practical Examples**  

### **📌 Example 1: Division by Zero**  
#### **🚫 Procedural Approach (Commented)**  
```python
a = int(input("Enter a number: "))
# Procedural check (commented)
# if(a/0):  # This would raise an error before the check
#     print("Error")
# else:
#     print("Please learn Exception Handling")
```  
**❓ Problem**: Division by zero is inherently invalid—conditional checks can't prevent the error.  

#### **✅ Exception Handling Approach**  
```python
try:
    print(a/0)  # Attempt division  
except:
    print("Error")  # Execute if division fails  
```  
**🖥️ Output**:  
```
Enter a number: 5  
Error  
```  
**📝 Explanation**:  
- `try` runs the risky operation (`a/0`).  
- `except` catches the `ZeroDivisionError` and prints a message.  

---  

### **📌 Example 2: List Index Out of Bounds**  
#### **🚫 Exception Handling**  
```python
myList = [2, 5, 4, 6, 5, 6]  
ind = int(input("Enter index: "))  

try:
    print(myList[ind])  # Try accessing the index  
except:
    print("Index Out of Bound")  
```  

#### **✅ Procedural Approach**  
```python
if(ind < len(myList)):  # Check if index is valid  
    print(myList[ind])  
else:
    print("Cannot access element in list.")  
```  
**🖥️ Output**:  
```
Enter index: 10  
Index Out of Bound  
Cannot access element in list.  
```  
**📝 Explanation**:  
- `try` fails for `ind=10` (list has only 6 elements).  
- Procedural check avoids the error by validating the index first.  

---  

### **📌 Example 3: String-Integer Concatenation**  
#### **🚫 Exception Handling**  
```python
try:
    print("Hello" + 3)  # Incompatible types  
except:
    print("Cannot concatenate string and an integer")  
```  

#### **✅ Procedural Approach**  
```python
a = input("Enter string: ")  
b = int(input("Enter integer: "))  

if type(a) is type(b):  # Check if types match  
    print(a + b)  
else:
    print("Cannot concatenate two different data types!")  
```  
**🖥️ Output**:  
```
Cannot concatenate string and an integer  
Enter string: Text  
Enter integer: 100  
Cannot concatenate two different data types!  
```  
**📝 Explanation**:  
- Python raises `TypeError` for `str + int`.  
- Procedural check prevents this by verifying types beforehand.  

---  

## **4. 🎯 Key Takeaways**  
- **🔍 Procedural Checks**: Best for predictable errors (e.g., index bounds).  
- **🛡️ Exception Handling**: Ideal for unpredictable errors (e.g., division by zero).  
- **✨ Pythonic Practice**: Prefer `try-except` for cleaner, more maintainable code.  

### **📖 Terminology**  
- **🚨 Exception**: A runtime error that disrupts normal program flow.  
- **⚡ Fault Tolerance**: System resilience against failures.  
- **🛡️ Robustness**: Language’s ability to handle errors gracefully.  

---  

**🔁 Revision Tip**: Practice by triggering different errors (e.g., `ValueError`, `KeyError`) and handling them with `try-except`.  

------------------------------

# **🚀 Exception Handling in Python**  

## **1. ❓ What is Exception Handling?**  
A mechanism to **gracefully manage runtime errors** without crashing the program.  

### **📌 Example**  
```python
try:
    print(5 / 0)  # Risky operation
except:
    print("Error handled!")  # Fallback action
```  
**Output**:  
```
Error handled!
```  

### **🆚 Exception vs Error**  
| **Error** | **Exception** |  
|-----------|--------------|  
| Caused by **syntax/logical flaws** (e.g., `SyntaxError`) | **Runtime disruptions** (e.g., `ZeroDivisionError`) |  
| **Prevents execution** entirely | **Can be caught and handled** |  

---

## **2. 🔑 Four Keywords in Exception Handling**  

### **❶ `try`**  
- **Defines a block** where exceptions might occur.  
```python
try:
    print(10 / 2)  # No error → executes normally
except:
    print("Error")
```  
**Output**:  
```
5.0
```  

### **❷ `except`**  
- **Catches and handles exceptions**.  
```python
try:
    print(10 / 0)
except ZeroDivisionError:
    print("Can’t divide by zero!")
```  
**Output**:  
```
Can’t divide by zero!
```  

### **❸ `finally`**  
- **Always executes**, whether an error occurs or not.  
- Used for **cleanup** (e.g., closing files).  
```python
try:
    print(5 / 0)
except:
    print("Error")
finally:
    print("This always runs!")
```  
**Output**:  
```
Error  
This always runs!
```  

### **❹ `raise`**  
- **Manually trigger exceptions**.  
```python
if age < 0:
    raise ValueError("Age can’t be negative!")
```  

---

## **3. 🎯 `try-except-else`**  
- **`else` runs only if no exception occurs**.  
```python
try:
    print(5 / 2)  # No error
except:
    print("Error")
else:
    print("Success!")  # Executes if try succeeds
```  
**Output**:  
```
2.5  
Success!
```  

---

## **4. 🔄 `finally` Block**  
### **❓ Why Use It?**  
- **Guaranteed execution** for critical tasks (e.g., releasing resources).  
```python
try:
    file = open("demo.txt", "r")
    print(file.read())
except:
    print("File error")
finally:
    file.close()  # Always closes the file
    print("Resource freed!")
```  

---

## **5. 🎯 Multiple `except` Blocks**  
- **Handle different exceptions separately**.  
```python
a = input("Enter value a: ")
b = input("Enter value b: ")

try:
    c = int(a) / int(b)
except TypeError:
    print("Use numbers only!")
except ValueError:
    print("Invalid conversion to int!")
except ZeroDivisionError:
    print("Denominator can’t be zero!")
except:
    print("Unknown error!")
```  

### **🖥️ Output Examples**  
#### **Case 1: Valid Input**  
```
Enter value a: 6  
Enter value b: 3  
2.0  
```  
#### **Case 2: Invalid Input**  
```
Enter value a: 5  
Enter value b: "hello"  
Invalid conversion to int!  
```  

---

## **6. 💡 Key Takeaways**  
- **`try-except`**: Safely handle errors.  
- **`else`**: Run code only on success.  
- **`finally`**: Mandatory cleanup (e.g., closing files).  
- **Multiple `except`**: Handle specific errors differently.  

**🔧 Pro Tip**: Always order exceptions from **most specific to generic**!  

```python
except ValueError:  # Specific  
except Exception:   # Generic (catches all)  
```

---

# **💰 InsufficientFundsError in Python**  

## **1. ❓ What is `InsufficientFundsError`?**  
- A **custom exception** to handle cases where a transaction fails due to lack of funds.  
- **Inherits** from Python’s base `Exception` class.  

### **📌 Why Use It?**  
- To **enforce business rules** (e.g., "Minimum balance required").  
- Makes code **more readable** by using domain-specific errors.  

---

## **2. 🛠️ How to Define & Use It**  

### **Step 1: Define the Custom Exception**  
```python
class InsufficientFundsError(Exception):  # Inherits from Exception
    pass  # Empty class (uses default behavior)
```

### **Step 2: Raise the Exception**  
```python
balance = 7
MIN_BALANCE = 5

if balance < MIN_BALANCE:
    raise InsufficientFundsError("Balance too low! Minimum required: 5")
```

### **🖥️ Output (When `balance = 3`)**  
```
InsufficientFundsError: Balance too low! Minimum required: 5
```

---

## **3. 🎯 Practical Example**  
### **Bank Transaction Simulation**  
```python
class InsufficientFundsError(Exception):
    pass

def withdraw(amount, balance):
    if amount > balance:
        raise InsufficientFundsError(f"Failed: You need {amount - balance} more!")
    return balance - amount

try:
    print(withdraw(100, 50))  # Triggers error
except InsufficientFundsError as e:
    print(e)
```

**Output**:  
```
Failed: You need 50 more!
```

---

## **4. 💡 Key Takeaways**  
1. **Custom Exceptions** improve code clarity for domain-specific errors.  
2. **`raise`** triggers the exception manually.  
3. **`try-except`** handles these errors gracefully.  

**🔧 Pro Tip**: Add helpful error messages to guide users!  

```python
raise InsufficientFundsError("Minimum balance: $5")  # Better than a generic error
```

**🎉 Now you can build financial apps safely!** 🚀  

--- 

# **🐍 Python vs. ☕ Java Exceptions**

## **1. Python Exception Types**
Python **doesn't have checked exceptions** like Java. All Python exceptions are **unchecked** (runtime exceptions). 

### **📌 Python Exception Categories**
| Type              | Description                          | Example Exceptions              |
|-------------------|--------------------------------------|---------------------------------|
| **Built-in**      | Predefined in Python                 | `ValueError`, `TypeError`, `IndexError` |
| **User-defined**  | Custom exceptions (you create them)  | `InsufficientFundsError` (your example) |

### **Example: Python's Unchecked Nature**
```python
# No compiler forces you to handle this!
print(10 / 0)  # Raises ZeroDivisionError at runtime
```

---

## **2. ☕ Java Exception Types**
Java has **two** explicit types:

| Type              | Description                          | Example                  | Handling Requirement      |
|-------------------|--------------------------------------|--------------------------|--------------------------|
| **Checked**       | Compiler-enforced exceptions         | `IOException`            | Must be caught or declared in method signature (`throws`) |
| **Unchecked**     | Runtime exceptions                   | `NullPointerException`   | Optional handling        |

### **Java Checked Exception Example**
```java
// Compiler ERROR if unhandled!
try {
    FileReader file = new FileReader("nonexistent.txt");
} catch (IOException e) {  // Mandatory handling
    System.out.println("File not found!");
}
```

---

## **3. Key Differences**
| Feature           | Python            | Java               |
|-------------------|-------------------|--------------------|
| **Checked Exceptions** | ❌ Not supported | ✅ Supported (compiler enforced) |
| **Unchecked Exceptions** | ✅ All exceptions are unchecked | ✅ Supported (e.g., `NullPointerException`) |
| **Custom Exceptions** | ✅ Supported (e.g., `class MyError(Exception)`) | ✅ Supported |

---

## **4. Why No Checked Exceptions in Python?**
- **Philosophy**: Python prefers **"easier to ask for forgiveness than permission"** (EAFP).
- **Flexibility**: Avoids forcing developers to handle exceptions they can’t recover from.
- **Example EAFP Style**:
  ```python
  try:
      print(10 / 0)
  except ZeroDivisionError:  # Handling is optional
      print("Handled gracefully!")
  ```

---

## **5. Practical Implications**
### **When to Handle Exceptions in Python?**
- **Recoverable Errors**: File I/O, network calls (e.g., `try-except` for `FileNotFoundError`).
- **Unrecoverable Errors**: `MemoryError` (usually let it crash and log).

### **Java-Style Workaround in Python**
```python
def read_file(filename):
    try:
        with open(filename) as f:
            return f.read()
    except FileNotFoundError as e:
        raise RuntimeError("Must handle this!") from e  # Simulate "checked" behavior
```

---

## **6. 🎯 Summary**
- **Python**: All exceptions are **unchecked** (handling is optional).  
- **Java**: **Checked + Unchecked** (compiler enforces some).  
- **Custom Exceptions**: Work similarly in both (inherit from base `Exception`/`RuntimeException`).  

**💡 Pythonic Approach**: Use `try-except` liberally for expected failures, but don’t overuse for control flow.  

**🚀 Pro Tip**: Use `logging` to track unexpected exceptions instead of suppressing them!  

```python
import logging
try:
    risky_operation()
except Exception as e:
    logging.error(f"Unexpected error: {e}")
    raise  # Re-raise if critical
```
---

# **💾 Data Persistence in Python**

## **1. ❓ What is Data Persistence?**  
- **Definition**: Storing data *permanently* (beyond program execution).  
- **Methods**: Files (e.g., `.txt`, `.csv`) and databases (e.g., SQLite, MySQL).  

---

## **2. 🏎️ Speed Comparison: In-Memory vs. Persistent Storage**  

| **Storage Type**       | **Speed**               | **Persistence** | **Use Case**              |  
|------------------------|-------------------------|------------------|---------------------------|  
| **In-Memory (List/Dict)** | ⚡ *Fastest* (CPU cache/RAM) | ❌ Temporary     | Runtime calculations      |  
| **SSD/HDD (Files/DB)**   | 🐢 *Slower* (I/O latency) | ✅ Permanent     | Long-term data retention  |  

### **🔧 Technical Reasons**  
- **In-Memory**:  
  - Stored in **RAM/CPU cache** (nanosecond access).  
  - Volatile (lost on program restart).  
- **Files/Databases**:  
  - Stored on **disk** (millisecond access, slower due to I/O).  
  - Non-volatile (retained after shutdown).  

---

## **3. 📊 Why Use Files/Databases?**  
### **When In-Memory Fails**  
1. **Data Size**: RAM is limited (e.g., 16GB), while disks offer TBs.  
2. **Durability**: Power loss won’t erase files/databases.  
3. **Sharing**: Multiple programs/users can access the same file/DB.  

### **Example**  
```python
# In-Memory (Volatile)  
users = ["Alice", "Bob"]  # Lost when program exits  

# File Storage (Persistent)  
with open("users.txt", "w") as f:  
    f.write("Alice, Bob")  # Saved permanently  
```

---

## **4. ⚡ Speed Hierarchy**  
**Fastest → Slowest**:  
1. **CPU Registers** (e.g., variables in a loop)  
2. **RAM** (e.g., `list`, `dict`)  
3. **SSD** (e.g., SQLite database)  
4. **HDD** (e.g., large CSV files)  
5. **Network Storage** (e.g., cloud databases)  

### **Real-World Analogy**  
- **RAM** = Your desk (fast but limited space).  
- **Disk** = Filing cabinet (slower but holds more).  

---

## **5. 🛠️ When to Use Each?**  
| **Structure**  | **Persistence** | **Speed** | **Example Use Case**         |  
|---------------|------------------|-----------|-------------------------------|  
| `list`/`dict` | ❌ No           | ⚡ Fast   | Sorting real-time sensor data |  
| File          | ✅ Yes          | 🐢 Slow   | Saving user preferences       |  
| Database      | ✅ Yes          | 🐢 Slow   | Multi-user inventory system   |  

---

## **6. 💡 Key Takeaways**  
- **Use In-Memory**: For temporary, high-speed operations.  
- **Use Files/DBs**: For permanent, large-scale, or shared data.  
- **Trade-off**: Speed vs. durability.  

**🚀 Pro Tip**: For speed-critical apps, **cache** frequently used data in memory (e.g., Redis).  

```python
# Hybrid approach: Load data from disk to memory on startup  
with open("data.json") as f:  
    cache = json.load(f)  # Now fast to access!  
``` 

---

# **📂 File Handling in Python**

## **1. 🗺️ Path Types**
| **Path Type**      | **Description**                          | **Example**                     |
|--------------------|------------------------------------------|---------------------------------|
| **Absolute Path**  | Full path from root directory            | `C:/Users/name/abc.txt` (Windows) or `/home/user/abc.txt` (Linux/Mac) |
| **Relative Path**  | Path relative to current working directory | `./abc.txt` (same folder) or `../parent/abc.txt` (parent folder) |

---

## **2. 📜 Opening a File**
### **Syntax**
```python
file = open("filepath", "mode")  # Modes: r (read), w (write), a (append), etc.
```

### **Example: Write Mode (`'w'`)**
```python
file = open("abc.txt", "w")  # Creates new file (or overwrites existing)
file.write("Hello..!! This is the new file we created.")
file.close()  # ⚠️ Always close files to free resources!
```

### **Example: Read Mode (`'r'`)**
```python
file = open("abc.txt", "r")  # File must exist
data = file.read()  # Reads entire content
file.close()
print(data)
```
**Output**:
```
Hello..!! This is the new file we created.
```

---

## **3. 🔐 Best Practices**
### **A. Use `with` Blocks (Auto-Closes File)**
```python
with open("abc.txt", "r") as file:  # No need to manually close
    data = file.read()
print(data)
```

### **B. File Modes Cheatsheet**
| **Mode** | **Description**                      | **File Exists?** |
|----------|--------------------------------------|------------------|
| `r`      | Read (default)                       | ✅ Yes           |
| `w`      | Write (creates/overwrites)           | ❌ No → Creates  |
| `a`      | Append (adds to end)                 | ❌ No → Creates  |
| `x`      | Exclusive creation (fails if exists) | ❌ No → Creates  |
| `b`      | Binary mode (e.g., `'rb'`)           | -               |

### **C. Handling Paths Cross-Platform**
```python
import os
file_path = os.path.join("folder", "abc.txt")  # Works on Windows/Linux/Mac
with open(file_path, "w") as f:
    f.write("Hello OS-agnostic path!")
```

---

## **4. 🚨 Common Pitfalls**
1. **Forgot to Close**:  
   - ❌ `file = open("x.txt", "w")` (leaks resources)  
   - ✅ Use `with` blocks.

2. **FileNotFoundError**:  
   ```python
   try:
       with open("nonexistent.txt", "r") as f:
           print(f.read())
   except FileNotFoundError:
       print("File not found!")  # Graceful handling
   ```

3. **Encoding Issues**:  
   ```python
   with open("unicode.txt", "w", encoding="utf-8") as f:
       f.write("こんにちは")  # Japanese text
   ```

---

## **5. 📊 Summary**
- **Absolute vs. Relative Paths**: Choose based on portability needs.  
- **`with` Blocks**: Safer and cleaner than manual `close()`.  
- **Modes Matter**: `w` overwrites, `a` appends, `r` reads.  

**🔧 Pro Tip**: Use `pathlib` for modern path handling:
```python
from pathlib import Path
data = Path("abc.txt").read_text()  # One-line read!
```

**🎯 Exercise**: Try creating a log file that appends timestamps!  
```python
import datetime
with open("log.txt", "a") as f:
    f.write(f"{datetime.datetime.now()} - Event occurred\n")
```

---

# **📂 File Handling Operations (Original Code + Explanations)**

## **1. Copying File Contents**  
### Original Code:
```python
a = open("a.txt", "w")
a.write("This is File 'a'. We are copying text of this file 'a' in file 'b'.")
a.close()

a = open("a.txt", "r")
data = a.read()
print("Content of file 'a': ")
print(data)
b = open("b.txt", "w")
b.write(data)
a.close()
b.close()

b = open("b.txt", "r")
data = b.read()
print("\nContent of file 'b':")
print(data)
b.close()
```
### Key Improvements:
1. **Use `with` blocks** (auto-closes files):
```python
with open("a.txt", "w") as a:
    a.write("Original content")

with open("a.txt", "r") as a, open("b.txt", "w") as b:
    b.write(a.read())
```

---

## **2. Flipping Vowel Cases**  
### Original Code:
```python
a = open("a.txt", "w")
a.write("This is File 'a'. We are copying text of this file 'a' in file 'b'.")
a.close()

a = open("a.txt", "r")
data = a.read()
print("Content of file 'a': ")
print(data)

flip_data = ""
for i in data:
    if i in "aeiou":
        flip_data += i.upper()
    elif i in "AEIOU":
        flip_data += i.lower()
    else:
        flip_data += i
        
b = open("b.txt", "w")
b.write(flip_data)
a.close()
b.close()

b = open("b.txt", "r")
data = b.read()
print("\nModified content in 'b':")
print(data)
b.close()
```
### Optimized Approach:
```python
vowel_map = str.maketrans("aeiouAEIOU", "AEIOUaeiou")
with open("a.txt", "r") as a, open("b.txt", "w") as b:
    b.write(a.read().translate(vowel_map))
```

---

## **3. Splitting Odd/Even Lines**  
### Original Code:
```python
a = open("a.txt", "w")
a.write("""This is File 'a'.
We are copying text of this file 'a' in file 'b'.
This is even file.
This is odd line.
This is fourth line.
This is 5th line.""")
a.close()

a = open("a.txt", "r")
data = a.read().split("\n")
print("Original lines:", data)

even, odd = [], []
for i in range(len(data)):
    if i % 2 == 0:
        even.append(data[i])
    else:
        odd.append(data[i])
        
with open("even.txt", "w") as e, open("odd.txt", "w") as o:
    e.write("\n".join(even))
    o.write("\n".join(odd))
```
### Pro Tip:
Use `enumerate()` for cleaner line numbering:
```python
for idx, line in enumerate(data, 1):  # Starts counting at 1
    if idx % 2 == 0: ...
```

---

## **4. Removing Duplicate Lines**  
### Original Code:
```python
a = open("a.txt", "w")
a.write("""This is File 'a'.
This is File 'a'.
We are copying text...
[rest of original content]""")
a.close()

a = open("a.txt", "r")
data = a.read().split("\n")
ans = []
for line in data:
    if line not in ans:
        ans.append(line)

with open("deduped.txt", "w") as out:
    out.write("\n".join(ans))
```
### Memory-Efficient Version (for large files):
```python
seen = set()
with open("bigfile.txt", "r") as infile, open("out.txt", "w") as outfile:
    for line in infile:
        if line not in seen:
            outfile.write(line)
            seen.add(line)
```

---

## **5. The `seek()` Function**  
### Original Functionality Preserved:
```python
# Example of using seek() to reset file pointer
with open("data.txt", "r+") as f:
    print(f.read(5))  # Reads first 5 bytes
    f.seek(0)         # Rewinds to start
    print(f.read()))   # Reads entire file
```
### Common `seek()` Patterns:
| Operation | Code | Description |
|-----------|------|-------------|
| Start | `f.seek(0)` | Beginning of file |
| End | `f.seek(0, 2)` | Jump to end |
| Relative | `f.seek(5, 1)` | Move 5 bytes forward |

---

## **Best Practices Summary**
1. **Always close files** (use `with` blocks)
2. **Specify encodings**: `open(..., encoding='utf-8')`
3. **For large files**: Process line-by-line instead of loading all into memory
4. **Binary files**: Use `'rb'`/`'wb'` modes

```python
# Example: Safe file writing
with open("important.txt", "w", encoding="utf-8") as f:
    f.write("Critical data")
    f.flush()  # Force write to disk
    os.fsync(f.fileno())  # Ensure OS buffer is flushed
```
---

## **1. Copy File Content (with Exception Handling)**
```python
try:
    # Writing to source file
    a = open("a.txt", "w")
    a.write("This is File 'a'. We are copying text of this file 'a' in file 'b'.")
    a.close()

    # Reading and copying
    a = open("a.txt", "r")
    data = a.read()
    print("Content of file 'a':")
    print(data)

    b = open("b.txt", "w")
    b.write(data)
    a.close()
    b.close()

    # Verification
    b = open("b.txt", "r")
    data = b.read()
    print("\nContent of file 'b':")
    print(data)
    b.close()

except FileNotFoundError:
    print("Error: File not found!")
except PermissionError:
    print("Error: No write permission!")
except Exception as e:
    print(f"Unexpected error: {e}")
```
**Output (Success Case)**:
```
Content of file 'a':
This is File 'a'. We are copying text of this file 'a' in file 'b'.

Content of file 'b':
This is File 'a'. We are copying text of this file 'a' in file 'b'.
```
**Output (Error Case - Missing File)**:
```
Error: File not found!
```

---

## **2. Flip Vowel Cases (with Exception Handling)**
```python
try:
    a = open("a.txt", "w")
    a.write("This is File 'a'. We are copying text of this file 'a' in file 'b'.")
    a.close()

    a = open("a.txt", "r")
    data = a.read()
    print("Content of file 'a':")
    print(data)

    flip_data = ""
    for i in data:
        if i in "aeiou":
            flip_data += i.upper()
        elif i in "AEIOU":
            flip_data += i.lower()
        else:
            flip_data += i
        
    b = open("b.txt", "w")
    b.write(flip_data)
    a.close()
    b.close()

    b = open("b.txt", "r")
    data = b.read()
    print("\nModified content in 'b':")
    print(data)
    b.close()

except IOError as e:
    print(f"File operation failed: {e}")
except Exception as e:
    print(f"Error: {e}")
```
**Output (Success Case)**:
```
Content of file 'a':
This is File 'a'. We are copying text of this file 'a' in file 'b'.

Modified content in 'b':
ThIs Is FIlE 'A'. WE ArE cOpyIng tExt Of thIs fIlE 'A' In fIlE 'b'.
```
**Output (Error Case - Permission Denied)**:
```
File operation failed: [Errno 13] Permission denied: 'a.txt'
```

---

## **3. Split Odd/Even Lines (with Exception Handling)**
```python
try:
    a = open("a.txt", "w")
    a.write("""This is File 'a'.
We are copying text of this file 'a' in file 'b'.
This is even file.
This is odd line.
This is fourth line.
This is 5th line.""")
    a.close()

    a = open("a.txt", "r")
    data = a.read().split("\n")
    print("Original lines:")
    print(data)

    even, odd = [], []
    for i in range(len(data)):
        if i % 2 == 0:
            even.append(data[i])
        else:
            odd.append(data[i])
        
    evenFile = open("even.txt", "w")
    oddFile = open("odd.txt", "w")
    evenFile.write("\n".join(even))
    oddFile.write("\n".join(odd))
    a.close()
    evenFile.close()
    oddFile.close()

    # Verification
    with open("even.txt", "r") as f:
        print("\nEven lines:")
        print(f.read())
    with open("odd.txt", "r") as f:
        print("\nOdd lines:")
        print(f.read())

except ValueError as e:
    print(f"Data processing error: {e}")
except Exception as e:
    print(f"Unexpected error: {e}")
```
**Output (Success Case)**:
```
Original lines:
["This is File 'a'.", "We are copying...", ...]

Even lines:
This is File 'a'.
This is even file.
This is fourth line.

Odd lines:
We are copying text...
This is odd line.
This is 5th line.
```

---

## **4. Remove Duplicate Lines (with Exception Handling)**
```python
try:
    a = open("a.txt", "w")
    a.write("""This is File 'a'.
This is File 'a'.
We are copying text...
[rest of original content]""")
    a.close()

    a = open("a.txt", "r")
    data = a.read().split("\n")
    print("Original content with duplicates:")
    print(data)

    ans = []
    for line in data:
        if line not in ans:
            ans.append(line)

    outputFile = open("output.txt", "w")
    outputFile.write("\n".join(ans))
    outputFile.close()

    # Verification
    with open("output.txt", "r") as f:
        print("\nAfter removing duplicates:")
        print(f.read())

except FileNotFoundError:
    print("Error: File not found!")
except MemoryError:
    print("Error: File too large!")
except Exception as e:
    print(f"Unexpected error: {e}")
```
**Output (Success Case)**:
```
Original content with duplicates:
["This is File 'a'.", "This is File 'a'.", ...]

After removing duplicates:
This is File 'a'.
We are copying text...
...
```

---

### **Key Exception Types Handled**
| Error Type | When It Occurs |
|------------|----------------|
| `FileNotFoundError` | File doesn't exist |
| `PermissionError` | No read/write access |
| `IOError` | General I/O failures |
| `MemoryError` | Insufficient RAM for large files |
| `ValueError` | Data format issues |

**Always handle exceptions specifically** before catching general `Exception`.  
**Pro Tip**: Use `logging` for production code:
```python
import logging
try:
    # File operations
except Exception as e:
    logging.error(f"Failed: {e}", exc_info=True)
```

---

# **🚀 Exception Handling & CSV File Operations**

## **1. Why `finally` Block is Essential**
### **Key Reasons:**
1. **Guaranteed Execution**: Runs whether an exception occurs or not  
2. **Resource Cleanup**: Always close files/database connections here  
3. **Avoid Memory Leaks**: Prevents resource hogging  

### **Example with Your Code:**
```python
file = None  # Initialize variable
try:
    file = open("data.txt", "r")
    data = file.read()
    print(data)
except FileNotFoundError:
    print("Error: File missing!")
except Exception as e:
    print(f"Unexpected error: {e}")
finally:
    if file:  # Check if file was opened
        file.close()  # 💡 This always executes
    print("Cleanup completed!")
```

---

## **2. Reading CSV Files (Original Code Preserved)**
### **Your Original Example:**
```python
a = open("C:/Users/dbda.STUDENTSDC\Desktop/data.csv", "r")
data = a.read()
print("Content of file 'a': ")
print("Data: ", data)
a.close()
```
**Output**:
```
Content of file 'a':
Data:  id, name, city, age
1, "arya", "nagpur", 23
2, "viraj", "kolhapur", 23
3, "rishi", "pune", 25
4, "amar", "latur", 23
5, "yash", "nagpur", 23
```

### **Improved Version (with Exception Handling):**
```python
try:
    with open("data.csv", "r") as file:  # Using 'with' for auto-close
        print("CSV Content:")
        print(file.read())
except FileNotFoundError:
    print("Error: CSV file not found!")
except PermissionError:
    print("Error: No read permissions!")
finally:
    print("File operation attempted.")  # Always executes
```

---

## **3. CSV File Structure (As Created in Notepad)**
Your CSV structure (tab-delimited in Notepad):
```
id     name     city       age
1      "arya"   "nagpur"   23
2      "viraj"  "kolhapur" 23
3      "rishi"  "pune"     25
4      "amar"   "latur"    23
5      "yash"   "nagpur"   23
```

### **Best Practices for CSV Handling:**
1. **Use Python's `csv` Module**:
```python
import csv
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)  # Each row as a list
```
**Output**:
```
['id', 'name', 'city', 'age']
['1', 'arya', 'nagpur', '23']
['2', 'viraj', 'kolhapur', '23']
...
```

2. **Handle Different Delimiters**:
```python
with open("data.csv", "r") as file:
    reader = csv.reader(file, delimiter='\t')  # For tab-separated
    for row in reader:
        print(row)
```

---

## **4. Common CSV Errors & Handling**
| Error | Cause | Solution |
|-------|-------|----------|
| `FileNotFoundError` | Wrong path | Verify file location |
| `PermissionError` | File in use | Close file in other programs |
| `csv.Error` | Malformed CSV | Check delimiter/quoting |

### **Robust CSV Reading:**
```python
import csv
try:
    with open("data.csv", "r") as file:
        reader = csv.reader(file)
        header = next(reader)  # Read header
        print("Header:", header)
        for row in reader:
            print("Row:", row)
except csv.Error as e:
    print(f"CSV Error: {e}")
except Exception as e:
    print(f"General Error: {e}")
finally:
    print("Processing complete.")
```
