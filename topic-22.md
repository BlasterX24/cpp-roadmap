# Topic 22: Memory Layout & Internals

Programs have text, data, heap, stack segments. Compilation: preprocess, compile, assemble, link. ELF is Linux; PE is Windows.

## Learn From

Memory references.

- Memory Model — https://en.cppreference.com/w/cpp/language/memory_model

## Key Concepts

- Text segment
- Data segment
- BSS segment
- Heap
- Stack
- Compilation stages
- ELF and PE formats

## Practice Problems & Solutions

### Problem 1

Stack vs heap addresses.

**Solution:**

```
#include <iostream>
int main(){int s=1;int *h=new int(2);std::cout<<"stack: "<<&s<<std::endl;std::cout<<"heap: "<<h<<std::endl;delete h;return 0;}
```

**Expected output:**

```
stack: 0x
```

**Learning points:** 

### Problem 2

Stack growth direction.

**Solution:**

```
#include <iostream>
void func(int *prev){int local;std::cout<<(prev>&local?"down":"up")<<std::endl;}
int main(){int f;func(&f);return 0;}
```

**Expected output:**

```
down
```

**Learning points:** 

### Problem 3

Segment sizes.

**Solution:**

```
#include <iostream>
int gi=1;int gu;
int main(){int l=1;static int si=1;int *h=new int(1);std::cout<<sizeof(l)<<std::endl;delete h;return 0;}
```

**Expected output:**

```
4
```

**Learning points:** 

### Problem 4

Function address.

**Solution:**

```
#include <iostream>
void func(){}
int main(){std::cout<<(void*)func<<std::endl;return 0;}
```

**Expected output:**

```
0x
```

**Learning points:** 

### Problem 5

Heap allocation speed.

**Solution:**

```
#include <iostream>
#include <chrono>
int main(){auto s=std::chrono::high_resolution_clock::now();for(int i=0;i<1000000;i++){int *p=new int(i);delete p;}auto e=std::chrono::high_resolution_clock::now();std::cout<<std::chrono::duration_cast<std::chrono::milliseconds>(e-s).count()<<std::endl;return 0;}
```

**Learning points:** 

### Problem 6

Global vs local addr.

**Solution:**

```
#include <iostream>
int gv=10;
int main(){int lv=20;std::cout<<"g: "<<&gv<<std::endl;std::cout<<"l: "<<&lv<<std::endl;return 0;}
```

**Expected output:**

```
g: 0x
```

**Learning points:** 

### Problem 7

Variable lifetime.

**Solution:**

```
#include <iostream>
int main(){std::cout<<"lifetime"<<std::endl;return 0;}
```

**Expected output:**

```
lifetime
```

**Learning points:** 

### Problem 8

Alignment.

**Solution:**

```
#include <iostream>
struct P{char a;int b;char c;};struct A{int a;char b;int c;};
int main(){std::cout<<sizeof(P)<<std::endl;std::cout<<sizeof(A)<<std::endl;return 0;}
```

**Expected output:**

```
12
12
```

**Learning points:** 

### Problem 9

Memory regions.

**Solution:**

```
#include <iostream>
int g;
int main(){int l;int *h=new int;std::cout<<"code: "<<(void*)main<<std::endl;std::cout<<"data: "<<&g<<std::endl;std::cout<<"stack: "<<&l<<std::endl;std::cout<<"heap: "<<h<<std::endl;delete h;return 0;}
```

**Expected output:**

```
code: 0x
```

**Learning points:** 

### Problem 10

Static storage.

**Solution:**

```
#include <iostream>
void counter(){static int c=0;c++;std::cout<<c<<std::endl;}
int main(){counter();counter();counter();return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Memory segments?

**A:** Text, data, BSS, heap, stack.

**Q2:** Text?

**A:** Executable code (read-only).

**Q3:** Heap?

**A:** Dynamic allocation, grows up.

**Q4:** Stack?

**A:** Locals/calls, grows down.

**Q5:** ELF?

**A:** Linux binary format.

**Q6:** PE?

**A:** Windows binary format.

**Q7:** Compilation stages?

**A:** Preprocess, compile, assemble, link.

**Q8:** Stack vs heap?

**A:** Stack fast; heap slow.

**Q9:** BSS?

**A:** Uninitialized globals.

**Q10:** Layout for RE?

**A:** Understanding structure and exploitation.
