# CMakeCatch2

## CMakeCatch2

### Intro 

* Demo project on **[GitHub](https://github.com)**: **[CMakeCatch2](<https://github.com/MattClarkson/CMakeCatch2>)**
* No functional code, other than adding 2 numbers
* Sets up ```Eigen``` and ```Catch```, header only, checked into project


### Homework - 21 - Manual linking

* Download ```CMakeCatch2```
* Practice manually compiling ```CMakeCatch2``` project
  * Find and compile ```mpMyFirstApp.cpp``` with ```-c```
  * Check that compilation fails
  * Link to ```Eigen``` in the ```3rdParty``` folder with ```-I```
  * Link to the exceptions header files in ```Lib``` with ```-I``` 
  * Enforce ```C++11``` standard
  * Suppress warnings
  * It should still fail as there is no linking to the implementation
  * Create a static library from the ```mpException.cpp mpBasicTypes.cpp mpMyFunctions.cpp``` files
    * Create ```.o``` files for each of them
    * Bundle them into ```libmyproject.a``` file using ```ar rcs``` command
  * Generate an executable by linking with ```-L``` and ```-l```
  
   
### Homework - 22 - Using ```CMake```

* Download ```CMakeCatch2```
* Practice compiling ```CMakeCatch2```
  * Develop a rudimentary ```CMakeLists.txt``` based on the existing one
  * Replace the ```-I, -L, -l``` switches with ```CMake``` functionality
  * Link to ```Eigen``` in the ```3rdParty``` folder
  
### Homework - 23 - Optional

  
* Choose a another project relevant to you
  * _e.g._ glog/gflags/VTK/OpenCV
* Compile it in a separate folder, as per their build instructions
* Modify some ```C++``` in ```CMakeCatch2```, recompile
* Try to include external library
  * _e.g._ glog/gflags/VTK/OpenCV and call a simple function
  * See example for Eigen, in **[Command Line App](<https://github.com/MattClarkson/CMakeCatch2/blob/master/Code/CommandLineApps/mpMyFirstApp.cpp>)**
  
### Homework - 24 - Optional 1/2

* Demo project on **[GitHub](<https://github.com>)**: **[CMakeCatchTemplate](<https://github.com/MattClarkson/CMakeCatchTemplate>)**
* No functional code, other than adding 2 numbers
* Basically shows how to use **CMake**, via various examples.


SuperBuild

* See flag: ```BUILD_SUPERBUILD:BOOL=[ON|OFF]```
* If ```OFF```
    * Just compiles *this* project in current folder
* If ```ON```
    * Dependencies in current folder
    * Compiles *this* project in sub-folder
	

### Homework - 24 - Optional 2/2

Setup folders like:

```bash
# Source folder
/User/me/build/CMakeCatchTemplate

# SuperBuild folder
/User/me/build/CMakeCatchTemplate-SuperBuild
```

* Ensure ```BUILD_SUPERBUILD=ON```
* Try turning a small library like ```BUILD_gflags``` to **ON**
* Run the build in the ```SuperBuild``` folder
* Look on disk, see how the dependencies are compiled in the ```CMakeCatchTemplate-SuperBuild``` folder.
* Then look in sub-folder ```MYPROJECT-build``` to see how this project is build, using the dependencies in the folder above.
