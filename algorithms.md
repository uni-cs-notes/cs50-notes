
# WEEK # 03 "ALGORITHMS"


# Algorithms
|   Sr.NO  |  statement |
|----------|------------|
|1. Definition| A finite sequence of rigorous instructions used to solve specific problems or perform computations.|
|2. Applications| Used for calculations, data processing, automated decision-making, and automated reasoning.|
|3. Advanced Features| Can include conditionals for different execution paths and use inference for automation.|


* An algorithm is a set of steps for accomplishing a task or solving a problem, typically executed by computers but also used in daily activities. In computer science, an algorithm is a mathematical process for problem-solving using a finite number of steps. Algorithms are crucial in computer programs, driving systems like navigation apps, search engines, and music streaming services


* They are a sequence of instructions that guide a computer to solve a specific problem efficiently and reliably, akin to a recipe producing consistent outcomes. Algorithms are essential in various industries, powering technology we use daily, aiding in decision-making, pattern recognition, and data analysis, ultimately automating processes to enhance efficiency and save time

### recall
* Recall that last week you were introduced to the idea of an array, blocks of memory that are side-by-side with one another.

## lets see at an example>>
* You can metaphorically imagine an array like a series of seven red lockers as follows:

  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/f469055f-4a74-41e8-b057-71419dec2bc1)



* We can imagine that we have an essential problem of wanting to know, “Is the number 50 inside an array?”
* We can potentially hand our array to an algorithm, wherein our algorithm will search through our lockers to see if the number 50 is behind one of the doors: Returning the value true or false.

  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/d0339eff-59af-40cc-9cb9-3b914d15427f)


* We can imagine various instructions we might provide our algorithm to undertake this task as follows:
```
For each door from left to right
    If 50 is behind door
        Return true
Return false
```
* `Notice` that the above instructions are called pseudocode: A human-readable version of the instructions that we could provide the computer.

* A computer scientist could translate that pseudocode as follows:
```
For i from 0 to n-1
    If 50 is behind doors[i]
        Return true
Return false
```
* `Notice `that the above is still not code, but it is a pretty close approximation of what the final code might look like.

* Binary search is a search algorithm that could be employed in our task of finding the 50.
Assuming that the values within the lockers have been arranged from smallest to largest, the pseudocode for binary search would appear as follows:
```
If there are no doors
    Return false
If 50 is behind middle door
    Return true
Else if 50 < middle door
    Search left half
Else if 50 > middle door
    Search right half
```
* Using the nomenclature of code, we can further modify our algorithm as follows:
```
If no doors
    Return false
If 50 is behind doors[middle]
    Return true
Else if 50 < doors[middle]
    Search doors[0] through doors[middle-1]
Else if 50 > doors[middle]
    Search doors[middle+1] through doors[n-1]
```
* `Notice,` looking at this approximation of code, you can nearly imagine what this might look like in actual code.

# Running Time
* Running time can be said as the shortest time period of solving the problem
* Different algorithms have different time period of solving the problems
#### here is an explanation using the graph 
* running time involves an analysis using `big O notation`.
* `Take a look at the following graph:`

  ![image](https://github.com/uni-cs-notes/cs50-notes/assets/160413612/48517079-98d4-4d34-b25c-b64c78927399)

# Linear and Binary Search
* Linear search and binary search are algorithms used to find an element within a list or array. They differ in their approach and efficiency:

### Linear Search

* Imagine searching a book page by page until you find the word you're looking for. That's linear search in essence.
* It starts at the beginning of the list and compares each element with the target element one by one.
* This continues until the target element is found or the entire list is scanned.
* Linear search works for both unsorted and sorted lists.
* It's relatively simple to implement.

### Binary Search

* Think of repeatedly folding a book in half to find a specific page. That's similar to binary search.
* It requires the list to be sorted in ascending order.
* It starts by finding the middle element of the list.
* If the target element is greater than the middle element, the search continues in the upper half of the list.
* If the target element is less than the middle element, the search continues in the lower half.
* This process of dividing the search space in half continues until the target element is found or it's proven not to be present.
* Binary search is generally much faster than linear search for large datasets, especially sorted ones.
* However, it requires the initial sorting step and might be more complex to implement.
* Here's a table summarizing the key differences:

#### Feature	Linear Search	Binary Search
```
Order of list	Unsorted or sorted	Sorted (ascending)
Search strategy	Sequential comparison	Divide-and-conquer
Time complexity	O(n)    |   (worst case)	O(log n)
Ease of implementation	|  Simpler	More complex
```

* You can implement linear search ourselves by typing `code search.c `in your terminal window and by writing code as follows:
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // An array of integers
    int numbers[] = {20, 500, 10, 5, 100, 1, 50};

    // Search for number
    int n = get_int("Number: ");
    for (int i = 0; i < 7; i++)
    {
        if (numbers[i] == n)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
* Notice that the line beginning with `int numbers[]` allows us to define the values of each element of the array as we create it. Then, in the `for loop`, we have an implementation of linear search.

* We have now implemented linear search ourselves in` C!`
#### What if we wanted to search for a string within an array? Modify your code as follows:
```
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // An array of strings
    string strings[] = {"battleship", "boot", "cannon", "iron", "thimble", "top hat"};

    // Search for string
    string s = get_string("String: ");
    for (int i = 0; i < 6; i++)
    {
        if (strcmp(strings[i], s) == 0)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
* Notice that `we cannot utilize == as in our previous iteration of this program`. Instead, we have to use `strcmp,` which comes from the `string.h library`.

* Indeed, running this code allows us to iterate over this array of strings to see if a certain string was within it. However, if you see a segmentation fault, where a part of memory was touched by your program that it should not have access to, do make sure you have `i < 6 `noted above instead of `i < 7.`

### lets combine both ideas of numbers and string >>>
* We can combine these ideas of both numbers and strings into a single program. Type `code phonebook.c` into your terminal window and write code as follows:
```
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // Arrays of strings
    string names[] = {"Carter", "David"};
    string numbers[] = {"+1-617-495-1000", "+1-949-468-2750"};

    // Search for name
    string name = get_string("Name: ");
    for (int i = 0; i < 2; i++)
    {
        if (strcmp(names[i], name) == 0)
        {
            printf("Found %s\n", numbers[i]);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
* Notice that Carter’s number begins with `+1-617` and David’s phone number starts with `‘1-949’.` Therefore, `names[0]` is `Carter` and `numbers[0] `is `Carter’s number`.
# Data structures
  * Data structures are the building blocks for organizing and storing data in a computer's memory. They define how data is arranged and how different operations can be performed on that data efficiently.
* `Organization:` Data structures provide a structured format for data, as opposed to just a random collection of bits. This structure allows for efficient access, manipulation, and retrieval of data.
* `Storage:` They dictate how data is stored in memory, considering factors like data type, relationships between data elements, and the desired operations.
* `Efficiency:` The core idea behind data structures is to optimize how data is handled. This includes faster access times, minimizing memory usage, and enabling efficient addition, removal, or modification of data elements.

* `There are various types of data structures` 

1. Arrays 
2. Linked 
3. Stacks 
4. Queues 
5. Trees 
6. Graphs

##### crucial role in:

* `Algorithm Design:` Choosing the right data structure for a problem can significantly impact the efficiency of an algorithm.
* `Software Development:` Data structures are the foundation for building efficient and scalable software applications.
* `Memory Management:` Efficient data structures help optimize memory usage and avoid memory-related issues.
* Overall, data structures are essential tools for programmers to organize, store, and manipulate data effectively.
### lets take a look at it in C
 * turns out that `C` allows a way by which we can create our own data types `via a struct`. Modify your code as follows:
```
#include <cs50.h>
#include <stdio.h>
#include <string.h>

typedef struct
{
    string name;
    string number;
}
person;

int main(void)
{
    person people[2];

    people[0].name = "Carter";
    people[0].number = "+1-617-495-1000";

    people[1].name = "David";
    people[1].number = "+1-949-468-2750";

    // Search for name
    string name = get_string("Name: ");
    for (int i = 0; i < 2; i++)
    {
        if (strcmp(people[i].name, name) == 0)
        {
            printf("Found %s\n", people[i].number);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
* Notice that the code begins with `typedef struct` where a `new datatype called person` is defined. Inside a person is a `string called name and a string called number`. In the `main function`, begin by `creating an array called people that is of type person that is a size of 2`. Then, we update the names and phone numbers of the two people in our people array. `Most important`, notice how the dot notation such as `people[0].`name allows us to access the person at the `0th location` and `assign that individual a name`.

* Sorting
* Sorting refers to the process of arranging data in a specific order. This order can be ascending `(from least to greatest)` or descending `(from greatest to least)`. Sorting algorithms take a list of elements and reorganize them based on a defined characteristic.

* `Definition:` It's a technique to organize data elements into a particular sequence according to a specified order. This order is usually based on the values of a key attribute within each element.
#### Purpose 
* `There are several reasons why sorting data is important>>>`
* `Efficient Searching:` Sorted data allows for faster searching using algorithms like binary search. Imagine searching a phonebook - it's much quicker if the names are alphabetized.
* `Data Analysis:` Sorting helps identify patterns, trends, and outliers within the data. Analyzing sorted exam scores is easier than looking at an unsorted list.
* `Data Presentation:` Sorting can make data easier to understand and interpret. When presenting customer information, it might be helpful to sort by name or purchase history.
* `Efficient Operations:` Certain data structures and algorithms work more efficiently when the data is sorted. Sorting a playlist alphabetically allows for faster song retrieval.  

* There are many different sorting algorithms , each with its own strengths and weaknesses. Some common sorting algorithms include:
```
Merge Sort: Efficient divide-and-conquer algorithm that works well for large datasets.
Quick Sort: Another efficient algorithm that works well on average but can have poor performance in specific cases.
Heap Sort: Utilizes a heap data structure for efficient sorting.
Selection Sort: Simpler algorithm but less efficient for large datasets.
```



  
