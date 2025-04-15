```markdown
# 💡 Python Notes: Functional Programming (FP) + Object-Oriented Programming (OOP)

---

## 🔧 Functional Programming (FP)

- In FP, **functions are treated as first-class citizens** — they can be passed around like variables.
- Goal: **Faster execution**, **less boilerplate code**, and **clear modularity**.

### 📌 Key Concepts:
- Functions can be passed as parameters.
- Functions can return other functions.
- FP prefers **immutability**, unlike OOP.
- Python, JavaScript (after ES6), Java 8+, and Scala support FP.

---

## 🧱 Object-Oriented Programming (OOP)

### 🎯 Core Concepts:
1. **Encapsulation**  
   → Hiding sensitive data using access modifiers, controlled via getters and setters.

2. **Abstraction**  
   → Hiding unnecessary details and exposing only essential parts.

3. **Inheritance**  
   → Reusing code by inheriting properties/methods of one class into another.

4. **Polymorphism**  
   → One interface, many implementations (overriding, overloading).

---

## 🧠 Definitions

| Term          | Meaning |
|---------------|---------|
| **Class**     | Blueprint for objects (grouping of attributes and methods) |
| **Object**    | Real-world entity with `State`, `Behavior`, `Identity`, and `Responsibility` |
| **State**     | Data or attributes (e.g., color, size) |
| **Behavior**  | What the object can do (methods) |
| **Identity**  | Unique property of an object |
| **Responsibility** | Role played by the object |

---

## 🧪 First OOP Example in Python

### ✅ `Employee` Class

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

e = Employee(1, "abc", 99000)
e.printEmp()
```

### 🖨️ Output:
```
EMPID: 1
EMAIL: abc
SALARY: 99000
```

---

## 🧬 Inheritance Example

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

class Developer(Employee):
    def __init__(self, empid, ename, salary, devAllowance):
        super().__init__(empid, ename, salary)
        self.devAllowance = devAllowance

    def printEmp(self):
        super().printEmp()
        print("ALLOWANCE:", self.devAllowance)

e = Employee(7, "james", 11000)
e.printEmp()
print("------------------------------")
d = Developer(1, "abc", 99000, 11000)
d.printEmp()
```

### 🖨️ Output:
```
EMPID: 7
EMAIL: james
SALARY: 11000
------------------------------
EMPID: 1
EMAIL: abc
SALARY: 99000
ALLOWANCE: 11000
```

---

## 🧠 Assignment 1: Calculator Class

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

### 🖨️ Output:
```
Addition: 60
Subtraction: 20
Multiplication: 800
Division: 2
```

---

## 🧠 Assignment 2: Advanced Calculator (Inheritance + Polymorphism)

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

class advanceCalculator(Calculator):
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

### 🖨️ Output:
```
Addition: 5
Subtraction: -1
Multiplication: 6
Division: 0
Exponentiation: 16
```

---

## 🧩 IS-A vs HAS-A

| Relationship | Meaning                          | Example                |
|--------------|----------------------------------|------------------------|
| **IS-A**     | Inheritance-based relationship   | Alto IS-A Car         |
| **HAS-A**    | Containment (Composition)        | Car HAS-A Engine      |

---

## 💬 Final Note

Before diving deep into Functional Programming (FP), strengthen your understanding of **OOP principles** like:
- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

Once comfortable, combining FP with OOP gives you great **flexibility**, **readability**, and **performance** in modern Python projects.

---
