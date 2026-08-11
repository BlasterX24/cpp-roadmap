# Topic 18: Smart Pointers & RAII

Smart pointers automate memory. unique_ptr exclusive; shared_ptr shared; weak_ptr observes. RAII ties resources to scope.

## Learn From

Smart pointer references.

- C++ Smart Pointers — https://en.cppreference.com/w/cpp/memory/unique_ptr

## Key Concepts

- unique_ptr exclusive
- shared_ptr shared
- weak_ptr observer
- make_unique/make_shared
- RAII cleanup
- Circular references
- Custom deleters

## Practice Problems & Solutions

### Problem 1

unique_ptr manage int.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){std::unique_ptr<int> p=std::make_unique<int>(42);std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
42
```

**Learning points:** 

### Problem 2

shared_ptr share string.

**Solution:**

```
#include <iostream>
#include <memory>
#include <string>
int main(){auto p1=std::make_shared<std::string>("Hello");auto p2=p1;std::cout<<*p1<<std::endl;std::cout<<p1.use_count()<<std::endl;return 0;}
```

**Expected output:**

```
Hello
2
```

**Learning points:** 

### Problem 3

weak_ptr observe.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){std::weak_ptr<int> wp;{auto sp=std::make_shared<int>(10);wp=sp;std::cout<<wp.expired()<<std::endl;}std::cout<<wp.expired()<<std::endl;return 0;}
```

**Expected output:**

```
0
1
```

**Learning points:** 

### Problem 4

unique_ptr array.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){auto arr=std::make_unique<int[]>(3);arr[0]=10;arr[1]=20;arr[2]=30;for(int i=0;i<3;i++)std::cout<<arr[i]<<std::endl;return 0;}
```

**Expected output:**

```
10
20
30
```

**Learning points:** 

### Problem 5

unique_ptr move.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){auto p1=std::make_unique<int>(5);auto p2=std::move(p1);std::cout<<(p1==nullptr)<<std::endl;std::cout<<*p2<<std::endl;return 0;}
```

**Expected output:**

```
1
5
```

**Learning points:** 

### Problem 6

make_shared pair.

**Solution:**

```
#include <iostream>
#include <memory>
#include <utility>
int main(){auto p=std::make_shared<std::pair<int,int>>(1,2);std::cout<<p->first<<" "<<p->second<<std::endl;return 0;}
```

**Expected output:**

```
1 2
```

**Learning points:** 

### Problem 7

RAII resource class.

**Solution:**

```
#include <iostream>
#include <memory>
class R{public:R(){std::cout<<"acquired"<<std::endl;}~R(){std::cout<<"released"<<std::endl;}};
int main(){auto p=std::make_unique<R>();return 0;}
```

**Expected output:**

```
acquired
released
```

**Learning points:** 

### Problem 8

shared_ptr custom deleter.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){auto d=[](int *p){std::cout<<"deleted"<<std::endl;delete p;};std::shared_ptr<int> p(new int(7),d);std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
7
deleted
```

**Learning points:** 

### Problem 9

weak_ptr lock.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){std::weak_ptr<int> wp;{auto sp=std::make_shared<int>(99);wp=sp;auto l=wp.lock();if(l)std::cout<<*l<<std::endl;}return 0;}
```

**Expected output:**

```
99
```

**Learning points:** 

### Problem 10

unique_ptr nullptr check.

**Solution:**

```
#include <iostream>
#include <memory>
int main(){std::unique_ptr<int> p;if(!p)std::cout<<"empty"<<std::endl;p=std::make_unique<int>(88);if(p)std::cout<<*p<<std::endl;return 0;}
```

**Expected output:**

```
empty
88
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** unique_ptr vs shared_ptr?

**A:** Exclusive vs shared ownership.

**Q2:** weak_ptr?

**A:** Observe without owning.

**Q3:** make_unique?

**A:** Creates unique_ptr safely.

**Q4:** make_shared?

**A:** Creates shared_ptr safely.

**Q5:** Copy unique_ptr?

**A:** No, use std::move.

**Q6:** Circular reference?

**A:** shared_ptrs prevent deallocation.

**Q7:** RAII?

**A:** Resources tied to scope.

**Q8:** Last shared_ptr?

**A:** Object destroyed.

**Q9:** weak_ptr access?

**A:** Call lock() first.

**Q10:** Custom deleter?

**A:** Defines cleanup function.
