# Topic 17: Lambda & Modern C++

C++11 introduced lambdas, auto, range-for, nullptr, and initializer lists for cleaner, safer code.

## Learn From

Modern C++ references.

- cppreference Lambda — https://en.cppreference.com/w/cpp/language/lambda

## Key Concepts

- Lambda [capture](params){body}
- Capture by value/reference
- auto deduction
- Range-based for
- nullptr
- Initializer lists
- std::function

## Practice Problems & Solutions

### Problem 1

Lambda prints Hello Lambda.

**Solution:**

```
#include <iostream>
int main(){auto greet=[](){std::cout<<"Hello Lambda"<<std::endl;};greet();return 0;}
```

**Expected output:**

```
Hello Lambda
```

**Learning points:** 

### Problem 2

Lambda adds two ints.

**Solution:**

```
#include <iostream>
int main(){auto add=[](int a,int b){return a+b;};std::cout<<add(3,4)<<std::endl;return 0;}
```

**Expected output:**

```
7
```

**Learning points:** 

### Problem 3

Auto deduction.

**Solution:**

```
#include <iostream>
int main(){auto x=42;auto y=3.14;std::cout<<x<<std::endl;std::cout<<y<<std::endl;return 0;}
```

**Expected output:**

```
42
3.14
```

**Learning points:** 

### Problem 4

Range-based for.

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={1,2,3,4,5};for(int x:v)std::cout<<x<<std::endl;return 0;}
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

### Problem 5

Lambda capture value.

**Solution:**

```
#include <iostream>
int main(){int f=3;auto m=[f](int x){return x*f;};std::cout<<m(5)<<std::endl;return 0;}
```

**Expected output:**

```
15
```

**Learning points:** 

### Problem 6

Lambda capture reference.

**Solution:**

```
#include <iostream>
int main(){int c=0;auto inc=[&c](){c++;};inc();inc();std::cout<<c<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 7

nullptr check.

**Solution:**

```
#include <iostream>
int main(){int *p=nullptr;if(p==nullptr)std::cout<<"null"<<std::endl;return 0;}
```

**Expected output:**

```
null
```

**Learning points:** 

### Problem 8

Initializer list vector.

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={10,20,30};for(int x:v)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
10
20
30
```

**Learning points:** 

### Problem 9

Lambda comparator sort.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={5,2,8,1};std::sort(v.begin(),v.end(),[](int a,int b){return a<b;});for(int x:v)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
1
2
5
8
```

**Learning points:** 

### Problem 10

Lambda auto return.

**Solution:**

```
#include <iostream>
int main(){auto sq=[](int x){return x*x;};std::cout<<sq(6)<<std::endl;return 0;}
```

**Expected output:**

```
36
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Lambda?

**A:** Anonymous function.

**Q2:** Capture list?

**A:** Variables and how to capture.

**Q3:** [x] vs [&x]?

**A:** Value vs reference.

**Q4:** auto?

**A:** Deduces type.

**Q5:** Range-for?

**A:** Iterates all elements.

**Q6:** nullptr vs NULL?

**A:** Type-safe vs 0.

**Q7:** Initializer lists?

**A:** Curly-brace initialization.

**Q8:** [=] capture?

**A:** All by value.

**Q9:** Store lambda?

**A:** auto or std::function.

**Q10:** Return syntax?

**A:** -> return_type.
