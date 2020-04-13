# Eigen

## Using Eigen

### Introduction

**[Eigen][EigenHome]** is:

* ```C++``` template library,
* Linear algebra, matrices, vectors, numerical solvers, etc.


### Tutorials

Obviously, you can read:

* The existing **[manual pages][EigenManual]**
* Tutorials (**[short][EigenShort], [long][EigenLong]**)
* The **[Quick Reference][EigenRef]**


### Getting started

* Header only, just need ```#include```
* Uses ```CMake```, but that's just for
    * Documentation
    * Run unit tests
    * Installation


### ```C++``` Principles

(_i.e._ why introduce ```Eigen``` on this course)

```Eigen``` uses

* Templates
* Loop unrolling, traits, template meta-programming


### Matrix class

:::::::::::::: {.columns}
::: {.column width="40%"}
This:

```cpp
#include <iostream>
#include <Eigen/Dense>
using Eigen::MatrixXd;
int main()
{
  MatrixXd m(2,2);
  m(0,0) = 3;
  m(1,0) = 2.5;
  m(0,1) = -1;
  m(1,1) = m(1,0) + m(0,1);
  std::cout << m << std::endl;
}
```

:::
::: {.column width="60%"}
Produces:

```cpp
  3 -1
2.5 1.5
```
:::
::::::::::::::

### Matrix class declaration

Matrix class is templated, **[so review last weeks lecture][Lecture2]**

```cpp
template< typename _Scalar, int _Rows, int _Cols,
          int _Options, int _MaxRows, int _MaxCols >
class Matrix
  : public PlainObjectBase<Matrix <_Scalar, _Rows,
                                   _Cols, _Options,
                                   _MaxRows, _MaxCols> >
{

}
```

### ```Eigen``` Matrix Summary

* Templated type supports dynamic and fixed arrays
  * Seamlessly on stack or heap
* Typedef to make life easier: ```Matrix3d``` = 3 by 3 of double
* Uses TMP to generate generate code at compile time
* Benefit from optimisations such as loop unrolling when using fixed size constant arrays


### ```Eigen``` Usage - CMake Include

* Need to set include path
* You could download and 'install' Eigen into your project, and commit it
* For instance

``` cmake
include_directories(
${CMAKE_SOURCE_DIR}/session03/cpp/Eigen/eigen-3.2.3/include/eigen3
)
```


### ```Eigen``` Usage - CMake Module

* ```CMake``` (3.1) does not have a ```Find Module``` for eigen, but eigen provides one.
* So, in your source tree

``` bash
mkdir CMake
cp <path_to_eigen>/cmake/FindEigen3.cmake ./CMake
```

* Then in your CMakeLists.txt

``` cmake
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/CMake;
${CMAKE_MODULE_PATH}")
find_package(Eigen3)
include_directories(${EIGEN3_INCLUDE_DIR})
```

### ```Eigen``` Summary

* Header only
* Use ```CMake``` to set the include path
* Templated, so its compiled in, no link or run-time dependencies
* Simple to use linear algebra library
* Advise not to mix with GUI code
* Consider static linking as using templates anyway - ease of distribution


[EigenHome]: http://eigen.tuxfamily.org
[EigenManual]: http://eigen.tuxfamily.org/dox/index.html
[EigenShort]: http://eigen.tuxfamily.org/dox/GettingStarted.html
[EigenLong]: http://eigen.tuxfamily.org/dox/group__TutorialMatrixClass.html
[EigenRef]: http://eigen.tuxfamily.org/dox/group__QuickRefPage.html
[Lecture2]: http://development.rc.ucl.ac.uk/training/rcwithcpp/session02/
[NiftySeg]: http://sourceforge.net/projects/niftyseg/
[PCL]: http://pointclouds.org/
[Arun]: http://dl.acm.org/citation.cfm?id=28821
