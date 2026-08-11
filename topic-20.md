# Topic 20: File I/O

File I/O uses fstream. ifstream reads; ofstream writes. getline reads lines. Binary uses read()/write(). Check is_open().

## Learn From

File I/O references.

- C++ fstream — https://cplusplus.com/doc/tutorial/files/

## Key Concepts

- ifstream/ofstream/fstream
- open() and close()
- getline()
- is_open()
- ios::binary
- read() and write()
- File modes

## Practice Problems & Solutions

### Problem 1

Write to file.

```
#include <fstream>
int main(){std::ofstream out("test.txt");out<<"Hello File";out.close();return 0;}
```

**Learning points:** 

### Problem 2

Read from file.

```
#include <fstream>
#include <iostream>
#include <string>
int main(){std::ifstream in("test.txt");std::string l;std::getline(in,l);std::cout<<l<<std::endl;in.close();return 0;}
```

**Expected output:**

```
Hello File
```

**Learning points:** 

### Problem 3

Append to file.

```
#include <fstream>
int main(){std::ofstream out("test.txt",std::ios::app);out<<"Append";out.close();return 0;}
```

**Learning points:** 

### Problem 4

Read lines.

```
#include <fstream>
#include <iostream>
#include <string>
int main(){std::ofstream out("lines.txt");out<<"Line1\nLine2\nLine3";out.close();std::ifstream in("lines.txt");std::string l;while(std::getline(in,l))std::cout<<l<<std::endl;in.close();return 0;}
```

**Expected output:**

```
Line1
Line2
Line3
```

**Learning points:** 

### Problem 5

Check file opened.

```
#include <fstream>
#include <iostream>
int main(){std::ifstream in("noexist.txt");std::cout<<(in.is_open()?"opened":"failed")<<std::endl;return 0;}
```

**Expected output:**

```
failed
```

**Learning points:** 

### Problem 6

Write numbers 1-5.

```
#include <fstream>
int main(){std::ofstream out("nums.txt");for(int i=1;i<=5;i++)out<<i<<"\n";out.close();return 0;}
```

**Learning points:** 

### Problem 7

Read back numbers.

```
#include <fstream>
#include <iostream>
int main(){std::ifstream in("nums.txt");int n;while(in>>n)std::cout<<n<<std::endl;in.close();return 0;}
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

### Problem 8

Binary write.

```
#include <fstream>
int main(){int d[]={1,2,3};std::ofstream out("bin.dat",std::ios::binary);out.write((char*)d,sizeof(d));out.close();return 0;}
```

**Learning points:** 

### Problem 9

Binary read.

```
#include <fstream>
#include <iostream>
int main(){int d[3];std::ifstream in("bin.dat",std::ios::binary);in.read((char*)d,sizeof(d));in.close();for(int i=0;i<3;i++)std::cout<<d[i]<<std::endl;return 0;}
```

**Expected output:**

```
1
2
3
```

**Learning points:** 

### Problem 10

Check file size.

```
#include <fstream>
#include <iostream>
int main(){std::ifstream in("bin.dat",std::ios::binary|std::ios::ate);std::cout<<in.tellg()<<std::endl;in.close();return 0;}
```

**Expected output:**

```
12
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** ifstream vs ofstream?

**A:** Read vs write.

**Q2:** getline()?

**A:** Reads line with spaces.

**Q3:** is_open()?

**A:** Check if opened.

**Q4:** ios::binary?

**A:** Binary mode.

**Q5:** read/write()?

**A:** Binary I/O.

**Q6:** ios::app?

**A:** Append mode.

**Q7:** ios::trunc?

**A:** Truncate on open.

**Q8:** Close when?

**A:** When done.

**Q9:** tellg()?

**A:** Read position.

**Q10:** seekg()?

**A:** Move read position.
