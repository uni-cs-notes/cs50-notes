
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
