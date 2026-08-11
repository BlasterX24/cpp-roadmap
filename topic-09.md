# Topic 9: Strings (std::string)

std::string manages memory with rich methods. Concatenate with +, find with find(), substr() extracts, compare with ==.

## Learn From

String references.

- C++ std::string — https://cplusplus.com/reference/string/string/

## Key Concepts

- Constructors
- length() and size()
- Concatenation +
- substr(pos, len)
- find() and rfind()
- Comparison operators
- at() and [] access
- c_str() conversion

## Practice Problems & Solutions

### Problem 1

Create Hello and print.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello";std::cout<<s<<std::endl;return 0;}
```

**Expected output:**

```
Hello
```

**Learning points:** 

### Problem 2

Print length of Programming.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Programming";std::cout<<s.length()<<std::endl;return 0;}
```

**Expected output:**

```
11
```

**Learning points:** 

### Problem 3

Concatenate strings.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello"+std::string(" World");std::cout<<s<<std::endl;return 0;}
```

**Expected output:**

```
Hello World
```

**Learning points:** 

### Problem 4

Substring from Hello World.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello World";std::cout<<s.substr(6,5)<<std::endl;return 0;}
```

**Expected output:**

```
World
```

**Learning points:** 

### Problem 5

Find W in Hello World.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello World";std::cout<<s.find('W')<<std::endl;return 0;}
```

**Expected output:**

```
6
```

**Learning points:** 

### Problem 6

Compare strings.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string a="abc",b="abd";std::cout<<(a==b?"equal":"not equal")<<std::endl;return 0;}
```

**Expected output:**

```
not equal
```

**Learning points:** 

### Problem 7

Access third char of Hello.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello";std::cout<<s[2]<<std::endl;return 0;}
```

**Expected output:**

```
l
```

**Learning points:** 

### Problem 8

Append ! to Hello.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello";s+="!";std::cout<<s<<std::endl;return 0;}
```

**Expected output:**

```
Hello!
```

**Learning points:** 

### Problem 9

Convert to C-string.

**Solution:**

```
#include <iostream>
#include <string>
#include <cstring>
int main(){std::string s="Hi";const char *cs=s.c_str();for(int i=0;i<(int)strlen(cs);i++)std::cout<<cs[i]<<std::endl;return 0;}
```

**Expected output:**

```
H
i
```

**Learning points:** 

### Problem 10

Check starts with H.

**Solution:**

```
#include <iostream>
#include <string>
int main(){std::string s="Hello";std::cout<<(s.find('H')==0?"yes":"no")<<std::endl;return 0;}
```

**Expected output:**

```
yes
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** size() vs length()?

**A:** Identical.

**Q2:** substr() bad position?

**A:** std::out_of_range.

**Q3:** find() not found?

**A:** std::string::npos.

**Q4:** Concat C-string + string?

**A:** Yes, using +.

**Q5:** at() vs []?

**A:** at() bounds checks; [] does not.

**Q6:** c_str()?

**A:** Returns const pointer to C-string.

**Q7:** Clear string?

**A:** clear() or assign empty.

**Q8:** String holds null chars?

**A:** Yes but c_str() expects null-terminated.

**Q9:** == vs compare()?

**A:** == returns bool; compare() returns 0/neg/pos.

**Q10:** Max string size?

**A:** Limited by size_t.
