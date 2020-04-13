# Choosing Libraries

### Libraries are awesome !

The **strength of a language** lies as much in:

* The **set of libraries** available
* As it does in the **language itself**

A great set of libraries allows for a very **[powerful programming style](<http://github-pages.ucl.ac.uk/rsd-engineeringcourse/ch04packaging/01Libraries.html>)**

* Write **minimal code** yourself
    * Choose the right libraries
    * Plug them together
    * Create impressive results
* Libraries for **efficiency**
    * Not only efficient with your programming time
    * More efficient with computer time
    * Chances are any general algorithm you might want to use has already been programmed better by someone else

### Drawbacks

Sometimes, libraries are not looked after by their creator anymore

Code that is not maintained **rots**:

* It no longer works with later versions of upstream libraries
* It doesn't work on newer platforms or systems
* Features needed now are not added because the field has moved on

To consider:

* When was the last commit ?
* How often are there commits ?
* Is the code on an open version control tool like GitHub ?

Sometimes, libraries are hard to get working:

* Many libraries involve compiled components that can be hard to install

### Contribute! don't duplicate

You have a **duty to the ecosystem** of scholarly software:

* If there's a tool or algorithm you need, find a project which provides it
* If there are features missing, or problems with it, fix them
* Raise a GitHub issue
* Don't create your own


### How to choose a library ?

\begin{center}
\textbf{Software Licenses}
\end{center}

Consider both:

* License for 3rd party code / dependencies
* License for your code when you distribute it


So, even if you aren't distributing code yet, you need to understand the licenses of your dependencies


### Third Party Licenses

**CAVEAT: This is not legal advice. If in doubt, seek your own legal advice**

When you distribute your code, the licenses of **any libraries you use** takes effect. If library has:

* **[MIT](<http://opensource.org/licenses/MIT>)** and **[BSD](<http://opensource.org/licenses/BSD-3-Clause>)** are **permissive**
  * So you can do what you want, including sell it on
* **[Apache](<http://opensource.org/licenses/Apache-2.0>)** handles multiple contributors and patent rights
  * But is basically permissive
* **[GPL](<http://opensource.org/licenses/gpl-license>)** requires you to **open-source** your code
  * Including changes to the library you imported
  * Your work is considered a _derivative work_, so must be shared
* **[LGPL](<http://opensource.org/licenses/lgpl-license>)** for libraries, but use **dynamic** not static linkage
  * If you use static linking its basically as per GPL

Still debate on **[GPL/LGPL and derivative works](<https://lwn.net/Articles/548216/>)**. Only true test is in court


### Choosing a license

**CAVEAT: This is not legal advice. If in doubt, seek your own legal advice.**

* When you plan to distribute code:    
    * Read this **[book](<http://www.oreilly.com/openbook/osfreesoft/book/>)**
    * **[GitHub's advice](<http://choosealicense.com/>)**
    * **[OSI](<http://opensource.org/>)** for choosing your own license
    * **Don't write your own license**, unless you use legal advice.
    * Try to **pick one of the standard ones** for compatibility.

* _Note_: Once a 3rd party has your code under a license agreement, their restrictions are determined by that version of the code.

     
### Choose stability

So, **take care** in your choice of 3rd party library

* Don't want to **redo work later**
* Don't want to **rely too heavily on non-distributable code**
* But if you do, understand what that means


### Are developers reachable?

* Can you find the lead contributor on the internet ?
    * Do they respond when approached ?
        * Emails to developer list
	* Personal emails
	* Tweets
	* Irc/gitter/Slack/matrix
	* Issues raised on GitHub
* Are there contributors other than the lead contributor ?
* Is there discussion of the library on Stack Exchange ?
* Is it on standard package repositories? (`apt/yum/brew`)


### Is code tested ?

* Are there many **unit tests**, do they run, do they pass ?
* Is there an open test dashboard ? (`Travis/Jenkins/CDash`)
* Are there coverage reports ? Benchmarking reports ?
* Does the library depend on other libraries ?
* Are the build tools common ?
* Is there a sensible versioning scheme (_e.g._ **[semantic versioning](<http://www.semver.org/>)**).
* Is there a suitable release schedule ? A changelog ?


### Is library high quality?

Shouldn't need to look excessively closely, but consider

* Documentation
* Number of ToDo's
* Dependencies (recursively)
* Data Structures? How to import/export image
* Can you write a convenient wrapper?
    
    
### Library features

Then look at features

* Manual
* Easy to use


### Summary

In comparison with languages such as ```MATLAB/Python```

* In `C++` prefer few well chosen libraries
* Be aware of their licenses for future distribution
* Keep a log of any changes, patches etc. that you make
* Be able to compile all your own code, including libraries
* Need for a common build environment ?
  * _e.g._ `CMake, Make, Visual Studio`

[Python04Intro]: <http://github-pages.ucl.ac.uk/rsd-engineeringcourse/ch04packaging/01Libraries.html>