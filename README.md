# C-Programming-Note

## Using *void to point to function
```
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
## Flexible Array Memory
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>

typedef struct {
    char num1;
    char num2;
    char num3[];
} str1;

typedef struct {
    char num1;
    char num2;
    char *num3;
} str2;


int main()
{
    str1 *t1 = (str1 *) malloc( sizeof(*t1) + (sizeof(char) * strlen("David")) );
    t1->num1 = 'A';
    t1->num2 = 'B';
    strcpy(t1->num3, "David");
    str2 t2 = {
        .num1 = 'A',
        .num2 = 'B'
    };
    t2.num3 = (char *) malloc( sizeof(char) * strlen("David") );
    strcpy(t2.num3, "David");
    
    printf("Begin Size: %ld, %ld\n", sizeof(t1), sizeof(t2)); 
    printf("T1: %c, %c, %s\n", t1->num1, t1->num2, t1->num3);
    printf("T2: %c, %c, %s\n", t2.num1, t2.num2, t2.num3);

    return 0;
}
// Begin Size: 8, 16
// T1: A, B, David
// T2: A, B, David
```
