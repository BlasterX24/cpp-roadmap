# Topic 7: Pointers & References

Pointers store memory addresses. * dereferences; & takes address. Pointer arithmetic traverses arrays. nullptr is modern null. void* is generic pointer.

## Learn From

Pointer references.

- C++ Pointers — https://cplusplus.com/doc/tutorial/pointers/

## Key Concepts

- Pointer declaration
- Dereferencing *
- Address-of &
- Pointer arithmetic
- nullptr
- void* pointer
- const pointers
- References vs pointers

## Practice Problems & Solutions

### Problem 1

Dereference pointer to print.

```
#include <iostream>
int main(){int x=10;int *p=&x;std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 2

Pointer modifies x 5 to 20.

```
#include <iostream>
int main(){int x=5;int *p=&x;*p=20;std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
20
```

**Learning points:** 

### Problem 3

Print address of variable.

```
#include <iostream>
int main(){int x=42;std::cout<<&x<<std::endl;return 0;}
```

**Expected output:**

```
0x
```

**Learning points:** 

### Problem 4

Pointer arithmetic traverse array.

```
#include <iostream>
int main(){int arr[]={10,20,30};int *p=arr;for(int i=0;i<3;i++)std::cout<<*(p+i)<<std::endl;return 0;}
```

**Expected output:**

```
10
20
30
```

**Learning points:** 

### Problem 5

nullptr check.

```
#include <iostream>
int main(){int *p=nullptr;if(p==nullptr)std::cout<<"null"<<std::endl;return 0;}
```

**Expected output:**

```
null
```

**Learning points:** 

### Problem 6

Reference modifies variable.

```
#include <iostream>
int main(){int x=5;int &ref=x;ref=15;std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
15
```

**Learning points:** 

### Problem 7

Const pointer.

```
#include <iostream>
int main(){int x=10;int *const p=&x;std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 8

Void* points to double.

```
#include <iostream>
int main(){double d=3.14;void *vp=&d;std::cout<<*(double*)vp<<std::endl;return 0;}
```

**Expected output:**

```
3.14
```

**Learning points:** 

### Problem 9

Pointer difference.

```
#include <iostream>
int main(){int arr[]={10,20,30,40};int *p1=&arr[0];int *p2=&arr[3];std::cout<<p2-p1<<std::endl;return 0;}
```

**Expected output:**

```
3
```

**Learning points:** 

### Problem 10

Swap with pointers.

```
#include <iostream>
void swapPtr(int *a,int *b){int temp=*a;*a=*b;*b=temp;}
int main(){int x=1,y=2;swapPtr(&x,&y);std::cout<<x<<" "<<y<<std::endl;return 0;}
```

**Expected output:**

```
2 1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Pointer?

**A:** Stores memory address.

**Q2:** * in declaration?

**A:** Declares pointer type.

**Q3:** Pointer vs reference?

**A:** Pointer can be null/reassigned; reference cannot.

**Q4:** nullptr?

**A:** Modern null pointer constant.

**Q5:** void*?

**A:** Generic pointer, cannot dereference.

**Q6:** Pointer arithmetic?

**A:** Adding/subtracting to move through memory.

**Q7:** const int *p?

**A:** Pointer to const int.

**Q8:** int *const p?

**A:** Const pointer to int.

**Q9:** Reference null?

**A:** No, must refer to valid object.

**Q10:** Dangling pointer?

**A:** Points to freed memory.
