# Creating High-Quality Code: Defensive Programming

## The idea behind defensive programming

In defensive programming, the main idea is that if a routine is passed bad data, it won’t be hurt

Even if the bad data is another routine’s fault

More generally, it’s the recognition that programs will have problems and modifications

And that a smart programmer will develop code accordingly

In following are few techniques to protect code from invalid data

## Protecting your program from invalid inputs

**Check the values of all data from external sources**

- When getting data from a file, a user, the network, or some other external interface, check to be sure that the data falls within the allowable range

**Check the values of all routine input parameters**

**Decide how to handle bad inputs** 

- Depending on the situation, you might choose any of a dozen different approaches

## Assertions

An assertion is code that’s used during development that allows a program to check itself as it runs. 

When an assertion is true, that means everything is operating as expected. 

When it’s false, that means it has detected an unexpected error in the code.

**Use assertions for conditions that should never occur**

- Assertions check for conditions that should never occur

**Avoid putting executable code into assertions** 

- Putting code into an assertion raises the possibility that the compiler will eliminate the code when you turn off the assertions

## Assertions

**Use assertions to document and verify preconditions and postconditions** 

- **Preconditions** and **postconditions** are part of an approach to program design and development known as _design by contract_.

_Preconditions_ are the properties that the usere of a routine or class promises will be true before it calls the routine or instantiates the object. 

_Postconditions_ are the properties that the routine or class promises will be true when it concludes executing. 

**For highly robust code, assert and then handle the error anyway**

## Error-Handling techniques

Error-handling code checks for exceptional but anticipated circumstances that need to be handled by the production code. 

Depending on the specific circumstances, you might want:

**To return a neutral value**

- Sometimes the best response to bad data is to continue operating and simply return a value that’s known to be harmless

**To substitute the next piece of valid data**

- When processing a stream of data, some circumstances call for simply returning the next valid data

## Error-Handling techniques

**To return the same answer as the previous time**

**To substitute the closest legal value**

**Log a warning message to a file**

**Return an error code** 

- Report that an error has been detected and trust that some other routine higher up in the calling hierarchy will handle the error

**Call an error-processing routine or object**

**Display an error message**

**Shut down**

## Exceptions

Exceptions are a **specific means** by which code can pass along errors or exceptional events to the code that called it

If code in one routine encounters an unexpected condition that it doesn’t know how to handle, it throws an exception

Exceptions have an attribute in common with inheritance: used judiciously, they can reduce complexity

Used imprudently, they can make code almost impossible to follow

**The overriding benefit of exceptions is their ability to signal error conditions in such a way that they cannot be ignored**

## Summary

- Production code should handle errors in a more sophisticated way than “garbage in, garbage out.”
- Defensive-programming techniques make errors
  - Easier to find
  - Easier to fix
  - Less damaging to production code
- Assertions can help detect errors early
- The decision about how to handle bad inputs is a key error-handling decision and a key high-level design decision
- Exceptions provide a means of handling errors that operates in a different dimension from the normal flow of the code


