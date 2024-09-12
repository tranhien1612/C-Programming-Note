# C-Programming-Note

## Using *void to point to function
```
/******************************************************************************

Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,
C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <stdio.h>

void hello();
void hello1();

typedef struct {
    void (*fnc)();
    void (*fnc1)();
} event;

event e = {
    .fnc = hello,
    .fnc1 = hello1
};

void hello(int a){
   printf("Hello World %d\n", a); 
}
void hello1(){
   printf("Hello World1\n"); 
}

int main()
{
    e.fnc(5);
    e.fnc1();

    return 0;
}

```
