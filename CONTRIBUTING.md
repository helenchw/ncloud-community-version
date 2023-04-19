# Code Contribution Guidelines

## Compiler version

- gcc 11 or above
- g++ 11 or above, supporting c++17 standard

## Source Code File

### File Naming

- All files are named using 
- Files extensions
  - Header files in C: `.h`
  - Source files in C: `.c`
  - Header files in C++: `.hh`
  - Source files in C++: `.cc`

### File Format

- All header files should be enclosed with `#define` to avoid multiple inclusion. The format of the symbol name should be `__<PATH>_<FILE>__`, e.g., for hello/hello_world.hh,
  
```cpp
#ifndef __HELLO_HELLO_WORLD_HH__
#define __HELLO_HELLO_WORLD_HH__

...


#endif //define __HELLO_HELLO_WORLD_HH__
```

## Code Style Guide

Unless otherwise specified below, we follow the coding style in the guideline -- [Google coding style for C++][google_gpp_code_style].

### Indentation

* Use **4 spaces** for each level of indentation

### Variables and Constants

- For C++ code, use Camel case (e.g., `helloWorld`) to name variables
  - First character of variables must be in lowercase
  - For C code, use underscores to delimit words in the name of variables without using any capital letters (e.g., `hello_world`)
  - For both C++ and C code, use capital letters for the name of constants, and delimit with underscores whenever appropriate (e.g., `HELLO_WORLD`)

### Class
  - Private and protected variables should start with one underscore (e.g., `_helloWorld`)
  - Public variables should NOT start with underscores
  - For functions that are not used by any other classes, always put them in the private section.

### Namespace
  - Avoid `using namespace ...;` (whenever possible)
  - For long namespace, consider defining an alias, e.g., alias `google::cloud::storage` as `gcs`: `namespace gcs = google::cloud::storage;`
    
## Code Documentation

We follow the documentation style in [Doxygen for C and C++ codes][doxygen_c_cpp].
    
For every function, use the following comment style to document its usage, e.g., parameters and return values. Skip fields if they are not used. Make sure all conditions and assumptions of the parameters are described, and the meaning of all possible return values are listed.
    
For every class variable, use the following comment style to document its meaning/purpose.
    
```cpp
class Arithmetics {
public:
    /**
     * (Function Description) Obtain the sum of two variables 
     *
     * @param[in] a
     * @param[in] b
     *
     * @return sum of a and b
     *
     * @remarks 
     * @see difference()
     **/
    int sum(int a, int b);

private:
    int _opCnt; /**< operation count */
};
```

[doxygen_c_cpp]: http://www.doxygen.nl/manual/docblocks.html#cppblock

[google_gpp_code_style]: https://google.github.io/styleguide/cppguide.html
