# Topic 12: OOP: Inheritance & Polymorphism

Inheritance enables code reuse. Polymorphism allows base pointers to call derived methods via virtual functions. override ensures correct overriding. Pure virtual makes abstract classes.

## Learn From

Inheritance references.

- C++ Inheritance — https://cplusplus.com/doc/tutorial/inheritance/

## Key Concepts

- Base and derived
- Single inheritance
- Virtual functions
- override keyword
- Pure virtual and abstract
- Constructor chaining
- Slicing problem
- Multiple inheritance

## Practice Problems & Solutions

### Problem 1

Animal virtual speak Dog Woof.

**Solution:**

```
#include <iostream>
class Animal{public:virtual void speak(){std::cout<<"..."<<std::endl;}};
class Dog:public Animal{public:void speak()override{std::cout<<"Woof"<<std::endl;}};
int main(){Dog d;d.speak();return 0;}
```

**Expected output:**

```
Woof
```

**Learning points:** 

### Problem 2

Base pointer derived method.

**Solution:**

```
#include <iostream>
class Base{public:virtual void show(){std::cout<<"Base"<<std::endl;}};
class Derived:public Base{public:void show()override{std::cout<<"Derived"<<std::endl;}};
int main(){Base *p=new Derived();p->show();delete p;return 0;}
```

**Expected output:**

```
Derived
```

**Learning points:** 

### Problem 3

Abstract Shape pure virtual area.

**Solution:**

```
#include <iostream>
class Shape{public:virtual double area()=0;};
class Circle:public Shape{public:double r;Circle(double r):r(r){}double area()override{return 3.14159*r*r;}};
int main(){Circle c(5);std::cout<<c.area()<<std::endl;return 0;}
```

**Expected output:**

```
78.5397
```

**Learning points:** 

### Problem 4

Shape->Rectangle area.

**Solution:**

```
#include <iostream>
class Shape{public:virtual double area()=0;virtual ~Shape(){}};
class Rectangle:public Shape{public:double w,h;Rectangle(double w,double h):w(w),h(h){}double area()override{return w*h;}};
int main(){Rectangle r(3,4);std::cout<<r.area()<<std::endl;return 0;}
```

**Expected output:**

```
12
```

**Learning points:** 

### Problem 5

Constructor chaining.

**Solution:**

```
#include <iostream>
class Base{public:Base(){std::cout<<"Base"<<std::endl;}};
class Derived:public Base{public:Derived(){std::cout<<"Derived"<<std::endl;}};
int main(){Derived d;return 0;}
```

**Expected output:**

```
Base
Derived
```

**Learning points:** 

### Problem 6

Slicing problem.

**Solution:**

```
#include <iostream>
class Base{public:virtual void type(){std::cout<<"Base"<<std::endl;}};
class Derived:public Base{public:void type()override{std::cout<<"Derived"<<std::endl;}};
int main(){Derived d;Base b=d;b.type();return 0;}
```

**Expected output:**

```
Base
```

**Learning points:** 

### Problem 7

Virtual destructor.

**Solution:**

```
#include <iostream>
class Base{public:virtual ~Base(){std::cout<<"~Base"<<std::endl;}};
class Derived:public Base{public:~Derived(){std::cout<<"~Derived"<<std::endl;}};
int main(){Base *p=new Derived();delete p;return 0;}
```

**Expected output:**

```
~Derived
~Base
```

**Learning points:** 

### Problem 8

Vehicle->Car printInfo.

**Solution:**

```
#include <iostream>
#include <string>
class Vehicle{public:std::string brand;Vehicle(std::string b):brand(b){}virtual void printInfo(){std::cout<<brand<<std::endl;}};
class Car:public Vehicle{public:int doors;Car(std::string b,int d):Vehicle(b),doors(d){}void printInfo()override{std::cout<<brand<<" "<<doors<<std::endl;}};
int main(){Car c("Toyota",4);c.printInfo();return 0;}
```

**Expected output:**

```
Toyota 4
```

**Learning points:** 

### Problem 9

Dynamic_cast downcast.

**Solution:**

```
#include <iostream>
class Base{public:virtual ~Base(){}};
class Derived:public Base{public:int x=10;};
int main(){Base *b=new Derived();Derived *d=dynamic_cast<Derived*>(b);if(d)std::cout<<d->x<<std::endl;delete b;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 10

Pure virtual interface.

**Solution:**

```
#include <iostream>
class Interface{public:virtual void execute()=0;};
class Implementation:public Interface{public:void execute()override{std::cout<<"Done"<<std::endl;}};
int main(){Implementation i;i.execute();return 0;}
```

**Expected output:**

```
Done
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Virtual functions?

**A:** Enable runtime polymorphism.

**Q2:** override?

**A:** Ensures correct overriding.

**Q3:** Pure virtual?

**A:** Virtual with =0, no base impl.

**Q4:** Abstract class?

**A:** Has pure virtual, cannot instantiate.

**Q5:** Virtual destructor?

**A:** Ensures derived dtor called via base ptr.

**Q6:** Object slicing?

**A:** Derived loses members when assigned to base.

**Q7:** Multiple inheritance?

**A:** Yes, from multiple bases.

**Q8:** Diamond problem?

**A:** Ambiguity from shared base.

**Q9:** dynamic_cast?

**A:** Safely downcasts at runtime.

**Q10:** Virtual vs non-virtual?

**A:** Virtual dynamic dispatch; non-virtual static.
