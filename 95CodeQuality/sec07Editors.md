# Useful Tools: Editors

## Auto-formatting

The end of brace wars: brainless auto-formatting

Code is read more often than written.

Most IDEs (Emacs, Sublime, Eclipse ...) have got a `C++` mode that helps pointing out badly formatted code.

From the command line, **[clang-format](https://clang.llvm.org/docs/ClangFormat.html)** is one possible
code formatter. Add it (or any equivalent) to your editor for automatic formating.
  
## How auto-formatting works ?

Let's assume I have in `test.cpp`

``` cpp
int GCD(int a,int b)
{int r;while(b){r=a%b;
a=b;b=r;}return a;}
```

Then, running `clang-format test.cpp` produces:

```cpp
int GCD(int a, int b) {
  int r;
  while (b) {
    r = a % b;
    a = b;
    b = r;
  }
  return a;
}
```


## Linting

Software to check code for correctness:

- The compilers themselves _i.e._ turning on warning flags `-Wall`
- **[clang-tidy](http://clang.llvm.org/extra/clang-tidy/)**
- **[cppcheck](http://cppcheck.sourceforge.net/)**

  example:

``` cpp
if(FFTW_plan_flag != FFTW_ESTIMATE | FFTW_PRESERVE_INPUT) {
...
}
```

## Refactoring

Once tests exist, it is easy and safe to modify the code:

Refactoring means make atomic rewrites:

- To simplify existing code
- To simplify future development
- For legibility
- To decrease tech-debt
- To consolidate similar code (avoid copy-pasta)
