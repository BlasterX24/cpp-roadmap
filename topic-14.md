# Topic 14: Templates

Templates enable generic programming. Function/class templates generate code per type. Specialization provides custom behavior.

## Learn From

Templates references.

- C++ Templates — https://cplusplus.com/doc/tutorial/templates/

## Key Concepts

- Function templates
- Class templates
- Template specialization
- Non-type parameters
- Template instantiation
- SFINAE basics
- Variadic templates

## Practice Problems & Solutions

### Problem 1

Template max.

```
#include <iostream>
template<typename T>
T maxValue(T a,T b){return (a>b)?a:b;}
int main(){std::cout<<maxValue(3,7)<<std::endl;std::cout<<maxValue(2.5,1.5)<<std::endl;return 0;}
```

**Expected output:**

```
7
2.5
```

**Learning points:** 

### Problem 2

Template swap.

```
#include <iostream>
template<typename T>
void mySwap(T &a,T &b){T temp=a;a=b;b=temp;}
int main(){int x=1,y=2;mySwap(x,y);std::cout<<x<<" "<<y<<std::endl;return 0;}
```

**Expected output:**

```
2 1
```

**Learning points:** 

### Problem 3

Class template Pair.

```
#include <iostream>
template<typename T,typename U>
class Pair{public:T first;U second;Pair(T f,U s):first(f),second(s){}};
int main(){Pair<int,double> p(42,3.14);std::cout<<p.first<<" "<<p.second<<std::endl;return 0;}
```

**Expected output:**

```
42 3.14
```

**Learning points:** 

### Problem 4

Template print array.

```
#include <iostream>
template<typename T>
void printArray(T arr[],int size){for(int i=0;i<size;i++)std::cout<<arr[i]<<std::endl;}
int main(){int arr[]={1,2,3};printArray(arr,3);return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

### Problem 5

Template specialization const char*.

```
#include <iostream>
#include <cstring>
template<typename T>
T minValue(T a,T b){return (a<b)?a:b;}
template<>
const char* minValue<const char*>(const char* a,const char* b){return (strcmp(a,b)<0)?a:b;}
int main(){std::cout<<minValue("apple","banana")<<std::endl;return 0;}
```

**Expected output:**

```
apple
```

**Learning points:** 

### Problem 6

Class template Stack.

```
#include <iostream>
#include <vector>
template<typename T>
class Stack{std::vector<T> data;public:void push(T v){data.push_back(v);}void pop(){data.pop_back();}T top(){return data.back();}};
int main(){Stack<int> s;s.push(10);s.push(20);std::cout<<s.top()<<std::endl;s.pop();std::cout<<s.top()<<std::endl;return 0;}
```

**Expected output:**

```
20
10
```

**Learning points:** 

### Problem 7

Template abs.

```
#include <iostream>
template<typename T>
T myAbs(T x){return (x<0)?-x:x;}
int main(){std::cout<<myAbs(-5)<<std::endl;std::cout<<myAbs(-3.14)<<std::endl;return 0;}
```

**Expected output:**

```
5
3.14
```

**Learning points:** 

### Problem 8

Template first element.

```
#include <iostream>
template<typename T>
T first(T arr[]){return arr[0];}
int main(){int arr[]={99,2,3};std::cout<<first(arr)<<std::endl;return 0;}
```

**Expected output:**

```
99
```

**Learning points:** 

### Problem 9

Template bool specialization.

```
#include <iostream>
template<typename T>
void printVal(T v){std::cout<<v<<std::endl;}
template<>
void printVal<bool>(bool v){std::cout<<(v?"true":"false")<<std::endl;}
int main(){printVal(42);printVal(true);printVal(false);return 0;}
```

**Expected output:**

```
42
true
false
```

**Learning points:** 

### Problem 10

Non-type template power of 2.

```
#include <iostream>
template<int N>
int powerOf2(){return 1<<N;}
int main(){std::cout<<powerOf2<3>()<<std::endl;std::cout<<powerOf2<0>()<<std::endl;return 0;}
```

**Expected output:**

```
8
1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Template?

**A:** Blueprint for generic code.

**Q2:** Specialization?

**A:** Custom impl for specific type.

**Q3:** When instantiated?

**A:** At compile time.

**Q4:** Non-type parameter?

**A:** Takes a value, not type.

**Q5:** SFINAE?

**A:** Substitution Failure Not Error.

**Q6:** Templates in headers?

**A:** Yes, needed at instantiation.

**Q7:** typename keyword?

**A:** Indicates dependent type name.

**Q8:** Variadic template?

**A:** Variable number of arguments.

**Q9:** Different members?

**A:** Yes, specialization can differ.

**Q10:** typename vs class?

**A:** Identical for type params.
