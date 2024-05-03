# week 1 > C <
## introduction to C langauage 

### BASED ON --->
* HELLO WORLD
* Operations & Types 
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
* Here the `int main` is our main function.
* Below the the structure of main funtion.
  ```
  int main (void)
  {
     // code body
  }
  ```
* Where as; `printf` function is basically yse to print anything on the `output terminal`
* the syntax for printing any string or variable  is given below.
```
    printf(" string " );  
      
```
* string can be anything u might print.
* ` ; ` in the end is compulsory or else ` syntax error ` will be generated.
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

# operations & types 
* `Operators` refer to the `mathematical operations` that are supported by your compiler. In C, these mathematical operators include:

* `+ `for addition
* `- `for subtraction
* `* `for multiplication
* `/ `for division
* `%` for remainder

## Types refer to the possible data that can be stored within a variable.
* For example, a char is designed to accommodate a single character like a or 2.
* Types are very important because each type has specific limits.
* For example, because of the limits in memory, the highest value of an int can be 4294967296. also known as |[intergers overflow](/intergers overflow.md)| 

 ### Types with which you might interact during this course include:

* `bool`, a Boolean expression of either true or false
* `char`, a single character like a or 2
* `double`, a floating-point value with more digits than a float
* `float`, a floating-point value, or real number with a decimal value
* `int`, integers up to a certain size, or number of bits
* `long`, integers with more bits, so they can count higher than an int
* `string`, a string of characters

* here is a simple code related to following expressions and types
```
#include <stdio.h>

int main(void)
{
    // ask user for x
    int x = get_int("x: ");

    // ask user for y
    int y = get_int("y: ");

    // Perform addition
    printf("%i\n", x + y);
}
```
* Notice how the `get_int` function is utilized to obtain an integer from the user twice. One integer is stored in the int variable called `x`. Another is stored in the int variable called `y`. Then, the `printf` function prints the value of `x + y`, designated by the `%i` symbol.

# Conditions 
* hey allow programs to make decisions and execute different parts of the code based on whether a certain condition is true or false. 
* You might want to do one thing if x is greater than y. Further, you might want to do something else if that condition is not met.
```
#include <stdio.h>

int main(void)
{
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    if (x < y)
    {
        printf("x is less than y\n");
    }
}
```
* Notice that we create two variables, an `int or integer called x and another called y`. The values of these are populated using the `get_int` function.

#### lets make it a bit better 
```
#include <stdio.h>

int main(void)
{
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    if (x < y)
    {
        printf("x is less than y\n");
    }
    else if (x > y)
    {
        printf("x is greater than y\n");
    }
    else
    {
        printf("x is equal to y\n");
    }
}
```
* now the following program design is a bit more logical.
* we have implemented three conditions now,
* if our `if conditons` is true it will exicute only similairly with `else if`, if both conditons are false `else` will run automatically.

# loops 
*  We can also utilize the loops building block from Scratch in our C programs.
```
#include <stdio.h>

int main(void)
{
    printf("meow\n");
    printf("meow\n");
    printf("meow\n");
}
```
* Notice this does as intended but has an opportunity for better design.

* We can improve our program by modifying your code as follows:
#### while loop
```
#include <stdio.h>

int main(void)
{
    int i = 0;
    while (i < 3)
    {
        printf("meow\n");
        i++;
    }
}
```
* We created an `int` called `i` and assign it the value `0`.
* Then, we create a `while loop` that will run as long as `i < 3`. Then, the loop runs. Every time `1` is added to `i` using the `i++` statement.

 #### Similarly, we can implement a count-down of sorts by modifying our code as follows:
```
#include <stdio.h>

int main(void)
{
    int i = 3;
    while (i > 0)
    {
        printf("meow\n");
        i--;
    }
}
```
* Notice how our counter `i` is started at `3`. Each time the loop runs, it will reduce the counter by `1`. Once the counter is less than zero, it will stop the loop.

* We can further improve the design using a for loop. Modify your code as follows:
### for loop
```
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("meow\n");
    }
}
```
* for loop includes three arguments. The first argument `int i = 0` starts our counter at `zero`. The second argument `i < 3` is the condition that is being checked. Finally, the argument `i++` tells the loop to `increment by one` each time the loop runs.
#### infinite loop
* We can even loop forever using the following code:
```
#include <stdio.h>

int main(void)
{
    while (true)
    {
        printf("meow\n");
    }
}
```
* In this case the condition always remain true due to which the code never ends since the is no false statement to terminate it!
