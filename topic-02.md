# Topic 2: Variables & Types

C++ is statically typed. Fundamental types include int, char, float, double, bool. sizeof returns byte count. Each type has defined ranges.

## Learn From

Fundamental types references.

- C++ Variables — https://cplusplus.com/doc/tutorial/variables/
- cppreference sizeof — https://en.cppreference.com/w/cpp/language/sizeof

## Key Concepts

- int, char, float, double, bool
- sizeof operator
- Signed vs unsigned
- Type ranges
- Declaration and initialization
- const variables
- auto deduction

## Practice Problems & Solutions

### Problem 1

Declare int x=10 and print.

**Solution:**

```
#include <iostream>
int main(){int x=10;std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 2

Print sizeof(int).

**Solution:**

```
#include <iostream>
int main(){std::cout<<sizeof(int)<<std::endl;return 0;}
```

**Expected output:**

```
4
```

**Learning points:** 

### Problem 3

Print sizeof(double).

**Solution:**

```
#include <iostream>
int main(){std::cout<<sizeof(double)<<std::endl;return 0;}
```

**Expected output:**

```
8
```

**Learning points:** 

### Problem 4

Declare char c='Z' and print.

**Solution:**

```
#include <iostream>
int main(){char c='Z';std::cout<<c<<std::endl;return 0;}
```

**Expected output:**

```
Z
```

**Learning points:** 

### Problem 5

Declare bool b=true and print.

**Solution:**

```
#include <iostream>
int main(){bool b=true;std::cout<<b<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 6

Print sizeof(char).

**Solution:**

```
#include <iostream>
int main(){std::cout<<sizeof(char)<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 7

Declare float f=2.5f and print.

**Solution:**

```
#include <iostream>
int main(){float f=2.5f;std::cout<<f<<std::endl;return 0;}
```

**Expected output:**

```
2.5
```

**Learning points:** 

### Problem 8

Use auto for y=42.

**Solution:**

```
#include <iostream>
int main(){auto y=42;std::cout<<y<<std::endl;return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 9

Declare const int MAX=100 and print.

**Solution:**

```
#include <iostream>
int main(){const int MAX=100;std::cout<<MAX<<std::endl;return 0;}
```

**Expected output:**

```
100
```

**Learning points:** 

### Problem 10

Print sizeof(long long).

**Solution:**

```
#include <iostream>
int main(){std::cout<<sizeof(long long)<<std::endl;return 0;}
```

**Expected output:**

```
8
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** sizeof int?

**A:** 4 bytes.

**Q2:** signed vs unsigned?

**A:** Signed holds negatives; unsigned larger positive range.

**Q3:** signed char range?

**A:** -128 to 127.

**Q4:** auto keyword?

**A:** Deduces type from initializer.

**Q5:** const purpose?

**A:** Makes variable read-only.

**Q6:** unsigned int max 32-bit?

**A:** 4294967295.

**Q7:** float literal to double?

**A:** Yes, implicit conversion.

**Q8:** 3.14 vs 3.14f?

**A:** 3.14 is double; 3.14f is float.

**Q9:** INT_MIN/INT_MAX header?

**A:** <climits>.

**Q10:** Overflow signed int?

**A:** Undefined behavior.
