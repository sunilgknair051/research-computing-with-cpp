# Useful Tools: Valgrind

## Memory leaks

**Checking memory allocation intrusively**

There are a variety of compiler flags to check standard memory errors:

- g++: `-fsanitize=address`
- clang: **[address sanitizer](https://clang.llvm.org/docs/AddressSanitizer.html)**

Good when debugging/testing, but may impact performance. May not detect all
memory errors (e.g. read before initialization).

**Checking memory allocation non-intrusively**

**[Valgrind](http://valgrind.org/)** is an instrumentation framework for Linux and (older) Mac.

It detects memory errors and leaks by intercepting every memory access,
allocation, and deallocation.

Unfortunately, Valgrind currently does not work with Mac OS/X > 10.11.

So let's use docker (on Linux) and docker-machine (Windows, Mac OS/X)!

## Homework 25: Traveling salesman solved by Simulated Annealing

Traveling Salesman Problem:

   A salesman living in an n-dimensional world must visit N cities. What is the
   shortest path?

Simulated Annealing:

- Start from a candidate A
- Create a neighbor B of A
- if `path(A) > path(B)`, then swap A and B
- else if `exp(beta * (path(B) - path(A))) > random()`, then swap A and B
- loop until satisfied

## Homework 25: Setting up 

First update and download all softwares:

```sh
sudo apt-get update && \ 
sudo apt-get install -y cmake g++ valgrind
git clone \ 
https://github.com/UCL-RITS/research-computing-with-cpp
cd /path/to/research-computing-with-cpp/95CodeQuality/cpp
```

Finally:

1. Create a build directory in the source code directory
1. Run `cmake` from the build directory
1. Run `make` in the build directory

Maybe you should:

1. Set the `CMakeLists.txt` to find `Eigen`

## Running valgrind on program called `awful`

Assuming everything went well, there should be a compiled program called awful.

It has memory leaks and bugs. Investigate and correct using valgrind:

```sh
> valgrind -v --leak-check=full --show-leak-kinds=all   \
                --track-origin=yes ./awful
```

## Running valgrind on program called `less_bad`

Even programs written without explicit memory allocations can have memory bugs.

The next version uses Eigen to solve the same problem.

1. Run valgrind on `less_bad`
1. Investigate and correct the code

