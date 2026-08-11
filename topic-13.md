# Topic 13: Operator Overloading

Operator overloading redefines operators for user-defined types. Overload arithmetic, stream operators, subscript, and function call operators.

## Learn From

Operator references.

- C++ Operators — https://cplusplus.com/doc/tutorial/operators/

## Key Concepts

- Overload + - * /
- Overload << >>
- Overload []
- Overload ()
- Friend functions
- Unary overloading
- Comparison overloading

## Practice Problems & Solutions

### Problem 1

Vec2 overloaded +.

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}Vec2 operator+(const Vec2 &o)const{return Vec2(x+o.x,y+o.y);}};
int main(){Vec2 a(1,2),b(3,4);Vec2 c=a+b;std::cout<<c.x<<" "<<c.y<<std::endl;return 0;}
```

**Expected output:**

```
4 6
```

**Learning points:** 

### Problem 2

Overloaded << for Point.

```
#include <iostream>
class Point{public:int x,y;Point(int x,int y):x(x),y(y){}friend std::ostream &operator<<(std::ostream &os,const Point &p){return os<<"("<<p.x<<","<<p.y<<")";}};
int main(){Point p(3,4);std::cout<<p<<std::endl;return 0;}
```

**Expected output:**

```
(3,4)
```

**Learning points:** 

### Problem 3

IntArray overloaded [].

```
#include <iostream>
#include <vector>
class IntArray{std::vector<int> data;public:IntArray(std::initializer_list<int> l):data(l){}int &operator[](int i){return data[i];}};
int main(){IntArray arr={10,20,30};std::cout<<arr[1]<<std::endl;return 0;}
```

**Expected output:**

```
20
```

**Learning points:** 

### Problem 4

Adder functor ().

```
#include <iostream>
class Adder{public:int operator()(int a,int b){return a+b;}};
int main(){Adder add;std::cout<<add(3,4)<<std::endl;return 0;}
```

**Expected output:**

```
7
```

**Learning points:** 

### Problem 5

Counter prefix ++.

```
#include <iostream>
class Counter{public:int val;Counter(int v):val(v){}Counter &operator++(){val++;return *this;}};
int main(){Counter c(5);++c;std::cout<<c.val<<std::endl;return 0;}
```

**Expected output:**

```
6
```

**Learning points:** 

### Problem 6

Overloaded ==.

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}bool operator==(const Vec2 &o)const{return x==o.x&&y==o.y;}};
int main(){Vec2 a(1,2),b(1,2);std::cout<<(a==b)<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 7

Scalar multiplication *.

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}Vec2 operator*(int s)const{return Vec2(x*s,y*s);}};
int main(){Vec2 a(2,3);Vec2 b=a*3;std::cout<<b.x<<" "<<b.y<<std::endl;return 0;}
```

**Expected output:**

```
6 9
```

**Learning points:** 

### Problem 8

Unary minus.

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}Vec2 operator-()const{return Vec2(-x,-y);}};
int main(){Vec2 a(3,4);Vec2 b=-a;std::cout<<b.x<<" "<<b.y<<std::endl;return 0;}
```

**Expected output:**

```
-3 -4
```

**Learning points:** 

### Problem 9

Overloaded !=.

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}bool operator==(const Vec2 &o)const{return x==o.x&&y==o.y;}bool operator!=(const Vec2 &o)const{return !(*this==o);}};
int main(){Vec2 a(1,2),b(3,4);std::cout<<(a!=b)<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 10

Overloaded < for sorting.

```
#include <iostream>
#include <algorithm>
#include <vector>
class Score{public:int val;Score(int v):val(v){}bool operator<(const Score &o)const{return val<o.val;}};
int main(){std::vector<Score> v={Score(5),Score(1),Score(3)};std::sort(v.begin(),v.end());std::cout<<v[0].val<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Overload all?

**A:** No, :: . .* ?: cannot.

**Q2:** Friend function?

**A:** Non-member with private access.

**Q3:** Prefix vs postfix?

**A:** Prefix reference; postfix dummy int.

**Q4:** Overload <<?

**A:** Yes, as friend.

**Q5:** Functor?

**A:** Class with operator().

**Q6:** [] return reference?

**A:** Yes, for read/write.

**Q7:** Overload ==?

**A:** Natural comparison.

**Q8:** Built-in types?

**A:** No, only user-defined.

**Q9:** == return type?

**A:** bool.

**Q10:** << be friend?

**A:** Yes, left is ostream.
