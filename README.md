# Programarea calculatoarelor

## Curs 1 - Introducere

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
- completed with libc.libc
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

int main(){
    printf("Hello world\n");

    return 0;
}
```
### Compiling of a C program
```
+-------------+      +----------------+        Compiler        +--------------------+       Linker        +------------------+
|   Editor    | ---> |  Source file   | ---------------------> |   Object file      | ------------------> |  Executable file |
+-------------+      +----------------+        ^               |  (incomplete)      |   ^           ^     |  (complete,      |
                                               |               +--------------------+   |           |     |   final)         |
                                               |                                        |           |     +------------------+
                                               |                                        |           |
                                               |                                        |           |
                                        +--------------+                    +----------------+     +----------------+
                                        |              |                    |  Standard      |     | Other          |
                                        |   Headers    |                    |  library       |     | libraries,     |
                                        |              |                    |  (printf,      |     | object files   |
                                        +--------------+                    |  scanf, etc.)  |     +----------------+
                                                                            +----------------+

```
