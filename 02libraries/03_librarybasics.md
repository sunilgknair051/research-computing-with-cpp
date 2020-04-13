# Library Basics

## Library Basics

### Aim

You need your compiler to find:

* Headers: ```#include```
* Library:
    * Dynamic: ```.dylib, .so, .lib / .dll```
    * Static: ```.a, .lib```


### Linux/Mac

```bash
g++ -c -I/users/me/myproject/include main.cpp
g++ -o main main.o -L/users/me/myproject/lib -lmylib
```

* ```-I``` to specify include folder
* ```-L``` to specify library folder
* ```-l``` to specify the actual library


### Compiler switches

So, that means

* Include directory
    * ```-I /some/directory``` 
* Library directory
    * ```-L /some/directory``` 
* Library
    * ```-l library``` 

Similar concept on Windows, Linux and Mac.


### Check native build platform

Look inside

* Makefile
* Visual Studio options

Basically constructing ```-I```, ```-L```, ```-l``` switches to pass to command line compiler.        


### Windows compiler switches

* Visual Studio (check version)
* Project Properties
    * ```C/C++``` $\Longrightarrow$ Additional Include Directories.
    * Configuration Properties $\Longrightarrow$ Linker $\Longrightarrow$ Additional Library Directories
    * Linker $\Longrightarrow$ Input $\Longrightarrow$ Additional Dependencies.
* Check compile line - its equivalent to Linux/Mac, `-I, -L, -l`


### Location issues

When you use a library:

* Where is it ?
* Header only ?
* System version or your version ?
* What about bugs? How do I upgrade? Do I need to build it myself ?


### Compilation issues

When you use a library:

* Which library version ?
* Which compiler version ?
* Debug or Release ?
* **[Static or Dynamic?][StaticVsDynamic]**
* 32 bit / 64 bit ?
* Platform specific flags ?
* Pre-installed, or did you compile it ?


### A few good libraries

Due to all those issues shown above, again, the main advice for libraries:

* As few as possible
* As good as possible

[StaticVsDynamic]: http://www.learncpp.com/cpp-tutorial/a1-static-and-dynamic-libraries/