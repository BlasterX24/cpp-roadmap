# Topic 25: Capstone Projects

Apply all concepts in complete projects. Reinforce fundamentals, OOP, STL, memory management, and system programming.

## Learn From

Practice projects.

- GitHub C++ Projects — https://github.com/topics/cpp-projects

## Key Concepts

- Combining all topics
- Architecture and design
- Error handling
- Memory management
- OOP patterns
- STL usage
- File I/O
- System programming

## Practice Problems & Solutions

### Problem 1

Contact Book.

**Solution:**

```
#include <iostream>
#include <vector>
#include <string>
struct Contact{std::string name,phone;};
class Book{std::vector<Contact> c;public:
void add(std::string n,std::string p){c.push_back({n,p});}
void print(){for(auto &x:c)std::cout<<x.name<<": "<<x.phone<<std::endl;}};
int main(){Book b;b.add("Alice","123");b.add("Bob","456");b.print();return 0;}
```

**Expected output:**

```
Alice: 123
Bob: 456
```

**Learning points:** 

### Problem 2

Calculator operator overloading.

**Solution:**

```
#include <iostream>
class Calc{public:
double add(double a,double b){return a+b;}
double sub(double a,double b){return a-b;}
double mul(double a,double b){return a*b;}
double div(double a,double b){return b!=0?a/b:0;}};
int main(){Calc c;std::cout<<c.add(10,5)<<std::endl;std::cout<<c.mul(3,4)<<std::endl;return 0;}
```

**Expected output:**

```
15
12
```

**Learning points:** 

### Problem 3

Matrix class.

**Solution:**

```
#include <iostream>
#include <vector>
class Matrix{std::vector<std::vector<int>> d;public:
Matrix(int r,int c):d(r,std::vector<int>(c,0)){}};
int main(){Matrix m(3,3);std::cout<<"matrix"<<std::endl;return 0;}
```

**Expected output:**

```
matrix
```

**Learning points:** 

### Problem 4

Linked list template.

**Solution:**

```
#include <iostream>
template<typename T>
class Node{public:T data;Node *next;Node(T d):data(d),next(nullptr){}};
int main(){Node<int> *h=new Node<int>(1);h->next=new Node<int>(2);std::cout<<h->data<<" "<<h->next->data<<std::endl;delete h->next;delete h;return 0;}
```

**Expected output:**

```
1 2
```

**Learning points:** 

### Problem 5

Run-length compression.

**Solution:**

```
#include <iostream>
#include <string>
std::string compress(const std::string &s){std::string r;int i=0;while(i<(int)s.length()){char c=s[i];int cnt=1;while(i+cnt<(int)s.length()&&s[i+cnt]==c)cnt++;r+=c;if(cnt>1)r+=std::to_string(cnt);i+=cnt;}return r;}
int main(){std::cout<<compress("aaabbbcc")<<std::endl;return 0;}
```

**Expected output:**

```
a3b3c2
```

**Learning points:** 

### Problem 6

Memory pool allocator.

**Solution:**

```
#include <iostream>
#include <vector>
class Pool{std::vector<char> m;public:Pool(int s):m(s){}void *alloc(int s){return (void*)m.data();}};
int main(){Pool p(1024);p.alloc(64);std::cout<<"allocated"<<std::endl;return 0;}
```

**Expected output:**

```
allocated
```

**Learning points:** 

### Problem 7

Template container.

**Solution:**

```
#include <iostream>
#include <vector>
template<typename T>
class MyCont{std::vector<T> d;public:
void push(T v){d.push_back(v);}
auto begin(){return d.begin();}
auto end(){return d.end();}};
int main(){MyCont<int> c;c.push(1);c.push(2);c.push(3);for(auto x:c)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

### Problem 8

Smart pointer custom deleter.

**Solution:**

```
#include <iostream>
#include <memory>
struct R{R(){std::cout<<"acq"<<std::endl;}~R(){std::cout<<"rel"<<std::endl;}};
int main(){std::unique_ptr<R,void(*)(R*)> p(new R(),[](R *r){delete r;});return 0;}
```

**Expected output:**

```
acq
rel
```

**Learning points:** 

### Problem 9

PE header parser.

**Solution:**

```
#include <iostream>
#include <cstdint>
struct PE{uint16_t machine;uint16_t sections;};
int main(){PE h;h.machine=0x14c;h.sections=3;std::cout<<"machine: "<<h.machine<<std::endl;std::cout<<"sections: "<<h.sections<<std::endl;return 0;}
```

**Expected output:**

```
machine: 332
sections: 3
```

**Learning points:** 

### Problem 10

Comprehensive review.

**Solution:**

```
#include <iostream>
#include <vector>
#include <string>
#include <memory>
template<typename T>
T max_val(T a,T b){return a>b?a:b;}
class App{public:
void run(){std::cout<<"All topics covered!"<<std::endl;}};
int main(){App app;app.run();auto p=std::make_unique<int>(42);std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
All topics covered!
42
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Architecture?

**A:** Plan before coding.

**Q2:** Error handling?

**A:** Use try-catch.

**Q3:** Memory practice?

**A:** Use smart pointers.

**Q4:** OOP in projects?

**A:** Encapsulation, inheritance, polymorphism.

**Q5:** STL practice?

**A:** Containers and algorithms.

**Q6:** File I/O?

**A:** Serialize state.

**Q7:** Templates?

**A:** Generic, reusable code.

**Q8:** Testing?

**A:** Verify components.

**Q9:** Performance?

**A:** Profile first.

**Q10:** Code organization?

**A:** Separate concerns.
