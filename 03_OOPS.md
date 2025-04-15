An object is a real world entity.

Class Loader is a component of JVM.

We have to avoid memory wastage.
Static is used to save memory.
But this is not a good practice.
Static is like global.
In OOPS, object is the main actor.

What if we start treating function as if it is an object?
Memory allocation will happen to single function.
That is what functional programming is.
Here, function is treated as object.

In Functional Programming, we can pass Functions as parameters.
Every FP is OOP Language.
A Function can return only one value and not values.
In case of list, we does not give an entire list, but its reference.

Beauty of FP:
Faster execution
You can pass function to another function
One function returns another function
This is overriding.

Good Example of FP:
Python
Python 3
Javascript (does not have multithreading, virtual threads)
Java, since Java 8.
C++ is not a FP Language.

Instead of using FP, we would have used `for` loop.
But with FP, when passing function as parameter, it gives programmers ease of use.

Now, onwards treat a function as object.
Whenever we write a function inside a class, it is called as method.
FP is focussed in writing less lines of code.
Reducing boilerplate code.
FP needs more inbuilt libraries.
Only those FP are famous those have a strong community.
To achieve our goals faster.
But first of all, our OOPS must be strong.

------------------------------------------------------------------------------

OOP (Object Oriented Programming):

CPP, Java, python, Javascript, Go, Scala is OOP Language.
Why?

Class is template.
Object is real world entity.

Procedural Programming Object:
Though there is reusability, we have to write lengthy code.
Focus was on creating code. Sequence and logic doesn't matter.

What is an Object?
Any real world entity that has state, behaviour, identity and responsibiity is referred as object.
e.g. Everything in this world is an object, i.e., cars, fans, person, student, etc.

State: Set of Attributes, but not just attributes, current values of attributes
e.g. Size, Color, Weight, Name, Price, Brand, Ink Capacity, Blood Group, Height etc.
Behaviour: Actions and reactions performed by the object.
e.g., Functioning, Writing.
Identity: one or more attribute which uniquely identify that object.
Responsibility: Role/goal that object serving in current requirement.
Behaviour and Responsibility are not same.
We perform behaviour to complete the responsibility.
Infinite attributes can be associated with an object. Same for behaviour.
Then why do we write limited number of attributes and methods for an object? How to decide?
Usecase, Based on the requirement.

In Encapsulation, we hide something. We use access specifiers here.
Difference between Encapsulation and Abstraction with Real World Example.

Rules:
1. ENCAPSULATION
2. ABSTRACTION
3. INHERITANCE
4. POLYMORPHISM

1. Encapsulation:
   Bind Code and Data together, so code can control access of data.
   Output: Hide data that is sensitive. Data security.
   Real World Example.
   getters() and setters() / accessors and mutators
2. Abstraction:
   Hide unnecessary Complexity.
   Choosing what is required while ignoring what is not required and not hiding.
   What is Complexity here: No. of attributes, no. of methods, which attributes are useful for me.
   e.g., Person got hospital details, academic records are not required.

   Inner Class: A Class written inside another class is Inner Class.
   But what is its purpose, goal, achievement of this class?
   private members are directly accessible in Inner Classes.
   Can access private methods as well.
   Inner Class can be private but not the Outer class.

   Types:
   Nested Static, Non-static, Anonymous 
   
3. Inheritance:
   We get reusability. We can access class with the help of another class.
   
   Two relationship between objects:
   Has A Relationship
   Is A Relationship

   Inheritance has "Is-a" Relationship.

   One object acquires properties of another object.
   Reusability with ownership.
   Ability to change.

4. Polymorphism:
   When similar objects behave differently when given same commands.
   Only behaviours can be polymorphic.
   Ability to change with ownership.
   When there is Inheritance, then only Polymorphism is possible.

   Method Overriding is true polymorphism.
   While Method Overloading is partial polymorphism.

IS A and HAS A Relation:

IS A:
Two objects can be simiar when they are of same type (i.e. through Inheritance)
e.g. Alto IS A Car

HAS A:
containment: When one object contains another object
e.g. Car HAS A engine.
Computer HAS A Harddisk.
   





































   
   


