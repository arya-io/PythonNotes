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

This was an example of Custom Exception.

There are two types of exceptions in Java:
Checked and unchecked exceptions.
What are in Python?
