# welcome to cs50 
# week 0 (Scratch)
### in scratch we will study the basic fundamentals about computers and programming in C 

  
## the course is based on 
* number system
* ASCII
* Unicode
* Scratch
*  MIT (scratch program)

#  number system
The number system is based on  
* unary
* binary
* octal
* decimal
* hexa_decimal

# Unary
As time has rolled on, there are more and more ways to communicate via text.
* Since there were not enough digits in binary to represent all the various characters that could be represented by humans, the Unicode standard expanded the number of bits that can be transmitted and understood by computers.
* Unicode includes not only special characters, but emoji as well.
* There are emoji that you probably use every day. The following may look familiar to you:
* Computer scientists faced a challenge when wanting to assign various skin tones to each emoji to allow the communication to be further personalized.
*  In this case, the creators and contributors of emoji decided that the initial bits would be the structure of the emoji itself, followed by skin tone.
* `For example`, the unicode for a generic `thumbs up is U+1F44D`. However, the following represents the same thumbs up with a different `skin tone: U+1F44D U+1F3FD`.
* More and more features are being added to the Unicode standard to represent further characters and emoji.

# Binary 
* all the computers use the binary lanaguage also known as the `Machine language`
* it is based on 1s and 0s
* binary was used in punch cards for computer operations back then, the cards use to contain the 
information in binary which use to be reconized by the computer

# Decimal
* `Definition`
* The decimal numeral system is a base-ten positional numeral system used to represent integer and non-integer numbers.
* `Decimal Notation`
* Refers to how numbers are denoted in the decimal system, often called decimal notation.
* `Decimal Fractions`
* Numbers that can be represented in the decimal system, such as fractions of the form a/10^n.
* `Approximation`
* Decimals are commonly used to approximate real numbers by increasing the digits after the decimal separator.
* `Infinite Decimals`
* The decimal system can be extended to represent any real number with an infinite sequence of digits after the decimal separator

# Octal 
* The octal number system is a `base-8` number system that uses the digits `0 to 7`. It is widely used in computer programming and digital systems because it is a compact way of representing binary numbers with each octal number corresponding to three binary digits.

# Hexa_Decimal
* `Definition`
* A positional numeral system that uses 16 distinct symbols (0-9 and A-F) to represent numbers.
* `Symbol Range`
* Uses symbols "0"-"9" to represent values 0 to 9, and "A"-"F" to represent values ten to fifteen.
* `Common Use`
* Widely used by software developers and system designers for a human-friendly representation of binary-coded values.
* `Bit Representation`
* Each hexadecimal digit represents four bits, also known as a nibble; an 8-bit byte ranges from 00 to FF in hexadecimal.
* `Mathematical Notation`
* In mathematics, uses subscripts to denote hexadecimal base; e.g., 40,405 in decimal is 9DD5~16~.
* `Programming Notation` 
* In programming, hexadecimal numbers are often denoted with a prefix, such as `0x` for the C programming language.

# ASCII
* `Full Name`
* American Standard Code for Information Interchange
* `Purpose`
* Represent text in computers, telecommunications equipment, and other devices
* `Total Code Points`
* 128, of which 95 are printable characters
* `Evolution`
* Modern computer systems now use Unicode, which includes ASCII's first 128 code points
* Just as numbers are binary patterns of ones and zeros, letters are represented using ones and zeros too!
* Since there is an overlap between the ones and zeros that represent numbers and letters, the ASCII standard was created to map specific letters to specific numbers.
* `For example:` the letter A was decided to map to the number 65.
* If you received a text message, the binary under that message might represent the numbers 72, 73, and 33. Mapping these out to ASCII, your message would look as follows:
```
  H   I   !
  72  73  33
```

# Pseudocode and the Basic Building Blocks of Programming
* The ability to create pseudocode is central to one’s success in both this class and in computer programming.
* `Pseudocode is a human-readable version of your code`.
* For example, considering the third algorithm above, we could compose pseudocode as follows:
```
  1  Pick up phone book
  2  Open to middle of phone book
  3  Look at page
  4  If person is on page
  5      Call person
  6  Else if person is earlier in book
  7      Open to middle of left half of book
  8      Go back to line 3
  9  Else if person is later in book
  10     Open to middle of right half of book
  11     Go back to line 3
  12 Else
  13     Quit
```
* Pseudocoding is such an important skill for at least two reasons. First, when you pseudocode before you create formal code, it allows you to think through the logic of your problem in advance.
* Second, when you pseudocode, you can later provide this information to others that are seeking to understand your coding decisions and how your code works.
* Notice that the language within our pseudocode has some unique features. First, some of these lines begin with verbs like pick up, open, look at. Later, we will call these functions.
* Second, notice that some lines include statements like if or else if. These are called conditionals.
* Third, notice how there are expressions that can be stated as true or false, such as “person is earlier in the book.” We call these boolean expressions.
* Finally, notice how these statements like “go back to line 3.” We call these loops.
* In the context of Scratch, which is discussed below, we will use each of the above basic building blocks of programming.



    
