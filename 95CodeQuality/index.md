---
title: Code Quality and Tools
---


## All tests pass, the code works, are we done yet ?

Lots of changes can be made to a code, from cosmetic to crucial:

- Formatting (layout)
- Linting (style checking)
- Refactoring (atomic enhancements)
- Checking for memory leaks
- Profiling and performance
- Benchmarking

## Beware of tests only

Far too often, software quality reduces to **testing**

Developers on many projects rely on testing as the primary method of both:

- Quality assessment
- Quality improvement

Testing by itself is not **optimally effective at removing errors**

## General principle

The General Principle of Software Quality is that 

\begin{center}
\textbf{Improving quality reduces development costs}
\end{center}
 
 
Understanding this principle depends on understanding a key observation: 

\begin{center}
\textbf{\textit{The best way to improve productivity and quality is to reduce the time spent reworking code}}
\end{center}

Whether the rework arises from changes in:

- Requirements
- Design
- Debugging

Rework (_i.e._ debugging and refactoring) consume about **50\% of the time**

## Software quality programme


The key idea is to **redistribute resources** away from debugging and refactoring into **upstream quality-assurance activities** (prerequisites)

- Problem definition
- Requirements
- Architecture

Upstream activities have **more leverage on product quality** than downstream activities

So the time you invest upstream saves more time downstream

The net effect is **fewer defects, shorter development time, and lower costs**

## Aim of the chapter - 1

Top level picture

- **Define code quality**
  - **External** _vs._ **Internal** characteristics
  - Make an optimal choice

- **Techniques for improving software quality**

- **Creating high-quality code**
  - Design in construction
  - Working classes
  - High-quality routines
  - Defensive programming
  - Documenting
  
## Aim of the chapter - 2

Practical hands-on

- **Introduce few useful tools**
  - Editors for formatting, linting and refactoring
  - Valgrind for memory leaks
  - Profiling for performance
  - Benchmarking


