
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

* It turns out that there are many different types of sort algorithms.
* Selection sort is one such search algorithm.
* The algorithm for selection sort in pseudocode is:
```
For i from 0 to n–1
    Find smallest number between numbers[i] and numbers[n-1]
    Swap smallest number with numbers[i]
```
* Consider the unsorted list as follows:
```
  5 2 7 4 1 6 3 0
  ^
```
* Selection sort will begin by looking for the smallest number in the list and swap that number with our current position in the list. In this case, the zero is located and moved to our current position.
```
  0 | 2 7 4 1 6 3 5
```
* Now, our problem has gotten smaller since we know at least the beginning of our list is sorted. So we can repeat what we did, starting from the second number in the list:
```
  0 | 2 7 4 1 6 3 5
      ^    
```
1 is the smallest number now, so we’ll swap it with the second number. We’ll repeat this again …
```
  0 1 | 7 4 2 6 3 5
        ^     
```
… and again…
```
  0 1 2 | 4 7 6 3 5
          ^
```
… and again…
```
  0 1 2 3 | 7 6 4 5
            ^
```
… and again …
```
  0 1 2 3 4 | 6 7 5
              ^
```
* and so on.
* Bubble sort is another sorting algorithm that works by repeatedly swapping elements to “bubble” larger elements to the end.
* The pseudocode for bubble sort is:
```
Repeat n-1 times
For i from 0 to n–2
    If numbers[i] and numbers[i+1] out of order
        Swap them
```
* We’ll start with our unsorted list, but this time we’ll look at pairs of numbers and swap them if they are out of order:
```
5 2 7 4 1 6 3 0
^ ^
2 5 7 4 1 6 3 0
  ^ ^
2 5 7 4 1 6 3 0
    ^ ^
2 5 4 7 1 6 3 0
      ^ ^
2 5 4 1 7 6 3 0
        ^ ^
2 5 4 1 6 7 3 0
          ^ ^
2 5 4 1 6 3 7 0
            ^ ^
2 5 4 1 6 3 0 7
```
* Now, the highest number is all the way to the right, so we’ve improved our problem. We’ll repeat this again:
```
2 5 4 1 6 3 0 | 7
^ ^
2 5 4 1 6 3 0 | 7
  ^ ^
2 4 5 1 6 3 0 | 7
    ^ ^
2 4 1 5 6 3 0 | 7
      ^ ^
2 4 1 5 6 3 0 | 7
        ^ ^
2 4 1 5 3 6 0 | 7
          ^ ^
2 4 1 5 3 0 6 | 7
```
* Now the two biggest values are on the right. We’ll repeat again:
```
  2 4 1 5 3 0 | 6 7
  ^ ^
  2 4 1 5 3 0 | 6 7
    ^ ^
  2 1 4 5 3 0 | 6 7
      ^ ^
  2 1 4 5 3 0 | 6 7
        ^ ^
  2 1 4 3 5 0 | 6 7
          ^ ^
  2 1 4 3 0 5 | 6 7
```
 … and again …
```
  2 1 4 3 0 | 5 6 7
  ^ ^
  1 2 4 3 0 | 5 6 7
    ^ ^
  1 2 3 4 0 | 5 6 7
      ^ ^
  1 2 3 4 0 | 5 6 7
        ^ ^
  1 2 3 0 4 | 5 6 7
```
 … and again …
```
  1 2 3 0 | 4 5 6 7
  ^ ^
  1 2 3 0 | 4 5 6 7
    ^ ^
  1 2 3 0 | 4 5 6 7
      ^ ^
  1 2 0 3 | 4 5 6 7
```
… and again …
```
  1 2 0 | 3 4 5 6 7
  ^ ^
  1 2 0 | 3 4 5 6 7
    ^ ^
  1 0 2 | 3 4 5 6 7
```
 … and finally …
```
  1 0 | 2 3 4 5 6 7
  ^ ^
  0 1 | 2 3 4 5 6 7
```
* Notice that, as we go through our list, we know more and more of it becomes sorted, so we only need to look at the pairs of numbers that haven’t been sorted yet.
* Analyzing selection sort, we made only seven comparisons. Representing this mathematically, where n represents the number of cases, it could be said that selection sort can be analyzed as:
```
  (n-1)+(n-2)+(n-3)+ ... + 1

```

You can visualize a comparison of these algorithms.
https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html
