# Flat-File Database
* As you have likely seen before, data can often be described in patterns of columns and tables.
* Spreadsheets like those created in Microsoft Excel and Google Sheets can be outputted to a csv or comma-separated values file.
* If you look at a csv file, you’ll notice that the file is flat in that all of our data is stored in a single table represented by a text file. * We call this form of data a flat-file database.
* Python comes with native support for csv files.
* In your terminal window, type code favorites.py and write code as follows:
```
# Prints all favorites in CSV using csv.reader

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create reader
    reader = csv.reader(file)

    # Skip header row
    next(reader)

    # Iterate over CSV file, printing each favorite
    for row in reader:
        print(row[1])
```
* Notice that the csv library is imported. Further, we created a reader that will hold the result of csv.reader(file). The csv.reader function reads each row from the file, and in our code we store the results in reader. print(row[1]), therefore, will print the language from the favorites.csv file.

* You can improve your code as follows:
```
# Stores favorite in a variable

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create reader
    reader = csv.reader(file)

    # Skip header row
    next(reader)

    # Iterate over CSV file, printing each favorite
    for row in reader:
        favorite = row[1]
        print(favorite)
```
* Notice that favorite is stored and then printed. Also notice that we use the next function to skip to the next line of our reader.

* Python also allows you to index by the keys of a list. Modify your code as follows:
```
# Prints all favorites in CSV using csv.DictReader

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Iterate over CSV file, printing each favorite
    for row in reader:
        print(row["language"])
```
* Notice that this example directly utilizes the language key in the print statement.

* To count the number of favorite languages expressed in the csv file, we can do the following:
```
# Counts favorites using variables

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    scratch, c, python = 0, 0, 0

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["language"]
        if favorite == "Scratch":
            scratch += 1
        elif favorite == "C":
            c += 1
        elif favorite == "Python":
            python += 1

# Print counts
print(f"Scratch: {scratch}")
print(f"C: {c}")
print(f"Python: {python}")
```
* Notice that each language is counted using if statements.

* Python allows us to use a dictionary to count the counts of each language. Consider the following improvement upon our code:
```
# Counts favorites using dictionary

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["language"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

# Print counts
for favorite in counts:
    print(f"{favorite}: {counts[favorite]}")
```
* Notice that the value in counts with the key favorite is incremented when it exists already. If it does not exist, we define counts[favorite] and set it to 1. Further, the formatted string has been improved to present the counts[favorite].

* Python also allows sorting counts. Improve your code as follows:
```
# Sorts favorites by key

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["language"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

# Print counts
for favorite in sorted(counts):
    print(f"{favorite}: {counts[favorite]}")
```
* Notice the sorted(counts) at the bottom of the code.

* If you look at the parameters for the sorted function in the Python documentation, you will find it has many built-in parameters. You can leverage some of these built-in parameters as follows:
```
# Sorts favorites by value

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["language"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

def get_value(language):
    return counts[language]

# Print counts
for favorite in sorted(counts, key=get_value, reverse=True):
    print(f"{favorite}: {counts[favorite]}")
```
* Notice that a function called get_value is created, and that the function itself is passed in as an argument to the sorted function. The key argument allows you to tell Python the method you wish to use to sort items.

* Python has a unique ability that we have not seen to date: It allows for the utilization of anonymous or lambda functions. These functions can be utilized when you want to not bother creating an entirely different function. Notice the following modification:
```
# Sorts favorites by value using lambda function

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["language"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

# Print counts
for favorite in sorted(counts, key=lambda language: counts[language], reverse=True):
    print(f"{favorite}: {counts[favorite]}")
```
* Notice that the get_value function has been removed. Instead, lambda language: counts[language] does in one line what our previous two-line function did.

* We can change the column we are examining, focusing on our favorite problem instead:
```
# Favorite problem instead of favorite language

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["problem"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

# Print counts
for favorite in sorted(counts, key=lambda problem: counts[problem], reverse=True):
    print(f"{favorite}: {counts[favorite]}")
```
* Notice that problem replaced language.

* What if we wanted to allow users to provide input directly in the terminal? We can modify our code, leveraging our previous knowledge about user input:
```
# Favorite problem instead of favorite language

import csv

# Open CSV file
with open("favorites.csv", "r") as file:

    # Create DictReader
    reader = csv.DictReader(file)

    # Counts
    counts = {}

    # Iterate over CSV file, counting favorites
    for row in reader:
        favorite = row["problem"]
        if favorite in counts:
            counts[favorite] += 1
        else:
            counts[favorite] = 1

# Print count
favorite = input("Favorite: ")
if favorite in counts:
    print(f"{favorite}: {counts[favorite]}")
```
* Notice how compact our code is compared to our experience in C.


