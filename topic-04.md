# Topic 4: Control Flow

Control flow determines execution order. Conditionals (if/else, switch) make decisions; loops (for, while, do-while) repeat code. break exits; continue skips iteration.

## Learn From

Control flow references.

- C++ Control — https://cplusplus.com/doc/tutorial/control/

## Key Concepts

- if/else if/else
- switch-case with default
- for loop
- while loop
- do-while loop
- break and continue
- Nested control

## Practice Problems & Solutions

### Problem 1

Print Even if 4 is even.

**Solution:**

```
#include <iostream>
int main(){int n=4;if(n%2==0)std::cout<<"Even"<<std::endl;else std::cout<<"Odd"<<std::endl;return 0;}
```

**Expected output:**

```
Even
```

**Learning points:** 

### Problem 2

For loop 1 to 5.

**Solution:**

```
#include <iostream>
int main(){for(int i=1;i<=5;i++)std::cout<<i<<std::endl;return 0;}
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

### Problem 3

Print first 5 even numbers.

**Solution:**

```
#include <iostream>
int main(){for(int i=1;i<=5;i++)std::cout<<i*2<<std::endl;return 0;}
```

**Expected output:**

```
2
4
6
8
10
```

**Learning points:** 

### Problem 4

While countdown 5 to 1.

**Solution:**

```
#include <iostream>
int main(){int i=5;while(i>=1){std::cout<<i<<std::endl;i--;}return 0;}
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

### Problem 5

Switch day=3 (Monday=1).

**Solution:**

```
#include <iostream>
int main(){int day=3;switch(day){case 1:std::cout<<"Monday"<<std::endl;break;case 2:std::cout<<"Tuesday"<<std::endl;break;case 3:std::cout<<"Wednesday"<<std::endl;break;default:std::cout<<"Other"<<std::endl;break;}return 0;}
```

**Expected output:**

```
Wednesday
```

**Learning points:** 

### Problem 6

Break when i=3 (1-5).

**Solution:**

```
#include <iostream>
int main(){for(int i=1;i<=5;i++){if(i==3)break;std::cout<<i<<std::endl;}return 0;}
```

**Expected output:**

```
1
2
```

**Learning points:** 

### Problem 7

Continue skip 3 (1-5).

**Solution:**

```
#include <iostream>
int main(){for(int i=1;i<=5;i++){if(i==3)continue;std::cout<<i<<std::endl;}return 0;}
```

**Expected output:**

```
1
2
4
5
```

**Learning points:** 

### Problem 8

Do-while 1 to 3.

**Solution:**

```
#include <iostream>
int main(){int i=1;do{std::cout<<i<<std::endl;i++;}while(i<=3);return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

### Problem 9

Print Positive if 7>0.

**Solution:**

```
#include <iostream>
int main(){int n=7;if(n>0)std::cout<<"Positive"<<std::endl;return 0;}
```

**Expected output:**

```
Positive
```

**Learning points:** 

### Problem 10

Sum 1 to 5 with for loop.

**Solution:**

```
#include <iostream>
int main(){int sum=0;for(int i=1;i<=5;i++)sum+=i;std::cout<<sum<<std::endl;return 0;}
```

**Expected output:**

```
15
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** while vs do-while?

**A:** while checks first; do-while executes at least once.

**Q2:** break in switch?

**A:** Exits switch block.

**Q3:** continue in loop?

**A:** Skips current iteration.

**Q4:** switch on strings?

**A:** No, only integral types.

**Q5:** default case?

**A:** Handles unmatched values.

**Q6:** Missing break in case?

**A:** Falls through to next case.

**Q7:** Nested for loops?

**A:** Yes, arbitrary depth.

**Q8:** Loop variable scope?

**A:** Local to for loop.

**Q9:** When use do-while?

**A:** When body must run at least once.

**Q10:** Float loop counter?

**A:** Yes but not recommended.
