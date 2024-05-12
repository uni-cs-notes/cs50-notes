# week 2 ARRAYS

# compiling 
* A compiler, a specialized computer program that `converts source code into machine code` that can be understood by a computer.
* For example, you might have a computer program that looks like this:
```
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
```
* A compiler will take the above code and turn it into the following machine code:
  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/250d180d-8ba5-446a-a5d9-6e3303e89c09)

# using clang (LINUX)
* The Clang tool is a front end compiler that is used to compile programming languages such as C++, C, Objective C++ and Objective C into machine code.
* Clang is also used as a compiler for frameworks like OpenMP, OpenCL, RenderScript, CUDA and HIP
* Consider the following code:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string name = get_string("What's your name? ");
    printf("hello, %s\n", name);
}
```
* You can attempt to enter into the terminal window: clang -o hello hello.c. You will be met by an error that indicates that clang does not know where to find the cs50.h library.
* Attempting again to compile this code, run the following command in the terminal window: clang -o hello hello.c -lcs50. This will enable the compiler to access the cs50.h library.
* Running in the terminal window ./hello, your program will run as intended.
* While the above is offered as an illustration, such that you can understand more deeply the process and concept of compiling code, using make in CS50 is perfectly fine and the expectation!

## steps of compilation 
* Compiling involves major steps, including the following:
* First, preprocessing is where the header files in your code, designated by a # (such as #include \<cs50.h\>) are effectively copied and pasted into your file.
* *During this step, the code from `cs50.h` is copied into your program. Similarly, just as your code contains` #include \<stdio.h\>`, code contained within stdio.h somewhere on your computer is copied to your program. 
* `This step can be visualized as follows`:
```
...
string get_string(string prompt);
int printf(string format, ...);
...

int main(void)
{
    string name = get_string("What's your name? ");
    printf("hello, %s\n", name);
}
```
* Second, `compiling` is where your program is converted into assembly code. This step can be visualized as follows:

![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/0ab492cb-5ca2-4609-a766-248d05f64235)



* Third, `assembling` involves the compiler converting your assembly code into machine code. This step can be visualized as follows:

![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/e32542cc-f29f-42bd-8cda-adb809a49683)


Finally, during the `linking step`, code from your included libraries are converted also into machine code and combined with your code. The final executable file is then outputted.

![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/668b7b8b-487f-4e5b-8107-4c6a796ef97a)


# debugging
* debugging means to remove errors from your code
* everyone does make mistakes int coding thats why debugging is also an impoertant factoer in programming
* consider the following code that has a bug purposely inserted within it:
```
#include <stdio.h>

int main(void)
{
    for (int i = 0; i <= 3; i++)
    {
        printf("#\n");
    }
}
```
* Type code `buggy0.c` into the `terminal window` and write the above code.
* Running this code, four bricks appear instead of the intended three.
* `printf is a very useful way of debugging your code`.
* You could modify your code as follows:
```
#include <stdio.h>

int main(void)
{
    for (int i = 0; i <= 3; i++)
    {
        printf("i is %i\n", i);
        printf("#\n");
    }
}
```
* Running this code, you will see numerous statements, including i is 0, i is 1, i is 2, and i is 3. Seeing this, you might realize that Further code needs to be corrected as follows:
```
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("#\n");
    }
}
```
* Notice the <= has been replaced with <.

* `A second tool in debugging is called a debugger`, a software tool created by programmers to help track down bugs in code.
* `In VS Code, a preconfigured debugger has been provided to you`.
# Arrays
* In Week 0, we talked about data types such as bool, int, char, string, etc.
* Each data type requires a certain amount of system resources:
* `bool` 1 byte
* `int` 4 bytes
* `long` 8 bytes
* `float` 4 bytes
* `double` 8 bytes
* `char` 1 byte
* `string` ? bytes
* Inside of your computer, you have a finite amount of memory available.
* Physically, on the memory of your computer, you can imagine how specific types of data are stored on your computer. You might imagine that a char, which only requires 1 byte of memory, may look as follows:
![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/589b9d2c-0b77-4fc1-b13b-a3c0358e8371)


* Similarly, an int, which requires 4 bytes might look as follows:
  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/1a7c7d6e-da65-4af5-abb5-1e0deffe1d19)

  *We can create a program that explores these concepts. Inside your terminal, type code scores.c and write code as follows:
```
#include <stdio.h>

int main(void)
{
    // Scores
    int score1 = 72;
    int score2 = 73;
    int score3 = 33;

    // Print average
    printf("Average: %f\n", (score1 + score2 + score3) / 3.0);
}
```
* Notice that the number on the right is a `floating point value of 3.0`, such that the calculation is rendered as a floating point value in the end.

* Running make scores, the program runs.
* You can imagine how these variables are stored in memory:

![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/109a964e-cfc2-422b-ad5c-f81caf324b11)
## how arrays are useful??
* Arrays are a way of storing data back-to-back in memory such that this data is easily accessible.
* `int scores[3]` is a way of telling the compiler to provide you `three back-to-back places in memory of size int to store three scores`.
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Scores
    int scores[3];
    scores[0] = 72;
    scores[1] = 73;
    scores[2] = 33;

    // Print average
    printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
}
```
* Notice that score[0] examines the value at this location of memory by indexing into the array called scores at location 0 to see what value is stored there.
* 
* You can see how while the above code works, there is still an opportunity for improving our code. Revise your code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Get scores
    int scores[3];
    for (int i = 0; i < 3; i++)
    {
        scores[i] = get_int("Score: ");
    }

    // Print average
    printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
}
```
* Notice how we `index into scores by using scores[i] where i is supplied by the for loop`.

* We can simplify or abstract away the calculation of the average. `Modify your code as follows`:
```
#include <cs50.h>
#include <stdio.h>

// Constant
const int N = 3;

// Prototype
float average(int length, int array[]);

int main(void)
{
    // Get scores
    int scores[N];
    for (int i = 0; i < N; i++)
    {
        scores[i] = get_int("Score: ");
    }

    // Print average
    printf("Average: %f\n", average(N, scores));
}

float average(int length, int array[])
{
    // Calculate average
    int sum = 0;
    for (int i = 0; i < length; i++)
    {
        sum += array[i];
    }
    return sum / (float) length;
}
```
* Notice that a new function called average is declared. Further, notice that a const or constant value of N is declared. Most importantly, notice how the average function takes int array[], which means that the compiler passes an array to this function.

* Not only can arrays be containers: They can be passed between functions.

 # Strings
* A string is simply an array of variables of type char: an array of characters.
* Considering the following image, you can see how a string is an array of characters that begins with the first character and ends with a special character called a `NUL character`  (/0):
  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/73dbfaeb-422f-429c-93c0-a2c72d4b6fcf)


* Implementing this in your own code, type code hi.c in the terminal window and write code as follows:
```
#include <stdio.h>

int main(void)
{
    char c1 = 'H';
    char c2 = 'I';
    char c3 = '!';

    printf("%i %i %i\n", c1, c2, c3);
}
```
* `Notice that this will output the decimal values of each character.`
* Imagining this in decimal, your array would look like the following:

![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/5253a34a-0f15-484c-94d6-2ed0e132f120)



* To further understand how a string works, revise your code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string s = "HI!";
    printf("%i %i %i\n", s[0], s[1], s[2]);
}
```
* Notice how the printf statement presents three values from our array called s.

* Let’s imagine we want to say both HI! and BYE!. Modify your code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string s = "HI!";
    string t = "BYE!";

    printf("%s\n", s);
    printf("%s\n", t);
}
```
* `Notice that two strings are declared and used in this example.`

* You can visualize this as follow:
![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/650cdb20-61d7-44b8-85da-0eb24963ec3a)


* We can further improve this code. Modify your code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string words[2];

    words[0] = "HI!";
    words[1] = "BYE!";

    printf("%s\n", words[0]);
    printf("%s\n", words[1]);
}
```
* Notice that both strings are stored within a single array of type string.

* A common problem within programming, and perhaps C more specifically, is to discover the length of an array. How could we implement this in code? Type code length.c in the terminal window and code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt for user's name
    string name = get_string("Name: ");

    // Count number of characters up until '\0' (aka NUL)
    int n = 0;
    while (name[n] != '\0')
    {
        n++;
    }
    printf("%i\n", n);
}
```
* Notice that this code loops until the NUL character is found.

* Since this is such a common problem within programming, other programmers have created code in the string.h library to find the length of a string. You can find the length of a string by modifying your code as follows:
```
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // Prompt for user's name
    string name = get_string("Name: ");
    int length = strlen(name);
    printf("%i\n", length);
}
```
* Notice that this code uses the string.h library, declared at the top of the file. Further, it uses a function from that library called strlen, which calculates the length of the string passed to it.

* `ctype.h` is another `library that is quite useful`. Imagine we wanted to create a program that converted all lowercase characters to uppercase ones. In the terminal window type code uppercase.c and write code as follows:
```
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Before: ");
    printf("After:  ");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        if (s[i] >= 'a' && s[i] <= 'z')
        {
            printf("%c", s[i] - 32);
        }
        else
        {
            printf("%c", s[i]);
        }
    }
    printf("\n");
}
```
* Notice that this code iterates through each value in the string. The program looks at each character. If the character is lowercase, it subtracts the value 32 from it to convert it to uppercase.


