# Topic 6: Arrays & C-Strings

Arrays hold same-type elements contiguously. C-strings are char arrays terminated by null. <cstring> has strlen, strcpy, strcmp, strcat. Bounds not checked.

## Learn From

Array references.

- C++ Arrays — https://cplusplus.com/doc/tutorial/arrays/
- cstring — https://en.cppreference.com/w/cpp/header/cstring

## Key Concepts

- Array declaration
- Array size with sizeof
- C-strings null termination
- strlen, strcpy, strcmp, strcat
- Bounds undefined behavior
- Multi-dimensional arrays
- Passing arrays to functions

## Practice Problems & Solutions

### Problem 1

Print array {1,2,3,4,5}.

**Solution:**

```
#include <iostream>
int main(){int arr[]={1,2,3,4,5};for(int i=0;i<5;i++)std::cout<<arr[i]<<std::endl;return 0;}
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

Print array size.

**Solution:**

```
#include <iostream>
int main(){int arr[]={10,20,30,40,50};std::cout<<sizeof(arr)/sizeof(arr[0])<<std::endl;return 0;}
```

**Expected output:**

```
5
```

**Learning points:** 

### Problem 3

Print strlen of Hello.

**Solution:**

```
#include <iostream>
#include <cstring>
int main(){char str[]="Hello";std::cout<<strlen(str)<<std::endl;return 0;}
```

**Expected output:**

```
5
```

**Learning points:** 

### Problem 4

Copy string.

**Solution:**

```
#include <iostream>
#include <cstring>
int main(){char dest[20];strcpy(dest,"World");std::cout<<dest<<std::endl;return 0;}
```

**Expected output:**

```
World
```

**Learning points:** 

### Problem 5

Compare strings.

**Solution:**

```
#include <iostream>
#include <cstring>
int main(){std::cout<<strcmp("abc","abd")<<std::endl;return 0;}
```

**Expected output:**

```
-1
```

**Learning points:** 

### Problem 6

Find max in array.

**Solution:**

```
#include <iostream>
int main(){int arr[]={3,7,2,9,4};int max=arr[0];for(int i=1;i<5;i++)if(arr[i]>max)max=arr[i];std::cout<<max<<std::endl;return 0;}
```

**Expected output:**

```
9
```

**Learning points:** 

### Problem 7

Reverse array.

**Solution:**

```
#include <iostream>
int main(){int arr[]={1,2,3,4,5};for(int i=4;i>=0;i--)std::cout<<arr[i]<<(i>0?" ":"");std::cout<<std::endl;return 0;}
```

**Expected output:**

```
5 4 3 2 1
```

**Learning points:** 

### Problem 8

Concatenate strings.

**Solution:**

```
#include <iostream>
#include <cstring>
int main(){char str[20]="Hello";strcat(str," there");std::cout<<str<<std::endl;return 0;}
```

**Expected output:**

```
Hello there
```

**Learning points:** 

### Problem 9

Count vowels in Hello World.

**Solution:**

```
#include <iostream>
#include <cstring>
int main(){char str[]="Hello World";int c=0;for(int i=0;str[i];i++){char ch=str[i];if(ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'||ch=='A'||ch=='E'||ch=='I'||ch=='O'||ch=='U')c++;}std::cout<<c<<std::endl;return 0;}
```

**Expected output:**

```
3
```

**Learning points:** 

### Problem 10

2D array print.

**Solution:**

```
#include <iostream>
int main(){int arr[2][3]={{1,2,3},{4,5,6}};for(int i=0;i<2;i++)for(int j=0;j<3;j++)std::cout<<arr[i][j]<<std::endl;return 0;}
```

**Expected output:**

```
1
2
3
4
5
6
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** C-string vs char array?

**A:** C-string terminated by null.

**Q2:** Bounds danger?

**A:** Undefined behavior.

**Q3:** strlen empty string?

**A:** 0.

**Q4:** strcpy overflow?

**A:** Buffer overflow.

**Q5:** Array size?

**A:** sizeof(arr)/sizeof(arr[0]).

**Q6:** Assign arrays with =?

**A:** No, must copy.

**Q7:** strcmp equal?

**A:** 0.

**Q8:** 2D array storage?

**A:** Row-major order.

**Q9:** Null terminator?

**A:** '\0' marks string end.

**Q10:** arr vs &arr?

**A:** arr decays to pointer; &arr is full array.
