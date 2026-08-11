# Topic 8: Dynamic Memory

Dynamic allocation creates objects at runtime. new allocates and calls constructor; delete frees. malloc/free don't call constructors. RAII ties resources to scope.

## Learn From

Memory references.

- C++ new/delete — https://cplusplus.com/doc/tutorial/dynamic/

## Key Concepts

- new and delete
- new[] and delete[]
- malloc, calloc, realloc, free
- Memory leaks
- Dangling pointers
- RAII principle
- Stack vs heap

## Practice Problems & Solutions

### Problem 1

Allocate int=42 print free.

**Solution:**

```
#include <iostream>
int main(){int *p=new int(42);std::cout<<*p<<std::endl;delete p;return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 2

Allocate array 5 ints.

**Solution:**

```
#include <iostream>
int main(){int *arr=new int[5]{1,2,3,4,5};for(int i=0;i<5;i++)std::cout<<arr[i]<<std::endl;delete[] arr;return 0;}
```

**Expected output:**

```
1
2
3
4
5
```

**Learning points:** 

### Problem 3

Malloc allocate int=99.

**Solution:**

```
#include <iostream>
#include <cstdlib>
int main(){int *p=(int*)malloc(sizeof(int));*p=99;std::cout<<*p<<std::endl;free(p);return 0;}
```

**Expected output:**

```
99
```

**Learning points:** 

### Problem 4

Allocate double=2.718.

**Solution:**

```
#include <iostream>
int main(){double *p=new double(2.718);std::cout<<*p<<std::endl;delete p;return 0;}
```

**Expected output:**

```
2.718
```

**Learning points:** 

### Problem 5

Malloc array realloc.

**Solution:**

```
#include <iostream>
#include <cstdlib>
int main(){int *arr=(int*)malloc(3*sizeof(int));arr[0]=1;arr[1]=2;arr[2]=3;arr=(int*)realloc(arr,5*sizeof(int));arr[3]=4;arr[4]=5;for(int i=0;i<5;i++)std::cout<<arr[i]<<std::endl;free(arr);return 0;}
```

**Expected output:**

```
1
2
3
4
5
```

**Learning points:** 

### Problem 6

Delete then nullptr.

**Solution:**

```
#include <iostream>
int main(){int *p=new int(10);delete p;p=nullptr;if(p==nullptr)std::cout<<"null"<<std::endl;return 0;}
```

**Expected output:**

```
null
```

**Learning points:** 

### Problem 7

Allocate char array Hi.

**Solution:**

```
#include <iostream>
int main(){char *str=new char[3];str[0]='H';str[1]='i';str[2]='\0';std::cout<<str<<std::endl;delete[] str;return 0;}
```

**Expected output:**

```
Hi
```

**Learning points:** 

### Problem 8

Sum 3 doubles.

**Solution:**

```
#include <iostream>
int main(){double *arr=new double[3]{1.1,2.2,3.3};double sum=0;for(int i=0;i<3;i++)sum+=arr[i];std::cout<<sum<<std::endl;delete[] arr;return 0;}
```

**Expected output:**

```
6.6
```

**Learning points:** 

### Problem 9

Memory leak demo.

**Solution:**

```
#include <iostream>
int main(){int *p=new int(5);std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
5
```

**Learning points:** 

### Problem 10

Malloc char sizeof.

**Solution:**

```
#include <iostream>
#include <cstdlib>
int main(){char *p=(char*)malloc(sizeof(char));std::cout<<sizeof(*p)<<std::endl;free(p);return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** new vs malloc?

**A:** new calls constructor; malloc does not.

**Q2:** delete[] for arrays?

**A:** Calls destructors for all elements.

**Q3:** Memory leak?

**A:** Allocated memory never freed.

**Q4:** RAII?

**A:** Resource lifetime tied to scope.

**Q5:** Double free?

**A:** Undefined behavior.

**Q6:** Dangling pointer?

**A:** Points to freed memory.

**Q7:** Stack vs heap?

**A:** Stack automatic/fast; heap manual/larger.

**Q8:** calloc vs malloc?

**A:** Initializes to zero.

**Q9:** free on new?

**A:** Undefined behavior.

**Q10:** Smart pointer?

**A:** Object managing memory automatically.
