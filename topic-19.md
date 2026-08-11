# Topic 19: Exception Handling

Exceptions handle runtime errors. throw raises; try wraps; catch handles. Propagates up call stack. noexcept means no throw.

## Learn From

Exception references.

- C++ Exceptions — https://cplusplus.com/doc/tutorial/exceptions/

## Key Concepts

- throw, try, catch
- catch-all (...)
- Standard exceptions
- Custom exceptions
- noexcept
- Stack unwinding
- Exception safety

## Practice Problems & Solutions

### Problem 1

Throw int exception.

```
#include <iostream>
int main(){try{throw 42;}catch(int e){std::cout<<e<<std::endl;}return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 2

Throw string exception.

```
#include <iostream>
#include <string>
int main(){try{throw std::string("error");}catch(std::string &e){std::cout<<e<<std::endl;}return 0;}
```

**Expected output:**

```
error
```

**Learning points:** 

### Problem 3

Throw runtime_error.

```
#include <iostream>
#include <stdexcept>
int main(){try{throw std::runtime_error("boom");}catch(std::exception &e){std::cout<<e.what()<<std::endl;}return 0;}
```

**Expected output:**

```
boom
```

**Learning points:** 

### Problem 4

Multiple catch blocks.

```
#include <iostream>
int main(){try{throw 3.14;}catch(int e){std::cout<<"int"<<std::endl;}catch(double e){std::cout<<"double"<<std::endl;}return 0;}
```

**Expected output:**

```
double
```

**Learning points:** 

### Problem 5

Catch-all handler.

```
#include <iostream>
int main(){try{throw 'x';}catch(...){std::cout<<"caught"<<std::endl;}return 0;}
```

**Expected output:**

```
caught
```

**Learning points:** 

### Problem 6

Throw negative.

```
#include <iostream>
#include <stdexcept>
void check(int n){if(n<0)throw std::invalid_argument("negative");}
int main(){try{check(-1);}catch(std::invalid_argument &e){std::cout<<e.what()<<std::endl;}return 0;}
```

**Expected output:**

```
negative
```

**Learning points:** 

### Problem 7

Custom exception class.

```
#include <iostream>
#include <exception>
#include <string>
class MyErr:public std::exception{std::string m;public:MyErr(std::string s):m(s){}const char* what()const noexcept override{return m.c_str();}};
int main(){try{throw MyErr("custom");}catch(MyErr &e){std::cout<<e.what()<<std::endl;}return 0;}
```

**Expected output:**

```
custom
```

**Learning points:** 

### Problem 8

Exception propagation.

```
#include <iostream>
#include <stdexcept>
void inner(){throw std::runtime_error("deep");}
void outer(){inner();}
int main(){try{outer();}catch(std::exception &e){std::cout<<e.what()<<std::endl;}return 0;}
```

**Expected output:**

```
deep
```

**Learning points:** 

### Problem 9

noexcept specifier.

```
#include <iostream>
void safe()noexcept{std::cout<<"safe"<<std::endl;}
int main(){safe();return 0;}
```

**Expected output:**

```
safe
```

**Learning points:** 

### Problem 10

Re-throw exception.

```
#include <iostream>
#include <stdexcept>
int main(){try{try{throw std::runtime_error("orig");}catch(...){throw;}}catch(std::exception &e){std::cout<<e.what()<<std::endl;}return 0;}
```

**Expected output:**

```
orig
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** try-catch purpose?

**A:** Handle exceptions.

**Q2:** throw do?

**A:** Raises exception.

**Q3:** catch-all?

**A:** catch(...) catches any.

**Q4:** std::exception?

**A:** Base class for exceptions.

**Q5:** noexcept?

**A:** Guarantees no throw.

**Q6:** Stack unwinding?

**A:** Destroying locals during propagation.

**Q7:** Uncatched?

**A:** std::terminate() called.

**Q8:** Constructors throw?

**A:** Yes.

**Q9:** Exception safety?

**A:** Valid state during errors.

**Q10:** throw vs throw;?

**A:** New vs re-throw current.
