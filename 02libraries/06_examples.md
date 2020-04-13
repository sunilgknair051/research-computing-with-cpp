# Examples

## Examples


### Reminder

Fundamentally, we need

* Access to **header files** - _declaration_
* Access to **compiled code** - _definition_ or _implementation_


### Header only?

After all these considerations:

* Static / Dynamic
* Package Managers / Build your own
* External build / Internal Build
* Release / Debug
* ```-I, -L, -l```

Header only libraries are very attractive !

\begin{center}
\textbf{CMake} can help !
\end{center}

### ```CMake``` - Example

An example in project **[CMakeCatch2](<https://github.com/MattClarkson/CMakeCatch2>)** `catch.hpp`

From ```CMakeCatch2/CMakeLists.txt```

```cmake
include_directories(${CMAKE_SOURCE_DIR}/Code/)
add_subdirectory(Code)
if(BUILD_TESTING)
  include_directories(${CMAKE_SOURCE_DIR}/Testing/)
  add_subdirectory(Testing)
endif()
```


### ```CMake``` - Header only

For example:

```bash
CMakeCatchTemplate/3rdParty/libraryA/version1/Class1.hpp
CMakeCatchTemplate/3rdParty/libraryA/version1/Class2.hpp
```

Add path to ```CMakeLists.txt```

```cmake
include_directories(
${CMAKE_SOURCE_DIR}/3rdParty/libraryA/version1/
)
```

You would have audit trail (_e.g._ via git repo) of when updates to library were made


### ```CMake``` - Header only, external

If you think library is too large

```bash
C:\3rdParty\Eigen
C:\build\MyProject
C:\build\MyProject-build
```

Add to ```CMakeLists.txt```

```cmake
include_directories(
"~/Desktop/3rdParty/Eigen/install/include/eigen3"
)
```

* Hard-coded, but usable if you write detailed build instructions
* Not very **platform independent**
* Not very **flexible**


### ```CMake``` - ```find_package```

In general, in ```CMake```, each dependency requires
a bit of code to look up include directories, and libraries.

```cmake
  find_package(OpenCV REQUIRED)
  include_directories(${OpenCV_INCLUDE_DIRS})
  list(APPEND ALL_THIRD_PARTY_LIBRARIES ${OpenCV_LIBS})
  add_definitions(-DBUILD_OpenCV)
```

So a 3rd party package can provide information on how you should use it


### Types of ```find_package```

```find_package``` has several different modes:

* *config* mode: Use 3rd party projects own **config**
  * _e.g._ ```VTKConfig.cmake```
* *module* mode: Use a ```FindModule```, some come with ```CMake```
* *module* mode: Write your own ```FindModule```
* *module* mode: Write your own ```FindModule``` 
  * With generated / substituted variables


### ```find_package``` - refer to docs

A Basic Example (for a full example - see **[docs](<https://cmake.org/cmake/help/latest/command/find_package.html>)**)

Given:

```cmake
  find_package(SomeLibrary [REQUIRED])
```

```CMake``` will search 

* All directories in **CMAKE_MODULE_PATH**
* For **SomeLibraryConfig.cmake** - does *config* mode
* For **FindSomeLibrary.cmake** - does *module* mode
* Case sensitive 
    
    
### ```find_package``` - Result

* ```find_package(SomeLibrary)``` should return 
  * **SomeLibrary_FOUND:BOOL=TRUE** if library was found
* Sets any other variables necessary to use the library
* Check **CMakeCache.txt** to see result


### ```find_package``` - Usage

* So many 3rd party libraries are ```CMake``` ready.
* If things go wrong, you can debug it - ```CMake``` is all text based


### ```find_package``` - Fixing

* You can provide patched versions
* Add your source/build folder to the **CMAKE_MODULE_PATH**

```cmake
set(CMAKE_MODULE_PATH
    ${CMAKE_SOURCE_DIR}/CMake
    ${CMAKE_BINARY_DIR}
    ${CMAKE_MODULE_PATH}
   )
```
* So ```CMake``` will find your version before the system versions


### ```find_package``` - Tailoring

You can write your own

* _e.g._ **FindEigen** in **[CMakeCatchTemplate](<https://github.com/MattClarkson/CMakeCatchTemplate/blob/master/CMake/FindEigen.cmake>)**

Use **CMake** to substitute variables

* Force include / library directories
* Useful for vendors API that isn't ```CMake``` compatible
* Useful for meta-build
* Force directories to match the package you just compiled


### Provide build flags

If a package is found, you can add compiler flag

```cmake
add_definitions(-DBUILD_OpenCV)
```

So, you can optionally include things:

```cpp
#ifdef BUILD_OpenCV
#include <cv.h>
#endif
```

* Best not to do too much of this
* Useful to provide build options, _e.g._ for running on clusters


### Check before committing

Before you commit code to git, make sure you are compiling what you think you are !

```cpp
#ifdef BUILD_OpenCV
blah blah
#include <cv.h>
#endif
```

should fail compilation


### Summary

Basic aim:

* ```include_directories()``` generates ```-I```
* ```link_directories()``` generates ```-L```
* ```target_link_libraries(mylibrary PRIVATE ${libs})``` generates ```-l``` for each library
* Might not need ```link_directories()``` if libraries fully qualified
* Try default ```CMake``` ```find_package```
* Or write your own and add location to **CMAKE_MODULE_PATH**
