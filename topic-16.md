# Topic 16: STL: Iterators & Algorithms

Iterators point to elements with uniform interface. Algorithms work on iterator ranges. Lambdas are common arguments.

## Learn From

Iterator references.

- C++ Algorithms — https://en.cppreference.com/w/cpp/algorithm

## Key Concepts

- Iterator types
- begin() and end()
- sort, find, transform
- for_each, count_if
- reverse, copy
- Lambdas with algorithms
- Iterator invalidation

## Practice Problems & Solutions

### Problem 1

Sort vector.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={5,3,1,4,2};std::sort(v.begin(),v.end());for(int x:v)std::cout<<x<<std::endl;return 0;}
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

### Problem 2

Find 7.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={3,7,1,9};auto it=std::find(v.begin(),v.end(),7);std::cout<<(it!=v.end())<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 3

Transform double.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={1,2,3};std::vector<int> r(3);std::transform(v.begin(),v.end(),r.begin(),[](int x){return x*2;});for(int x:r)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
2
4
6
```

**Learning points:** 

### Problem 4

Count_if >5.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={3,8,1,9,4};int c=std::count_if(v.begin(),v.end(),[](int x){return x>5;});std::cout<<c<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 5

Reverse vector.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={1,2,3,4,5};std::reverse(v.begin(),v.end());for(int x:v)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
5
4
3
2
1
```

**Learning points:** 

### Problem 6

For_each print.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={10,20,30};std::for_each(v.begin(),v.end(),[](int x){std::cout<<x<<std::endl;});return 0;}
```

**Expected output:**

```
10
20
30
```

**Learning points:** 

### Problem 7

Accumulate sum.

**Solution:**

```
#include <iostream>
#include <vector>
#include <numeric>
int main(){std::vector<int> v={1,2,3,4,5};int s=std::accumulate(v.begin(),v.end(),0);std::cout<<s<<std::endl;return 0;}
```

**Expected output:**

```
15
```

**Learning points:** 

### Problem 8

Copy vector.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> src={1,2,3};std::vector<int> dst(3);std::copy(src.begin(),src.end(),dst.begin());for(int x:dst)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

### Problem 9

Max element.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={3,1,4,1,5};auto it=std::max_element(v.begin(),v.end());std::cout<<*it<<std::endl;return 0;}
```

**Expected output:**

```
5
```

**Learning points:** 

### Problem 10

Sort descending lambda.

**Solution:**

```
#include <iostream>
#include <vector>
#include <algorithm>
int main(){std::vector<int> v={3,1,4,1,5};std::sort(v.begin(),v.end(),[](int a,int b){return a>b;});for(int x:v)std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
5
4
3
1
1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** Iterator?

**A:** Points to container element.

**Q2:** begin()?

**A:** First element.

**Q3:** end()?

**A:** Past last element.

**Q4:** sort complexity?

**A:** O(n log n).

**Q5:** find not found?

**A:** Returns end().

**Q6:** transform?

**A:** Apply function to elements.

**Q7:** Lambdas with STL?

**A:** Yes, as comparators/predicates.

**Q8:** accumulate?

**A:** Sum or binary operation.

**Q9:** Invalidation?

**A:** Iterators point to invalid memory.

**Q10:** Categories?

**A:** Input, output, forward, bidirectional, random-access.
