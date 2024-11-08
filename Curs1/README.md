# Programarea calculatoarelor

## [Curs 1 - Introducere](https://wiki.mta.ro/c/1/prog/curs/curs1)

### Key points of the C programming language
- widely used 
- various systems programming
- compiles to native code 
- small no of keywords:
```
auto        double      int         struct
break       else        long        switch
case        enum        register    typedef
char        extern      return      union
const       float       short       unsigned
continue    for         signed      void
default     goto        sizeof      volatile
do          if          static      while
```
- completed with libc.libc:
```
printf/scanf, gets/puts, strcpy, strcmp, memcpy, malloc...
```
- function oriented
- flow control: branches(if-else, switch)
- flow contorl: iterative(for, while, do-while)
- arrays
- structures
- pointers
- structures, unions

### A first program

```C
#include <stdlib.h>

int main()
{
    printf("Hello world\n");

    return 0;
}
```

### Compiling of a C program

```
+----------------+    Compiler    +----------------+       Linker      +------------------+
|  Source file   | -------------> |   Object file  | ----------------> |  Executable file |
+----------------+        ^       |  (incomplete)  |      ^     ^      |  (complete,      |
        ^                 |       +----------------+     /       \     |   final)         |
        |                 |                             /         \    +------------------+
        |                 |                            /           \ 
        |                 |                           /             \
 +------------+     +--------------+        +----------------+  +----------------+
 |            |     |              |        |  Standard      |  | Other          |
 |  Editor    |     |   Headers    |        |  library       |  | libraries,     |
 |            |     |              |        |  (printf,      |  | object files   |
 +------------+     +--------------+        |  scanf, etc.)  |  +----------------+
                                            +----------------+

```
> [More on C compiling](https://en.wikipedia.org/wiki/C_standard_library)

### C vs Assembly

```
<< C >>                 << Assembly (simplified) >>
--------------------+---------------------------------
                    |  .bss
int a, b;           |      dw a,b;
int foo()           |  .code
{                   |  foo:
    if(a<b)         |      %function prolog%
        return a;   |      mov     eax,dword prt[b]
    else            |      cmp     eax,dword prt[a]
        return b;   |      jl      L3
}                   |      mov     eax,dword prt[b]
                    |  L3:
                    |      %function epilog%
                    |      ret
```

### C Standard library (libc.lib)

- Mathematical functions: **sqrt**, **pow**, **sin**, **tan**
- Manipulating characters: **isdigit**, **isalpha**, **toupper**, **tolower**
- Manipulating stirngs: **strlen**, **strcpy**, **strcmp**, **strcat**, **strstr**
- Formatted I/O: **printf**, **scanf**, **sprintf**, **sscanf**
- File I/O: **fopen**, **fclose**, **fgets**, **fputs**, **fseek**
- Error handling: **assert**, **exit**
- Time and Date functions: **clock**, **time**, **difftime**
- Sort and search: **qsort**, **bsearch**
- Low-level memory operations: **memcpy**, **memset**
> [!NOTE]
> Various header files must be included in the program source:
>  <stdio.h>,
>  <stdlib.h>,
>  <string.h>,
>  <math.h>,
>  <time.h>,
>  . . .

> [More on libc](https://en.wikipedia.org/wiki/C_standard_library)

### The Structure of the C programs:

- **Pre-Processor Directives**
    - includes
    - defines
    - comments
- **Program's global data**
    - global variables
- **Declarations**
    - functions
    - variables
- **main() function**
    - C program's starting point
    - Executable's entry point
    - Call other functions
- **Other functions**
    - each handles a specific task

> [About flowcharts](https://www.smartdraw.com/flowchart/?srsltid=AfmBOoqcB1sb0C54hShV_Wjc-8Nfrgkv-hNHzXHjMjYgAzeOgbnWmVJN)