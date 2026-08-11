# Topic 1: Setup & First Program

C++ is a compiled language requiring a compiler. g++ is the common free compiler. Every program starts with main(). Use #include for headers and std::cout for output.

## Learn From

Beginner tutorials for C++ setup.

- GCC — https://gcc.gnu.org/
- C++ Reference — https://cplusplus.com/reference/iostream/
- LearnCpp — https://www.learncpp.com/

## Key Concepts

- g++ compiler
- #include <iostream>
- int main()
- std::cout <<
- std::endl
- Compiling with g++
- Return values from main()

## Practice Problems & Solutions

### Problem 1

Print 'Hello, World!'.

```
#include <iostream>
int main(){std::cout<<"Hello, World!"<<std::endl;return 0;}
```

**Expected output:**

```
Hello, World!
```

**Learning points:** 

### Problem 2

Print your name.

```
#include <iostream>
int main(){std::cout<<"BlasterX24"<<std::endl;return 0;}
```

**Expected output:**

```
BlasterX24
```

**Learning points:** 

### Problem 3

Print two lines.

```
#include <iostream>
int main(){std::cout<<"Line 1"<<std::endl;std::cout<<"Line 2"<<std::endl;return 0;}
```

**Expected output:**

```
Line 1
Line 2
```

**Learning points:** 

### Problem 4

Print 7+3.

```
#include <iostream>
int main(){std::cout<<7+3<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 5

Print A B C on separate lines.

```
#include <iostream>
int main(){std::cout<<'A'<<std::endl;std::cout<<'B'<<std::endl;std::cout<<'C'<<std::endl;return 0;}
```

**Expected output:**

```
A
B
C
```

**Learning points:** 

### Problem 6

Return 42 from main().

```
#include <iostream>
int main(){return 42;}
```

**Learning points:** 

### Problem 7

Print 'C++ C++ C++'.

```
#include <iostream>
int main(){std::cout<<"C++ C++ C++"<<std::endl;return 0;}
```

**Expected output:**

```
C++ C++ C++
```

**Learning points:** 

### Problem 8

Print character 'x'.

```
#include <iostream>
int main(){std::cout<<'x'<<std::endl;return 0;}
```

**Expected output:**

```
x
```

**Learning points:** 

### Problem 9

Print 'Start, End'.

```
#include <iostream>
int main(){std::cout<<"Start, End"<<std::endl;return 0;}
```

**Expected output:**

```
Start, End
```

**Learning points:** 

### Problem 10

Print 3.14.

```
#include <iostream>
int main(){std::cout<<3.14<<std::endl;return 0;}
```

**Expected output:**

```
3.14
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Compiler command for main.cpp to app?

**A:** g++ main.cpp -o app

**Q2:** Header for std::cout?

**A:** #include <iostream>

**Q3:** Return type of main()?

**A:** int

**Q4:** What does std::endl do?

**A:** Prints newline and flushes buffer.

**Q5:** Entry point of C++ program?

**A:** main() function.

**Q6:** Multiple main() allowed?

**A:** No, only one.

**Q7:** return 0 signifies?

**A:** Successful execution.

**Q8:** \n vs std::endl?

**A:** \n is newline only; endl flushes too.

**Q9:** cout namespace?

**A:** std namespace.

**Q10:** C++17 flag?

**A:** -std=c++17
