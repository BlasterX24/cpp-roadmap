# Topic 23: Bitwise Operations & Manipulation

Bitwise operations work on bits. Shifts move bits. Masks isolate bits. Common tricks: even/odd, power of 2, set/clear/toggle.

## Learn From

Bitwise references.

- C++ Bitset — https://cplusplus.com/reference/bitset/bitset/

## Key Concepts

- AND & OR | XOR ^ NOT ~
- Left << Right >> shifts
- Bit masks
- Set/clear/toggle
- std::bitset
- Common tricks
- Bit counting

## Practice Problems & Solutions

### Problem 1

Set bit 3.

**Solution:**

```
#include <iostream>
int main(){int v=0;v|=(1<<3);std::cout<<v<<std::endl;return 0;}
```

**Expected output:**

```
8
```

**Learning points:** 

### Problem 2

Clear bit 3.

**Solution:**

```
#include <iostream>
int main(){int v=0xFF;v&=~(1<<3);std::cout<<v<<std::endl;return 0;}
```

**Expected output:**

```
247
```

**Learning points:** 

### Problem 3

Toggle bit 0.

**Solution:**

```
#include <iostream>
int main(){int v=5;v^=(1<<0);std::cout<<v<<std::endl;return 0;}
```

**Expected output:**

```
4
```

**Learning points:** 

### Problem 4

Check bit 2 set.

**Solution:**

```
#include <iostream>
int main(){int v=5;bool s=(v&(1<<2))!=0;std::cout<<s<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

### Problem 5

Even/odd check.

**Solution:**

```
#include <iostream>
int main(){int n=4;std::cout<<(n%2==0?"even":"odd")<<std::endl;return 0;}
```

**Expected output:**

```
even
```

**Learning points:** 

### Problem 6

Count set bits 7.

**Solution:**

```
#include <iostream>
int main(){int n=7;int c=0;while(n){c+=n&1;n>>=1;}std::cout<<c<<std::endl;return 0;}
```

**Expected output:**

```
3
```

**Learning points:** 

### Problem 7

Bitset binary 10.

**Solution:**

```
#include <iostream>
#include <bitset>
int main(){std::cout<<std::bitset<8>(10)<<std::endl;return 0;}
```

**Expected output:**

```
00001010
```

**Learning points:** 

### Problem 8

XOR swap.

**Solution:**

```
#include <iostream>
int main(){int a=3,b=5;a^=b;b^=a;a^=b;std::cout<<a<<" "<<b<<std::endl;return 0;}
```

**Expected output:**

```
5 3
```

**Learning points:** 

### Problem 9

Extract byte 1.

**Solution:**

```
#include <iostream>
int main(){int v=0x12345678;int b=(v>>8)&0xFF;std::cout<<std::hex<<b<<std::endl;return 0;}
```

**Expected output:**

```
56
```

**Learning points:** 

### Problem 10

Power of 2 check.

**Solution:**

```
#include <iostream>
int main(){int n=8;bool p=(n>0)&&((n&(n-1))==0);std::cout<<p<<std::endl;return 0;}
```

**Expected output:**

```
1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** & purpose?

**A:** AND: clear/check bits.

**Q2:** | purpose?

**A:** OR: set bits.

**Q3:** ^ purpose?

**A:** XOR: toggle, swap.

**Q4:** ~ purpose?

**A:** NOT: flip all bits.

**Q5:** << purpose?

**A:** Left shift: *2^n.

**Q6:** >> purpose?

**A:** Right shift: /2^n.

**Q7:** Bitmask?

**A:** Value with specific bits.

**Q8:** Check bit n?

**A:** (val & (1 << n)) != 0.

**Q9:** Set bit n?

**A:** val |= (1 << n).

**Q10:** Clear bit n?

**A:** val &= ~(1 << n).
