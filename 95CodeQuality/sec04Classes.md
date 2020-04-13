# Creating High-Quality Code: Working Classes

## (Ontological) Reasons to create a class 

Sometimes the idea that the only reason to create a class is to **model real-world objects**

In practice, classes get created for **many more reasons**

- Model real-world objects
- Model abstract objects
- Reduce complexity
- Isolate complexity
- Hide implementation details
- Limit effects of changes
- Make central points of control
- Facilitate reusable code


## Class foundations: Abstract Data Types (ADTs)

An **abstract data type** is a coherent collection of

- Data and operations that work on that data

Benefits of using ADTs

- You can hide implementation details
- Changes don't affect the whole program
- You can make the interface more informative
- It's easier to improve performance
- The program is more obviously correct
- The program becomes more self-documenting
- You don't have to pass data all over your program

Each ADT can be implemented as its **own class**

Which can be thought as an **ADT plus inheritance and polymorphism**

## Good class interfaces

Creating a high-quality class means creating a good interface. That is:

**Good abstraction**

A class interface provides an abstraction of the implementation that's hidden behind and offer a group of routines that **clearly belong together**

**Good encapsulation**

Encapsulation prevents you from looking at the details even if you want to

- Minimise accessibility of classes and members
- Don't expose member data in public
- Avoid putting private implementation details into a class's interface
- Don't make a routine public because it uses only public routines
- Favor read-time convenience to write-time convenience
- Be very, very wary of semantic violations of encapsulation

## Design and implementation issues - Containment

Besides good classes interfaces, the internal class design and implementation are also important

Few points to consider

**Containment -- _has a_ relationships -- **

Containment is the simple idea that a class contains a primitive data element or object

- Implement _has a_ through private inheritance as a last resort
- Be critical of classes with more than about seven data members

## Design and implementation issues - Inheritance

**Inheritance -- _is a_ relationships -- **

Inheritance is the idea that one class is a specialisation of another class:

- Will the routines / data member be visible to derived classes ? 
- Default implementation? 
- Overridable ?

Few tips to make these decisions:

- Implement _is a_ through public inheritance
- Adhere to the Liskov Substitution Principle (LSP)
- Be sure to inherit only what you want to inherit
- Don’t “override” a non-overridable member function
- Move common interfaces, data, and behavior as high as possible in the inheritance tree

## Design and implementation issues - More inheritance

- Be suspicious of classes of which there is only one instance
- Be suspicious of base classes of which there is only one derived class
- Be suspicious of classes that override a routine and do nothing inside the derived routine
- Avoid deep inheritance trees
- Prefer polymorphism to extensive type checking
- Make all data private, not protected

## Design and implementation issues - Member functions and data

**Member Functions and Data**

- Keep the number of routines in a class as small as possible
- Disallow implicitly generated member functions and operators you don’t want
- Minimise the number of different routines called by a class
- Minimise indirect routine calls to other classes
- In general, minimise the extent to which a class collaborates with other classes

## Design and implementation issues - Constructors

**Constructors**

- Initialise all member data in all constructors, if possible
  - Inexpensive defensive programming practice
- Enforce the singleton property by using a private constructor
- Prefer deep copies to shallow copies until proven otherwise
  - Simpler to code and maintain
  - Shallow copies add code to count references
  - Ensure safe object copies, safe comparisons, safe deletes

## Summary

- Class interfaces should provide a consistent abstraction
  - Many problems arise from violating this single principle
- A class interface should hide something
  - A system interface
  - A design decision
  - An implementation detail.
- Containment is usually preferable to inheritance unless you’re modeling an _is a_ relationship
- Inheritance is a useful tool, but it adds complexity
  - Works adversely to Software’s Primary Technical Imperative of managing complexity
- Classes are your primary tool for managing complexity
  - Give their design as much attention as needed to accomplish that objective
