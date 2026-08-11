# Topic 15: STL: Containers

STL provides ready-made containers. vector is dynamic array; map stores key-value pairs; set stores unique elements; stack/queue are adapters.

## Learn From

Container references.

- C++ Containers — https://cplusplus.com/reference/stl/

## Key Concepts

- std::vector
- std::list
- std::map
- std::set
- std::stack
- std::queue
- std::pair
- Container operations

## Practice Problems & Solutions

### Problem 1

Vector push 4 print size.

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={1,2,3};v.push_back(4);std::cout<<v.size()<<std::endl;return 0;}
```

**Expected output:**

```
4
```

**Learning points:** 

### Problem 2

Map insert key-value.

**Solution:**

```
#include <iostream>
#include <map>
#include <string>
int main(){std::map<std::string,int> m;m["one"]=1;m["two"]=2;std::cout<<m["one"]<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 3

Set insert unique.

**Solution:**

```
#include <iostream>
#include <set>
int main(){std::set<int> s;s.insert(3);s.insert(1);s.insert(3);std::cout<<s.size()<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 4

Stack push/pop.

**Solution:**

```
#include <iostream>
#include <stack>
int main(){std::stack<int> s;s.push(1);s.push(2);s.push(3);s.pop();std::cout<<s.top()<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 5

Queue push/pop.

**Solution:**

```
#include <iostream>
#include <queue>
int main(){std::queue<int> q;q.push(10);q.push(20);q.push(30);q.pop();std::cout<<q.front()<<std::endl;return 0;}
```

**Expected output:**

```
20
```

**Learning points:** 

### Problem 6

Pair creation.

**Solution:**

```
#include <iostream>
#include <utility>
#include <string>
int main(){std::pair<int,std::string> p(42,"hello");std::cout<<p.first<<" "<<p.second<<std::endl;return 0;}
```

**Expected output:**

```
42 hello
```

**Learning points:** 

### Problem 7

Vector [] access.

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={10,20,30};std::cout<<v[0]<<" "<<v[2]<<std::endl;return 0;}
```

**Expected output:**

```
10 30
```

**Learning points:** 

### Problem 8

Vector at().

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={1,2,3};std::cout<<v.at(1)<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 9

Map find check.

**Solution:**

```
#include <iostream>
#include <map>
#include <string>
int main(){std::map<int,std::string> m;m[1]="one";if(m.find(1)!=m.end())std::cout<<m[1]<<std::endl;return 0;}
```

**Expected output:**

```
one
```

**Learning points:** 

### Problem 10

Vector clear empty.

**Solution:**

```
#include <iostream>
#include <vector>
int main(){std::vector<int> v={1,2,3};v.clear();std::cout<<(v.empty()?"empty":"not empty")<<std::endl;return 0;}
```

**Expected output:**

```
empty
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** vector vs array?

**A:** Dynamic vs fixed-size.

**Q2:** Vector access?

**A:** O(1) random access.

**Q3:** Map insert?

**A:** O(log n).

**Q4:** find not found?

**A:** Returns end().

**Q5:** Set duplicates?

**A:** No, use multiset.

**Q6:** stack vs queue?

**A:** LIFO vs FIFO.

**Q7:** push_back?

**A:** Amortized O(1).

**Q8:** pair?

**A:** Holds two values.

**Q9:** multimap?

**A:** Multiple values per key.

**Q10:** begin vs end?

**A:** First element vs past last.
