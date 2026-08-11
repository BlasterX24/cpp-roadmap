# Topic 21: Preprocessor

Preprocessor runs before compilation. #define creates macros. #include imports headers. Conditional compilation enables platform-specific code.

## Learn From

Preprocessor references.

- C++ Preprocessor — https://cplusplus.com/doc/tutorial/preprocessor/

## Key Concepts

- #define macros
- #include headers
- #ifdef/#ifndef/#endif
- #pragma directives
- Macro functions
- Include guards
- # and ## operators

## Practice Problems & Solutions

### Problem 1

#define constant.

```
#include <iostream>
#define MAX 100
int main(){std::cout<<MAX<<std::endl;return 0;}
```

**Expected output:**

```
100
```

**Learning points:** 

### Problem 2

#define macro function.

```
#include <iostream>
#define SQUARE(x) ((x)*(x))
int main(){std::cout<<SQUARE(5)<<std::endl;return 0;}
```

**Expected output:**

```
25
```

**Learning points:** 

### Problem 3

#ifdef conditional.

```
#include <iostream>
#define DEBUG
int main(){#ifdef DEBUG
std::cout<<"debug"<<std::endl;#endif
return 0;}
```

**Expected output:**

```
debug
```

**Learning points:** 

### Problem 4

Include guard.

```
#include <iostream>
#ifndef MYHEADER_H
#define MYHEADER_H
int getValue(){return 42;}
#endif
int main(){std::cout<<getValue()<<std::endl;return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 5

#undef.

```
#include <iostream>
#define TEMP 10
#undef TEMP
int main(){std::cout<<"undef"<<std::endl;return 0;}
```

**Expected output:**

```
undef
```

**Learning points:** 

### Problem 6

#pragma once.

```
#pragma once
#include <iostream>
int main(){std::cout<<"pragma"<<std::endl;return 0;}
```

**Expected output:**

```
pragma
```

**Learning points:** 

### Problem 7

Token pasting ##.

```
#include <iostream>
#define MAKE_VAR(x) var_##x
int main(){int MAKE_VAR(1)=10;std::cout<<var_1<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 8

Stringize #.

```
#include <iostream>
#define STR(x) #x
int main(){std::cout<<STR(Hello)<<std::endl;return 0;}
```

**Expected output:**

```
Hello
```

**Learning points:** 

### Problem 9

Platform conditional.

```
#include <iostream>
#ifdef _WIN32
#define PLATFORM "Windows"
#else
#define PLATFORM "Other"
#endif
int main(){std::cout<<PLATFORM<<std::endl;return 0;}
```

**Expected output:**

```
Other
```

**Learning points:** 

### Problem 10

Nested ifdef.

```
#include <iostream>
#define A
#define B
int main(){#if defined(A)&&defined(B)
std::cout<<"both"<<std::endl;#endif
return 0;}
```

**Expected output:**

```
both
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** #define?

**A:** Creates macros/constants.

**Q2:** Preprocessor?

**A:** Runs before compilation.

**Q3:** #ifdef?

**A:** Check if defined.

**Q4:** #ifndef?

**A:** Check if not defined.

**Q5:** Include guards?

**A:** Prevent multiple inclusion.

**Q6:** #pragma?

**A:** Compiler-specific directives.

**Q7:** ##?

**A:** Token pasting.

**Q8:** #?

**A:** Stringize to string.

**Q9:** #undef?

**A:** Undefines macro.

**Q10:** When preprocessor runs?

**A:** Before compilation.
