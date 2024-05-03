# week 1 > C <
## introduction to C langauage 

### BASED ON --->
* HELLO WORLD
* SCRATCH TO C
* VS CODE (CS-50)
* CONDITIONS
* VARAIBLES
* LOOPS
* FUNCTIONS COMPOSITIONS
   
# Hello World 
* to write the 1st program we will make a simple print of `HELLO WORLD`>
  ```
  #include <stdio.h>

  int main (void)
  {
    printf("hello world");  
  return 0;
  }
  ```
# Variables
* variables are used to store data in them.
* When a user insert Data the Data had to be stored somewhere and thats where variables are used.
* common example is a simple code asking user its name and storing it in a variable.
```
#include <stdio.h>

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, %s\n", answer);
 return 0;
}
```
* We have taken string as a variables since its use for store data related to alphabets and words.
* Here is the explanation
* The get_string function is used to get a string from the user.
* Then, the variable answer is passed to the printf function.
* %s tells the printf function to prepare itself to receive a string.
* Answer is a special holding place we call a variable. answer is of type string and can hold any string within it.
* There are many data types, such as int, bool, char, and many others.
* You can run your program by typing ./hello. The program now asks for your name and then says hello with your name attached.
   
