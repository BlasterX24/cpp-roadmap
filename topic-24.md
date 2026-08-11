# Topic 24: WinAPI Basics for RE

Windows API essential for RE. Key functions: MessageBox, CreateFile/ReadFile, ReadProcessMemory, PE format structures.

## Learn From

WinAPI references.

- Microsoft WinAPI — https://docs.microsoft.com/en-us/windows/win32/api/

## Key Concepts

- MessageBox
- CreateFile and ReadFile
- ReadProcessMemory
- PE format structures
- Virtual Address
- Import/Export tables
- PE loading process

## Practice Problems & Solutions

### Problem 1

MessageBox.

**Solution:**

```
#include <windows.h>
int WINAPI WinMain(HINSTANCE h,HINSTANCE p,LPSTR cmd,int show){MessageBox(NULL,"Hello RE","Title",MB_OK);return 0;}
```

**Learning points:** 

### Problem 2

CreateFile open.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){HANDLE h=CreateFile("test.txt",GENERIC_READ,0,NULL,OPEN_EXISTING,0,NULL);if(h!=INVALID_HANDLE_VALUE){std::cout<<"opened"<<std::endl;CloseHandle(h);}return 0;}
```

**Expected output:**

```
opened
```

**Learning points:** 

### Problem 3

ReadFile content.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){HANDLE h=CreateFile("test.txt",GENERIC_READ,0,NULL,OPEN_EXISTING,0,NULL);char b[256]={0};DWORD r;ReadFile(h,b,255,&r,NULL);std::cout<<b<<std::endl;CloseHandle(h);return 0;}
```

**Learning points:** 

### Problem 4

GetModuleHandle.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){HMODULE h=GetModuleHandle(NULL);std::cout<<h<<std::endl;return 0;}
```

**Learning points:** 

### Problem 5

GetCurrentProcessId.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){std::cout<<GetCurrentProcessId()<<std::endl;return 0;}
```

**Learning points:** 

### Problem 6

GetLastError.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){CreateFile("noexist.txt",GENERIC_READ,0,NULL,OPEN_EXISTING,0,NULL);std::cout<<GetLastError()<<std::endl;return 0;}
```

**Expected output:**

```
2
```

**Learning points:** 

### Problem 7

GetSystemInfo.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){SYSTEM_INFO si;GetSystemInfo(&si);std::cout<<si.dwNumberOfProcessors<<std::endl;return 0;}
```

**Learning points:** 

### Problem 8

VirtualAlloc.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){void *p=VirtualAlloc(NULL,4096,MEM_COMMIT,PAGE_READWRITE);if(p)std::cout<<"allocated"<<std::endl;VirtualFree(p,0,MEM_RELEASE);return 0;}
```

**Expected output:**

```
allocated
```

**Learning points:** 

### Problem 9

FindWindow.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){HWND h=FindWindow(NULL,"Untitled - Notepad");std::cout<<(h?"found":"not found")<<std::endl;return 0;}
```

**Expected output:**

```
not found
```

**Learning points:** 

### Problem 10

GetVersionEx.

**Solution:**

```
#include <windows.h>
#include <iostream>
int main(){OSVERSIONINFO oi;oi.dwOSVersionInfoSize=sizeof(oi);GetVersionEx(&oi);std::cout<<oi.dwMajorVersion<<"."<<oi.dwMinorVersion<<std::endl;return 0;}
```

**Expected output:**

```
6.1
```

**Learning points:** 

## Quick Questions & Answers

**Q1:** WinAPI?

**A:** Windows system calls.

**Q2:** CreateFile?

**A:** Opens/creates files/devices.

**Q3:** ReadProcessMemory?

**A:** Reads another process memory.

**Q4:** PE format?

**A:** Windows binary format.

**Q5:** Virtual Address?

**A:** Process memory address.

**Q6:** IMAGE_NT_HEADERS?

**A:** PE header with entry point.

**Q7:** Import Table?

**A:** Lists imported DLLs/functions.

**Q8:** Export Table?

**A:** Lists exported functions.

**Q9:** GetModuleHandle?

**A:** Returns module base address.

**Q10:** VA vs RVA?

**A:** Virtual vs offset from base.
