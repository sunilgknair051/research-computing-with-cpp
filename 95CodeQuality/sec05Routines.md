# Creating High-Quality Code: High-quality routines

## Reasons to Create a Routine

A routine is an individual method or procedure invocable for a single purpose.

What they do is to :

- Make programs easier to read and easier to understand
- Saving space and improve performance
- Introduce an intermediate, understandable abstraction
- Reduce complexity
- Avoid duplicate code
- Support subclassing
- Hide sequences 
- Hide pointer operations
- Improve portability

## Design at the routine level

Abstraction and encapsulation, tend to yield more insight at the class level

**Cohesion** is the workhorse design heuristic at the individual-routine level

Cohesion refers to how closely the operations in a routine are related

The goal is to have each routine do one thing well and not do anything else

Typically refer to several levels of cohesion

## Forms of routine cohesion - 1

**Functional cohesion**

- Is the strongest and best kind of cohesion, occurring when a routine performs one and only one operation

**Sequential cohesion**

- When a routine contains operations that must be performed in a specific order

**Communicational cohesion**

- Occurs when operations in a routine make use of the same data and aren’t related in any other way

## Forms of routine cohesion - 2

**Temporal cohesion**

- Occurs when operations are combined into a routine because they are all done at the same time

**Procedural cohesion**

- Occurs when operations in a routine are done in a specified order

**Logical cohesion**

- Occurs when several operations are stuffed into the same routine and one of the operations is selected by a control flag that’s passed in

**Coincidental cohesion**

- Occurs when the operations in a routine have no discernible relationship to each other. 

## Good routine names

A good name for a routine clearly describes everything the routine does

**Describe everything the routine does**

- In the routine's name, describe all the outputs and side effects.

**Avoid meaningless, vague, or wishy-washy verbs**

- Some verbs are elastic, stretched to cover just about any meaning

**Don’t differentiate routine names solely by number**

## Good routine names

**Make names of routines as long as necessary**

- Routines tend to be more complicated than variables (9 to 15 characters), and good names for them tend to be longer

**To name a function, use a description of the return value**

- A function returns a value, name function after for the value it returns

**To name a procedure, use a strong verb followed by an object**

- A procedure with functional cohesion usually performs an operation on an object

**Use opposites precisely**

- Using naming conventions for opposites helps consistency, which helps readability

## How long can a routine be ?

The result has been an interminable debate

The theoretical best maximum length is often described as approximately 50 to 150 lines

A large percentage of routines in object-oriented programs will be accessor routines, which will be very short 

From time to time, a complex algorithm will lead to a longer routine should be allowed to grow organically up to 100–200 lines

None of the studies that reported decreased cost, decreased error rates, or both with larger routines distinguished among sizes larger than 200 lines

## How to use routine parameters

Interfaces between routines are some of the **most error-prone** areas of a program

Studies found that 39 percent of all errors were internal interface errors — errors in communication between routines

Here are a few guidelines for minimising interface problems:

**Put parameters in input-modify-output order**

Instead of ordering parameters randomly or alphabetically, list the parameters: 

1. Input-only
2. Input-and-output
3. Output-only

## How to use routine parameters

**If several routines use similar parameters, put the similar parameters in a consistent order**

- The order of routine parameters can be a mnemonic, and inconsistent order can make parameters hard to remember

**Use all the parameters**

- If you pass a parameter to a routine, use it. If you aren’t using it, remove the parameter from the routine interface

**Put status or error variables last**

- By convention, status variables and variables that indicate an error has occurred go last in the parameter list

## How to use routine parameters

**Don’t use routine parameters as working variables**

- It’s dangerous to use the parameters passed to a routine as working variables

**Document interface assumptions about parameters**

- If you assume the data being passed to your routine has certain characteristics, document the assumptions as you make them

**Limit the number of a routine’s parameters to about seven**

- Seven is a magic number for people’s comprehension

## How to use routine parameters

**Consider an input, modify, and output naming convention for parameters**

- If you find that it’s important to distinguish among input, modify, and output parameters, establish a naming convention that identifies them

**Pass the variables or objects that the routine needs to maintain its interface abstraction**

- There are two competing schools of thought about how to pass members of an object to a routine

**Use named parameters**

- In some languages, you can explicitly associate formal parameters with actual parameters
