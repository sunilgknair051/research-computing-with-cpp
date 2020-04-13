# Creating High-Quality Code: Design in construction

## Introduction to design in construction

Somtimes design isn’t really considered a construction activity 

But many activities are thought of as construction, often including design

Sometimes formal architecture might address only the system-level issues 

And much design work might intentionally be left for construction

Or the design might be intended to be detailed enough for coding to be fairly mechanical 

## Design in construction

A lot of design is done while the programmer sits at the keyboard

It might be 

- Just writing a class interface in pseudocode before writing the details
- Drawing diagrams of a few class relationships before coding them
- Asking which design pattern seems like a better choice

Projects benefit from careful design

Recognising design as an explicit activity maximises the returning benefit

## Design challenges - 1

**Design is a wicked problem**

- You have to solve the problem once in order to clearly define it and then solve it again to create a solution that works

**Design is a sloppy process**

- You take many false steps and go down many blind alleys you make a lot of mistakes

**Design is about tradeoffs and priorities**

- A key part of the designer’s job is to weigh competing design characteristics and strike a balance among those characteristics

## Design challenges - 2

**Design involves restrictions**

- The point of design is partly to create possibilities and partly to restrict possibilities

**Design is nondeterministic**

- There are usually dozens of ways to design a computer program

**Design is a heuristic process**

- Because design is nondeterministic, design techniques tend to be heuristics

## Key design concepts

\begin{center}
\textbf{Software’s Primary Technical Imperative: Managing Complexity}
\end{center}

Software development is a notoriously and inherently complex task

When projects do fail for reasons that are primarily technical, the reason is often **uncontrolled complexity**

## How to deal with complexity ?

Overly costly, ineffective designs arise from three sources:

- A complex solution to a simple problem
- A simple, incorrect solution to a complex problem
- An inappropriate, complex solution to a complex problem

A two-prong approach to managing complexity:

- Minimize the amount of _essential complexity_ that anyone’s brain has to deal with at any one time
  - Hierachical approach
- Keep _accidental complexity_ from needlessly proliferating

## Desirable characteristics of a design - 1

Design is creating a good set of tradeoffs from competing objectives

**Minimal complexity**

- The primary goal of design should be to minimise complexity. Make _simple_ and _easy-to-understand_ designs 

**Ease of maintenance**

- Designing for the maintenance programmer as your audience and design the system to be self-explanatory

**Loose coupling**

- Means to design classes with as few interconnections as possible
  - Good abstractions in class interfaces
  - Encapsulation
  - Information hiding

## Desirable characteristics of a design - 2

**Extensibility**

- Extensibility means that you can enhance a system without causing violence to the underlying structure

**Reusability**

- Reusability means designing the system so that you can reuse pieces of it in other systems

**High fan-in**

- High fan-in refers to having a high number of classes that use a given class. Make good use of utility classes at the lower levels in the system

## Desirable characteristics of a design - 3

**Low-to-medium fan-out**

- Low-to-medium fan-out means having a given class use a low-to-medium number of other classes

**Portability**

- Portability means designing the system so that you can easily move it to another environment

**Leanness**

- Leanness means designing the system so that it has no extra parts

**Stratification**

- Means keeping the levels of decomposition stratified so that you can view the system at any single level and get a consistent view


## Levels of design - hierachy

Design is needed at several different levels of detail in a software system

**Level 1: Software System**

- The first level is the entire system 

**Level 2: Division into Subsystems or Packages**

- The main product of design at this level is the identification of all major subsystems

**Level 3: Division into Classes**

- Design at this level includes identifying all classes in the system

**Level 4: Division into Routines**

- Design at this level includes dividing each class into routines


## Design heuristics - 1

Because design is nondeterministic, skillful application of an effective set of heuristics is the core activity in good software design

**Find real-world objects**

The steps in designing with objects are

- Identify the objects and their attributes (methods and data).
- Determine what can be done to each object.
- Determine what each object is allowed to do to other objects.
- Determine the parts of each object that will be
  - Visible to other objects
  - Public and private
- Define each object's public interface

## Design heuristics - 2

**Form consistent abstractions**

- Abstraction is the ability to engage with a concept while safely ignoring some of its details
  - Handling different details at different levels

**Encapsulate implementation details**

- Encapsulation work hand-in-hand with abstraction 
- It restricts access to an object at any other level of detail

## Design heuristics - 3

**Inherit—when it simplifies the design**

- Defining similarities and differences among such objects is called _inheritance_ 
- It works synergistically with abstraction
- It simplifies programming because you write a general routine to handle what depends on general properties and then specific routines to handle specific operations

**Hide secrets (information hiding)**

- Each class (or package or routine) is characterised by the design or construction decisions that it hides from all other classes 
- In object-oriented design, it gives rise to
    - Encapsulation
    - Modularity
