# Summary

## Summary

### No magic answer

* ```C++``` is trickier than ```MATLAB / Python```
* While package managers make it easier, you still need to understand what you're building


### A Few Good Libraries

Main advice for libraries:

* As few as possible
* As high quality as possible


### Ways to Use

Easiest - header only

* Just include directly in your source code
* Use ```CMake``` ```include_directories()```
* Compile it in

Use packages from package manager

* Use ```CMake``` to ```find_package```
* Set variables to your installed version

Use build system to build everything

* You control ALL flags
* ```CMake``` does ```find_package``` on things you just compiled

### Git submodule anyone?

```git``` submodule

* If all dependencies are ```CMake```'d
* Put each project in a git submodule
* ```CMake``` can configure whole project
* Not really used on this course