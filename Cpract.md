# C practice 
> using the cs50 "headerfile"
```
#include <stdio.h>
#include <cs50.h>

int main(void){

 string name = get_string("whats your name >> ");
 int age = get_int("whats your age >> ");
 float height = get_float("whats your height >> ");

printf("well Hi , %s  soo u r %d year old , and ur %f cm \n" , name , age , height );

}

```
```
#include <stdio.h>
#include <cs50.h>

int main(void){

int n1 = get_int ("write an interger > ");
int n2 = get_int ("write an interger > ");

char keys = get_char ("arthimatice operator > ");

switch(keys){
    case '+': printf("SUM >> %d \n" , n1 + n2);
    break;
    case '-': printf("SUB >> %d \n" , n1 - n2);
    break;
    case '*': printf("MULTI >> %d \n" , n1 * n2);
    break;
    case '/': printf("DIV >> %d \n" , n1 / n2);
    break;
    default : printf("invaild ");
    break;
}
 }
```

