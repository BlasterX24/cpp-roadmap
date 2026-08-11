# Topic 11: OOP: Classes & Objects

OOP builds around classes bundling data and behavior. Constructors initialize; destructors clean up. this pointer refers to current object.

## Learn From

Classes references.

- C++ Classes — https://cplusplus.com/doc/tutorial/classes/

## Key Concepts

- Class with public/private/protected
- Constructors
- Destructor
- this pointer
- Member functions
- Access specifiers
- Struct vs class

## Practice Problems & Solutions

### Problem 1

Class Animal speak.

**Solution:**

```
#include <iostream>
#include <string>
class Animal{public:std::string name;void speak(){std::cout<<name<<std::endl;}};
int main(){Animal a;a.name="Dog";a.speak();return 0;}
```

**Expected output:**

```
Dog
```

**Learning points:** 

### Problem 2

Class Box default constructor.

**Solution:**

```
#include <iostream>
class Box{public:int volume;Box():volume(0){}};
int main(){Box b;std::cout<<b.volume<<std::endl;return 0;}
```

**Expected output:**

```
0
```

**Learning points:** 

### Problem 3

Circle with area.

**Solution:**

```
#include <iostream>
#include <cmath>
class Circle{public:double radius;Circle(double r):radius(r){}double area(){return 3.14159*radius*radius;}};
int main(){Circle c(5);std::cout<<c.area()<<std::endl;return 0;}
```

**Expected output:**

```
78.5397
```

**Learning points:** 

### Problem 4

Counter increment/get.

**Solution:**

```
#include <iostream>
class Counter{private:int count;public:Counter():count(0){}void increment(){count++;}int get(){return count;}};
int main(){Counter c;c.increment();c.increment();std::cout<<c.get()<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 5

This pointer setter.

**Solution:**

```
#include <iostream>
class MyClass{public:int value;MyClass &setValue(int v){this->value=v;return *this;}};
int main(){MyClass obj;obj.setValue(42);std::cout<<obj.value<<std::endl;return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 6

Copy constructor.

**Solution:**

```
#include <iostream>
class Vec2{public:int x,y;Vec2(int x,int y):x(x),y(y){}Vec2(const Vec2 &o):x(o.x),y(o.y){}};
int main(){Vec2 a(1,2);Vec2 b=a;std::cout<<b.x<<" "<<b.y<<std::endl;return 0;}
```

**Expected output:**

```
1 2
```

**Learning points:** 

### Problem 7

Static member count.

**Solution:**

```
#include <iostream>
class Obj{public:static int count;Obj(){count++;}};
int Obj::count=0;
int main(){Obj a,b,c;std::cout<<Obj::count<<std::endl;return 0;}
```

**Expected output:**

```
3
```

**Learning points:** 

### Problem 8

Rectangle area/perimeter.

**Solution:**

```
#include <iostream>
class Rectangle{public:int w,h;Rectangle(int w,int h):w(w),h(h){}int area(){return w*h;}int perimeter(){return 2*(w+h);}};
int main(){Rectangle r(4,5);std::cout<<r.area()<<std::endl;std::cout<<r.perimeter()<<std::endl;return 0;}
```

**Expected output:**

```
20
18
```

**Learning points:** 

### Problem 9

Const member function.

**Solution:**

```
#include <iostream>
class Point{public:int x,y;Point(int x,int y):x(x),y(y){}void print()const{std::cout<<x<<","<<y<<std::endl;}};
int main(){const Point p(3,4);p.print();return 0;}
```

**Expected output:**

```
3,4
```

**Learning points:** 

### Problem 10

Singleton pattern.

**Solution:**

```
#include <iostream>
class Singleton{public:static Singleton& getInstance(){static Singleton instance;return instance;}void show(){std::cout<<"Singleton"<<std::endl;}};
int main(){Singleton::getInstance().show();return 0;}
```

**Expected output:**

```
Singleton
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Public vs private?

**A:** Public anywhere; private within class.

**Q2:** this pointer?

**A:** Hidden pointer to current object.

**Q3:** Constructor?

**A:** Called on object creation.

**Q4:** Copy constructor?

**A:** Creates new object as copy.

**Q5:** Destructor?

**A:** Called when object goes out of scope.

**Q6:** Private constructor?

**A:** Yes, for singleton/factory.

**Q7:** const member function?

**A:** Promises not to modify members.

**Q8:** struct vs class?

**A:** Struct public default; class private.

**Q9:** static member?

**A:** Shared by all instances.

**Q10:** No constructor?

**A:** Compiler provides default.
