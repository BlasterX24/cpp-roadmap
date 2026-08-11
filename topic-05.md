# Topic 5: Functions

Functions are reusable code blocks. C++ supports overloading, pass by value/reference, and inline hint. Functions organize code and reduce duplication.

## Learn From

Function references.

- C++ Functions — https://cplusplus.com/doc/tutorial/functions/

## Key Concepts

- Declaration vs definition
- Parameters vs arguments
- Return types
- Pass by value vs reference
- Function overloading
- Inline functions
- Default parameters
- Variable scope

## Practice Problems & Solutions

### Problem 1

Function double int value.

```
#include <iostream>
double doubleValue(int x){return x*2.0;}
int main(){std::cout<<doubleValue(5)<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 2

Function sum two ints.

```
#include <iostream>
int add(int a,int b){return a+b;}
int main(){std::cout<<add(3,7)<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 3

Function double by reference.

```
#include <iostream>
void doubleRef(int &x){x*=2;}
int main(){int a=5;doubleRef(a);std::cout<<a<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 4

Overloaded max for int and double.

```
#include <iostream>
int max(int a,int b){return a>b?a:b;}
double max(double a,double b){return a>b?a:b;}
int main(){std::cout<<max(3,7)<<std::endl;std::cout<<max(2.5,1.5)<<std::endl;return 0;}
```

**Expected output:**

```
7
2.5
```

**Learning points:** 

### Problem 5

Default parameter greeting.

```
#include <iostream>
#include <string>
void greet(std::string name="World"){std::cout<<"Hello, "<<name<<std::endl;}
int main(){greet();return 0;}
```

**Expected output:**

```
Hello, World
```

**Learning points:** 

### Problem 6

Function return larger of two.

```
#include <iostream>
int maximum(int a,int b){return (a>b)?a:b;}
int main(){std::cout<<maximum(10,20)<<std::endl;return 0;}
```

**Expected output:**

```
20
```

**Learning points:** 

### Problem 7

Function sum array.

```
#include <iostream>
int sumArray(int arr[],int size){int s=0;for(int i=0;i<size;i++)s+=arr[i];return s;}
int main(){int arr[]={1,2,3};std::cout<<sumArray(arr,3)<<std::endl;return 0;}
```

**Expected output:**

```
6
```

**Learning points:** 

### Problem 8

Function swap by reference.

```
#include <iostream>
void swapVals(int &a,int &b){int temp=a;a=b;b=temp;}
int main(){int x=1,y=2;swapVals(x,y);std::cout<<x<<" "<<y<<std::endl;return 0;}
```

**Expected output:**

```
2 1
```

**Learning points:** 

### Problem 9

Inline square function.

```
#include <iostream>
inline int square(int x){return x*x;}
int main(){std::cout<<square(4)<<std::endl;return 0;}
```

**Expected output:**

```
16
```

**Learning points:** 

### Problem 10

Recursive factorial(5).

```
#include <iostream>
int factorial(int n){if(n<=1)return 1;return n*factorial(n-1);}
int main(){std::cout<<factorial(5)<<std::endl;return 0;}
```

**Expected output:**

```
120
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Declaration vs definition?

**A:** Declaration tells signature; definition provides code.

**Q2:** Pass by reference?

**A:** Pass address to modify original.

**Q3:** Function overloading?

**A:** Same name, different parameter lists.

**Q4:** Inline suggestion?

**A:** Insert body at call site.

**Q5:** Return reference?

**A:** Yes but not to local.

**Q6:** Default parameters?

**A:** Take default if no arg.

**Q7:** Non-void no return?

**A:** Undefined behavior.

**Q8:** Recursion?

**A:** Function calling itself with base case.

**Q9:** Function pointer?

**A:** Stores function address.

**Q10:** Overload by return type?

**A:** No, params must differ.
