# Topic 10: Structs & Enums

Structs group data. Enums define named constants. Unions share memory. typedef aliases types. Bitfields pack flags into bits.

## Learn From

Struct references.

- C++ Structs — https://cplusplus.com/doc/tutorial/structures/

## Key Concepts

- Struct declaration
- Struct access
- Enum declaration
- Scoped enums
- Union memory
- typedef and using
- Bitfields

## Practice Problems & Solutions

### Problem 1

Struct Point x,y.

**Solution:**

```
#include <iostream>
struct Point{int x;int y;};
int main(){Point p={3,7};std::cout<<p.x<<" "<<p.y<<std::endl;return 0;}
```

**Expected output:**

```
3 7
```

**Learning points:** 

### Problem 2

Enum Color GREEN=1.

**Solution:**

```
#include <iostream>
enum Color{RED,GREEN,BLUE};
int main(){std::cout<<GREEN<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 3

Union int/float.

**Solution:**

```
#include <iostream>
union Data{int i;float f;};
int main(){Data d;d.i=42;std::cout<<d.i<<std::endl;d.f=3.14f;std::cout<<d.f<<std::endl;return 0;}
```

**Expected output:**

```
42
3.14
```

**Learning points:** 

### Problem 4

typedef alias.

**Solution:**

```
#include <iostream>
typedef int Integer;
int main(){Integer x=10;std::cout<<x<<std::endl;return 0;}
```

**Expected output:**

```
10
```

**Learning points:** 

### Problem 5

Bitfield flags.

**Solution:**

```
#include <iostream>
struct Flags{unsigned int active:1;unsigned int mode:2;};
int main(){Flags f={1,3};std::cout<<f.active<<" "<<f.mode<<std::endl;return 0;}
```

**Expected output:**

```
1 3
```

**Learning points:** 

### Problem 6

Scoped enum class.

**Solution:**

```
#include <iostream>
enum class Direction{North,South,East,West};
int main(){Direction d=Direction::North;std::cout<<static_cast<int>(d)<<std::endl;return 0;}
```

**Expected output:**

```
0
```

**Learning points:** 

### Problem 7

Struct Rectangle area.

**Solution:**

```
#include <iostream>
struct Rectangle{int w;int h;};
int main(){Rectangle r={5,3};std::cout<<r.w*r.h<<std::endl;return 0;}
```

**Expected output:**

```
15
```

**Learning points:** 

### Problem 8

Struct Student print.

**Solution:**

```
#include <iostream>
#include <string>
struct Student{std::string name;int grade;};
int main(){Student s={"Alice",95};std::cout<<s.name<<" "<<s.grade<<std::endl;return 0;}
```

**Expected output:**

```
Alice 95
```

**Learning points:** 

### Problem 9

Union as bytes.

**Solution:**

```
#include <iostream>
union IntBytes{int i;unsigned char bytes[4];};
int main(){IntBytes u;u.i=0x41424344;for(int i=0;i<4;i++)std::cout<<(int)u.bytes[i]<<std::endl;return 0;}
```

**Expected output:**

```
68
67
66
65
```

**Learning points:** 

### Problem 10

using alias double.

**Solution:**

```
#include <iostream>
using F64=double;
int main(){F64 pi=3.14159;std::cout<<pi<<std::endl;return 0;}
```

**Expected output:**

```
3.14159
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** struct vs class?

**A:** Struct public default; class private default.

**Q2:** enum purpose?

**A:** Named integer constants.

**Q3:** scoped enum?

**A:** Values scoped within enum.

**Q4:** union memory?

**A:** All members share same memory.

**Q5:** bitfield?

**A:** Struct member with specified bits.

**Q6:** typedef purpose?

**A:** Alias for existing type.

**Q7:** Struct own type?

**A:** Only as pointer.

**Q8:** Empty struct size?

**A:** At least 1 byte.

**Q9:** Pass struct by value?

**A:** Yes, entire struct copied.

**Q10:** Default enum values?

**A:** From 0, incrementing.
