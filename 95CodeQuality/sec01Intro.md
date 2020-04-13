# Code Quality

## Characteristics of software quality

Software has both **quality characteristics**:

**External**

- Characteristics that a **user** of the software product care about
  - Ease of use or correctness
  - Not whether it is easily modifiable, readable or well structured
- **Programmers** do care about !

**Internal**

- Characteristics that a **programmer** of the software product care about

## External characteristics - 1

**Correctness**

- The degree to which a system is **free from faults**
  - In all specification, design, and implementation

**Usability**

- The ease with which users can **learn and uptake** a system

**Efficiency**

- **Minimal use of system resources**, _i.e._ memory and execution time

**Reliability**

- The ability to **perform its required functions under stated conditions**
  
## External characteristics - 2
  
**Integrity**

- Prevention of unauthorised or improper access to
  - Functionalities and data

**Adaptability**

- The ability to be used in other applications or environments

**Accuracy**

- The degree to which a system, as built, is **free from error**
  - $\neq$ correctness; it is a determination of how well a system performs

**Robustness**

- Continues to function in the presence of invalid inputs or stressful environmental conditions

## Internal characteristics - 1
 
**Maintainability**

- The ease to modify, change, improve or correct a software system

**Flexibility** 

- The extent to modify a system for uses in other environments

**Portability** 

- The ease to modify a system to operate in other environments

**Reusability** 

- The extent to which and the ease with which you can use parts of a system in other systems

## Internal characteristics - 2

**Readability**

- The ease with which you can read and understand the source code of a system

**Testability**

- The degree to which you can unit-test and system-test a system to verify that it meets its requirements

**Understandability**

- The ease with which you can comprehend the whole coherence of a system at both the system-organisational and detailed-statement levels

## Which ones to emphasize ?

Quality characteristics **overlap**, but each have different meanings

Internal _vs._ External characteristics **difference isn’t completely clear-cut**

At some level, internal characteristics affect external ones

For instance:

- Software that isn’t internally understandable or maintainable impairs defects correction
  - Affects the external characteristics of correctness and reliability
- Software that isn’t flexible can’t be enhanced to user requests
  - Affects the external characteristic of usability

## Make an optimal decision for your project

Some quality characteristics are emphasized to make life easier for:

- The user 
- The programmer

Try to know which is which and when and how these characteristics interact

The attempt to **maximize** certain characteristics inevitably **conflicts** with the attempt to maximize others

Finding an **optimal solution** from a set of competing objectives is one activity that makes software development a true engineering discipline
