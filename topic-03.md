# Topic 3: Operators & Expressions

Operators perform operations on operands. Includes arithmetic (+,-,*,/,%), comparison (==,!=,<,>), logical (&&,||,!), bitwise (&,|,^,~,<<,>>), and ternary (?:).

## Learn From

Operators references.

- C++ Operators — https://cplusplus.com/doc/tutorial/operators/
- cppreference Operators — https://en.cppreference.com/w/cpp/language/operator

## Key Concepts

- Arithmetic operators
- Comparison operators
- Logical operators
- Bitwise operators
- Ternary operator
- Operator precedence
- Type promotion

## Practice Problems & Solutions

### Problem 1

Print 15/4 integer division.

```
#include <iostream>
int main(){std::cout<<15/4<<std::endl;return 0;}
```

**Expected output:**

```
3
```

**Learning points:** 

### Problem 2

Print 17%5.

```
#include <iostream>
int main(){std::cout<<17%5<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 3

Print (5>3).

```
#include <iostream>
int main(){std::cout<<(5>3)<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 4

Print 3+4*2.

```
#include <iostream>
int main(){std::cout<<3+4*2<<std::endl;return 0;}
```

**Expected output:**

```
11
```

**Learning points:** 

### Problem 5

Ternary max of 10,20.

```
#include <iostream>
int main(){int a=10,b=20;std::cout<<(a>b?a:b)<<std::endl;return 0;}
```

**Expected output:**

```
20
```

**Learning points:** 

### Problem 6

Print 6&3.

```
#include <iostream>
int main(){std::cout<<(6&3)<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 7

Print 1<<3.

```
#include <iostream>
int main(){std::cout<<(1<<3)<<std::endl;return 0;}
```

**Expected output:**

```
8
```

**Learning points:** 

### Problem 8

Print (5>3&&10>7).

```
#include <iostream>
int main(){std::cout<<(5>3&&10>7)<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 9

Print 10/3.0.

```
#include <iostream>
int main(){std::cout<<10/3.0<<std::endl;return 0;}
```

**Expected output:**

```
3.33333
```

**Learning points:** 

### Problem 10

Print 5^3.

```
#include <iostream>
int main(){std::cout<<(5^3)<<std::endl;return 0;}
```

**Expected output:**

```
6
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Operator precedence?

**A:** Rules for evaluation order.

**Q2:** 10/3 in C++?

**A:** 3 (truncates).

**Q3:** % operator?

**A:** Remainder of division.

**Q4:** Ternary operator?

**A:** condition?a:b.

**Q5:** Type promotion?

**A:** Implicit smaller to larger type.

**Q6:** << bitwise?

**A:** Left shift.

**Q7:** !0 result?

**A:** 1 (true).

**Q8:** Short-circuit evaluation?

**A:** Right not evaluated if left determines result.

**Q9:** ~ operator?

**A:** Bitwise NOT.

**Q10:** == vs =?

**A:** == compares; = assigns.
