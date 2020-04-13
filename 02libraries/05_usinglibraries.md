# Using Libraries

## Using libraries

### Package managers

* Package Manager (Linux / Mac)
    * Precompiled
    * Stable choice
    * Inter-dependencies work
* Linux
    * ```sudo apt-get install```
    * ```sudo yum install```
* Mac    
    * ```sudo port install```
    * ```brew install```
    

### Windows

* Libraries typically:
    * Randomly installed location
    * In system folders
    * In developer folders
    * In build folder
* Please **clean** your machine
* Try **Chocolatey** package manager


### Package managers

* So, if you can **use standard versions** of 3rd party libraries
* Package managers are a **good way** to go
* You just need to **specify what versions** so your collaborator can check


### Problems

As soon as you hit a bug in a library

* How to update ?
* Knock on effects
  * Cascading updates
  * Inconsistent development environment
        

### Build your own

Two basic approaches

* **External / Individual** build
  * Build dependencies externally
  * Point your software at those packages
* **SuperBuild / Meta-Build**
  * Write code to download all dependencies
  * The correct version numbers is stored in code
        

### External / Individual Build

For example

```bash
~/Desktop/ITK-v1
~/Desktop/ITK-v1-build
~/Desktop/VTK-v2
~/Desktop/VTK-v2-build
~/Desktop/MyProject
~/Desktop/MyProject-build
```

We setup ```MyProject-build``` to know the location of ITK and VTK install folder
       

### Meta-Build / Super-Build

For example

```
~/Desktop/MyProject
~/Desktop/MyProject-SuperBuild/ITK/src
~/Desktop/MyProject-SuperBuild/ITK/build
~/Desktop/MyProject-SuperBuild/VTK/src
~/Desktop/MyProject-SuperBuild/VTK/build
~/Desktop/MyProject-SuperBuild/MyProject-build
```

We setup ```MyProject-build``` to know the location of ITK and VTK that **it itself compiled**


### Pro's / Con's

External Build

* Pro's - build each dependency once
* Con's - collaborators will do this inconsistently
* Con's - how to manage multiple versions of all dependencies

Meta Build

* Pro's - all documented, all self-contained, easier to share
* Con's - Slow build? Not a problem if you only run ```make``` in sub-folder ```MyProject-build```
