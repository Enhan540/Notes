# Python Notes

## Table of Contents
Intro to Programming

- [Part 1](#part-1)
	- Section 1: [Getting Started](#getting-started)
	- Section 2: [Information from the User](#getting-user-input)
	- Section 3: [More About Variables](#variables)
	- Section 4: [Arithmetic Operations](#arithmetic-operations)
	- Section 5: [Conditional Statements](#conditional-statements)
- [Part 2](#part-2)
	- Section 1: [Programming Terminology](#programming-terminology)
	- Section 2: [More Conditionals](#more-conditionals)
    - Section 3: [Combining Conditionals](#combining-conditionals)
    - Section 4: [Simple Loops](#simple-loops)
- [Part 3](#part-3)
    - Section 1: [Loops With Conditions](#loops-with-conditions)
    - Section 2: [Working with Strings](#working-with-strings)
- [Part 4](#part-4)
- [Part 5](#part-5)
- [Part 6](#part-6)
- [Part 7](#part-7)

Advanced Courses in Programming

- Part 8
- Part 9
- Part 10
- Part 11
- Part 12
- Part 13
- Part 14

## Part 1
### Getting Started
Programs consist of commands
- ex: **'print'** command
```
print("Hi there!")
	# Will print 'Hi there!' in the terminal
```
Can also output the answer to arithmetic answers.
```
print(2 + 3)
print(3 * 3)
print (2 + 2 * 10)
	# Quotations ARE NOT used since using quotations would print it as a string rather than the computed answer
```
Can use single quotations instead of double quotations; comes in handy when wanting to print double quotations in the string.
```
print('He shouted, "Look out!"')
```
### Getting User Input
To get a line from the user, the **input** command is used.
The input command can also output a string when asking for the input.

ex:
```
name = input("What is your name? ")	
	# Takes the next line from the user and stores that line in the name variable

print("Hi there, " + name)
	# Prints the string with the inputted line from the user.
```

### Variables

'name' in previous example was a variable that held the information/input from the user and could be used anywhere else in the code.

Variables can have their values changed throughout the execution of the program. Simply set the variable to another value by `var_name = ...', where '...' stands for any sort of information.
- unlike Java, the variable doesn't need to have a type declared

Example: The variable 'word' in this example would have different values three times throughout the code's execution
```
word = input("Please type in a word: ")
print(word)

word = input("And another word: ")
print(word)

word = "third"
print(word)
```
> **TIP:** having reasonable and good names for your variables are helpful so you can easily refer back to a specific variable when you are using many

#### Integers
We've been using strings in variables, denoted by the quotation marks around the line of words. But integers do not use quotations, and are just their value. 

Integers are numbers, negative and positive, that have no decimal or fractional part. 

Variable type matters because certain operations behave differently with different variable types. For example, the '+' operator works differently when adding two integers and two strings:
```
number1 = 100
number2 = "100"

print(number1 + number1)
print(number2 + number2)
```
Output:
```
200
100100
```
#### Combining Values When Printing
- the '+' operator for integers performs an addition of the two integers while for strings, it combines the two strings into one, which is called "concatenation" of the strings.

You also cannot print a string with an integer as you can in Java.
- must use the 'str' function to turn the integer into a string.
```
result = 10 * 25
print("The result is " + str(result))
	# An error will be thrown if the 'str' is not invoked.
```

However, the print command has another call method which uses commas to separate the different inputs/variables.
```
result = 10 * 25
print("The result is", result)
```
Output:
```
The result is 250	# Space between different types is already added
```
#### Printing with F-Strings
F-strings are another way of formatting printouts in Python and are considered one of the simplest ways of formatting text.

An example of the f-string in use:
```
result = 10*25
print(f"The result is {result}")
```
> The **f** denotes that the following string is an f-string to Python. 
> 
> When a variable is in the curly brackets of the f-string, the value of that variable is then added as part of the string.

Multiple variables can be used in an f-string:
```
name = "Mark"
age = 19
city = "Upland"
print(f"Hi {name}, you are {age} years old. You live in {city}.")
```
Output:
```
Hi Mark, you are 19 years old. You live in Upland.
```
##### Printing On Only One Line
If you want to only keep everything on one line with multiple print commands, use the 'end = ""' parameter. Can be used with f-string prints.
```
print("Hi ", end="")
print("there")
```
#### Floating Point Numbers
Float numbers are numbers that have a fractional/decimal point. Operations work the same on float point numbers as integers.

### Arithmetic Operations
#### Basic Python Arithmetic Operations
> '+' -> Addition
>
> '-' -> Subtraction
>
> '*' -> Multiplication
>
> '/' -> Division (floating point result)
>
> '//' -> Division (integer result)
>
> '%' -> Modulo (remainder)
>
> '**' -> Exponentiation

Order of operation follow typical order in math.

Typically, the result of the operation will match those of the operands. Example would be integer plus integer = integer; float + float = float. However, if a float and integer are the operands, the answer will become a float.
- One exception would be the '/' operation, which always returns a float number.

Integer division ('//') rounds the float down to the nearest integer.

Example:
```
x = 3
y = 2

print(f"/ operator {x/y}")
print(f"// operator {x//y}")
```
Output:
```
/ operator 1.5
// operator 1
```

Python doesn't have the sqaure root operation by default. To use that sqrt() function, you must import it using the import command:
```
from math import sqrt
```

#### Reading Numbers as Input
The 'input' command that was used to read strings will also be used to read integer inputs. But, the inputted integer must be cast to an integer type using the int() command.

Example:
```
input_str = input("Which year were you born?")
year = int(input_str)
print(f"Your age at the end of the year 2021: {2021 - year}")
```

Can combine into just one variable:
```
year = int(input("Which year were you born?"))
print(f"Your age at the end of the year 2021: {2021 - year}")
```

A string can be converted to a float using the float() command as well.

### Conditional Statements
Conditional statements run certain lines if a certain criteria is met. This means that some lines of code may not be run while other lines are run. 

For example, the following code checks whether the user is of age:
```
age = int(input("How old are you? "))

if age > 17:
    print("You are of age!")
    print("Here's a copy of GTA6 for you.")

print("Next customer, please!")
```
If the inputted age is over 17, the output is:
```
How old are you? 18
You are of age!
Here's a copy of GTA6 for you.
Next customer, please!
```
Otherwise the age is less than 17 and will output:
```
How old are you? 16
Next customer, please!
```
Conditional statements have an if statement, which checks a set condition, and a following block of code which will run if the condition in the if statement returns true. 

Comparision operators include:
> '==' -> Equal to
>
> '!=' -> Not Equal to
>
> '>' -> Greater than
>
> '>=' -> Greater than or equal to
>
> '<' -> Less than
>
> '<=' -> Less than or equal to

Example:
```
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative.")

if number > 0:
    print("The number is positive.")

if number == 0:
    print("The number is zero.")
```
Outputs:
```
Please type in a number: 15
The number is positive.
```

```
Please type in a number: -18
The number is negative.
```

```
Please type in a number: 0
The number is zero.
```

**TIP:** To use else if statements, use the command 'elif'.

#### Indentation
An if-statement recognizes the conditional code if it is indented the same, meaning there should be some whitespace in front of the code that should run if the condition is true.

Example:
```
age = int(input("Type in a number: "))

if age >= 18:
	print("You are of age.")
	print("You may enter the building.")

print("Program executed.")
```
The lines indented after the conditional will run if age is greater than or equal to 18. 

#### Boolean Values and Expressions
A boolean value is a result of some sort of condition, meaning its values can be true or false.

A boolean expression is some sort of expression that gives a boolean value as a result, typically found in conditional statements.

## Part 2

### Programming Terminology
#### Statements
A **statement** refers to a part of a program that executes something. 

Examples:
> print("Hi!")
>
> number = 2

Sometimes, a statement can take up multiple lines of code. It can contain other statements, for example:
```
if name == "Anna":
	print("Hi!")
	number = 2
```

There are two statements in the prior example:
- A print statement and an assignment statement inside a conditional statement.

#### Block
A **block** is a group of consecutive statements on the same level in a program. An example of a block of code would be the statements that run when a conditional statement is true.

Example:
```
if age > 17:
    # beginning of the conditional block
    print("You are of age!")
    age = age + 1
    print("You are now one year older...")
    # end of the conditional block

print("This here belongs to another block")
```
Python blocks are shown when they are indented the same amount of whitespace.
On top of that, main code of the program must not be indented or it will not execute.

#### Expressions
An **expression** is a bit of code that results in a determined data type. 
The expression will be evaluated when the program is executed, and the expression will be turned into a value that the program will be used.

Examples:
> 2 + 3 + 4
> 
> "abc" + "de"
>
> 11 / 2
>
> 2 * 5 > 9

Expressions can be put into a variable since they result in a value of some type. And, simple expressions can be combined into more complicated expressions.
```
y = 3 * x - 8 ** x
```

#### Functions
A **function** executes some functionality. Functions can receive arguments which the function will process and/or execute the function with. 

For a function to work, it needs to be called in the main code. To call a function, the function needs to be mentioned with any arguments necessary. For example, the print command is called when the print() line is put into the code and given an argument. The following code calls the print function with the argument "this is an argument":
```
print("this is an argument")
```

Some functions return a value. The function processes any arguments given to the function and produces a result, which the funtion would then return that result to the main function to use. An example would be the input command, which returns the user's input as a string to the main code. The return value of a function is usually stored in a variable so the data can be used later.

#### Data Type
Any value has a specific **data type**. The data type is determined by what type of value the value is. In the following example, the variable `name` has the data type of a `str`, or a string, and the variable `result` has the data type of an `int`.
```
name = "Joe"
result = 100
```

The `type` command can show the data type of any expression:
```
print(type("Anna"))
print(type(100))
```
> <class 'str'>
>
> <class 'int'>

#### Syntax
**Syntax** of a programming language refers to how the code should be written.
Each programming language has a different syntax.

If the syntax isn't followed, errors/exceptions can occur.

#### Debugging
A **bug** occurs when something doesn't work the way it is supposed to. They can happen due to many different things. So **debugging** is looking for these bugs and fixing them. 

### More Conditionals
We can make conditional statements more compact instead of having many different if statements. For example, the following code can be easily compacted from:
```
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")

if number >= 0:
    print("The number is positive or zero")
```
To this longer and single if statement:
```
number = int(input("Please type in a number: "))

if number < 0:
    print("The number is negative")
else:
    print("The number is positive or zero")
```
The newly compacted code utilizes the `else` statement, which runs when the none of the if statement(s) are run within the same if statement block. An `else` statement cannot be used unless there is at least one if-statement used.

If statements can have branches of other if statements. This allows for other conditions to be checked when a given condition is found to be falsed. To have other if-statements, the `elif` command, short for "else if", is used. 

For example, the following code checks whether a given number is positive, negative, or zero by making use of the elif statement.
```
number = int(input("Input any number."))

if number < 0:
	print("The number is negative.")
elif number > 0:
	print("The number is positive.")
else:
	print("The number is zero.")
```
There are two conditionals to be checked and an else statement to be executed if none of the conditional statements are executed. 
- The if-statement conditional is checked first. 
	- If that condition is true, then that if-statements block of code is run and skips all the other conditionals and else statements. 
	- If not, it checks the next conditional statement, the elif. 
- The same routine applies to the elif statement. 
	- Run the code if the conditional is true and skips the rest of the other if/else statements. 
	- If false, then it would check the next elif statement if it exists or the else statement if no other elif statement. 
- If none of the other if-statements are executed, the else statement executes.

**SIDENOTE**: Strings can be compared to find which string comes before another alphabetically.

### Combining Conditionals
To combine conditinals, the logical operators `and` and `or` are used. 
- The `and` operator returns true when all given conditionals are also true.
- The `or` operator returns true when at least one of the given conditinals are also true.

For example, `number >= 5 and number <= 8` returns true when the value of `number` is between 5 and 8.

On the other hand, `number < 5 or number > 8` returns true when `number` is either less than 5 or greater than 8.

Sometimes determining when a condition is not true is important. In those cases, the `not` operator negates a condition.

Example:
```
number = int(input("Please type in a number: "))
if not (number >= 5 and number <= 8):
	print("The number is not within the range of 5 to 8.")
```
> In this case, the code will only print if the number is NOT in the range of 5 to 8.

The `and`, `or`, `not` operators are also called Boolean operators.

> **Simplified combined conditions**
>
> The condition `x >= a and x <= b` is commonly used to check whether `x` is in the range of `a` to `b`.
>
> However, Python allows for another way to write this condition: `a <= x <= b`

#### Combining and Chaining Conditions
The following example uses chained conditionals to check which of the four inputted numbers is the greatest:
```
n1 = int(input("Number 1: "))
n2 = int(input("Number 2: "))
n3 = int(input("Number 3: "))
n4 = int(input("Number 4: "))

if n1 > n2 and n1 > n3 and n1 > n4:
    greatest = n1
elif n2 > n3 and n2 > n4:
    greatest = n2
elif n3 > n4:
    greatest = n3
else:
    greatest = n4

print(f" {greatest} is the greatest of the numbers.")
```

Example Output:
```
Number 1: 2
Number 2: 4
Number 3: 1
Number 4: 1
4 is the greatest of the numbers.
```

#### Nested Conditionals
Conditionals can be nested or put into other conditionals. For example, this code checks whether a number is greater than 0, then checks whether the number is odd or even:
```
number = int(input("Please type in a number: "))

if number > 0:
    if number % 2 == 0:
        print("The number is even")
    else:
        print("The number is odd")
else:
    print("The number is negative or zero")
```

Example Output:
```
Please type in a number: 3
The number is odd

Please type in a number: 18
The number is even

Please type in a number: -4
The number is negative or zero
```
> With nested conditionals, it's important to make sure the code is indented so the right code is in the right conditional branch.
>
> However, nested conditionals can typically be also done with logical operators.

### Simple Loops
Another important concept used in coding is repetition, or iteration. Combined with conditionals, the form a control structure. They are called constructures because they "essentially allow you to control which lines of code get executed when." The are sometimes called *loops* because occassionally the code goes back to the front. 

In this section, a simple `while` loop is introduced, which has a similar structure to the if conditional statements. 

In this example, this program continues to ask the user for a number and then prints that number sqaured. It continues to do so until the number -1 is entered:
```
while True:
    number = int(input("Please type in a number, -1 to quit: "))

    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```
Example Output:
```
Please type in a number, -1 to quit: 2
4
Please type in a number, -1 to quit: 4
16
Please type in a number, -1 to quit: 10
100
Please type in a number, -1 to quit: -1
Thanks and bye!
```
> The break command causes the code to exit the loop and continue executing the program after the while loop. 

It is important with loops to always exit the loop at some point. If not, an infinite loop can be created. 

In this case, the prompt is outside the loop, meaning that if the first number inputted isn't -1, then the sqaure of the number is forever printed:
```
number = int(input("Please type in a number, -1 to quit: "))
while True:
    if number == -1:
        break

    print(number ** 2)

print("Thanks and bye!")
```

#### Loops and Helper Variables
When creating a program to check a PIN number, we want the user to only have three attempts. To make this possible, we use **helper variables**.

In the following example, two helper variables are used: `attempts`, which is used to track the number of times the user tries to enter the PIN, and `success`, which is a boolean variable that shows whether the user is successful in signing in. 
```
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1

    if code == "1234":
        success = True
        break

    if attempts == 3:
        success = False
        break

    # this is printed if the code was incorrect AND there have been less than three attempts
    print("Incorrect...try again")

if success:
    print("Correct PIN entered!")
else:
    print("Too many attempts...")
```
Example Outputs:
```
Please type in your PIN: 0000
Incorrect...try again
Please type in your PIN: 1234
Correct PIN entered!
```
```
Please type in your PIN: 0000
Incorrect...try again
Please type in your PIN: 9999
Incorrect...try again
Please type in your PIN: 4321
Too many attempts...
```
The loops either exits when three attempts are used up or when the user gets the right PIN.

#### Debugging Print Statements in Loops
When using loops, it's important to make sure it's doing what it's supposed to. To check if things are going properly, print commands can be used throughout the loop and other parts of the code to see if a part of the code is either running when it's supposed to or not running.

#### Concatenating Strings with the + Operator
The above example kept count of the amount of attempts the user had. But, concatentation could keep track of all the different PIN attempts.

To do so, another variable will be used called codes, which will be set to blank at first:
```
codes = ""
attempts = 0

while True:
    code = input("Please type in your PIN: ")
    attempts += 1
    codes += code + ", "
    # ...
```
The variable `codes` contains an empty string at first. However, with each iteration the string gets longer as more PIN numbers are added on to the string. 

## Part 3

### Loops with Conditions
In the last section, a simple `while True` loop was used to repeat certain parts of code. Because `True` will always return true, the loop will continue until the code specifically and explicitly breaks out of the loop.

Instead, we can put a condition in the while loop so that the loop will stop itself when the condition is found to be false. A basic construction of a while loop with a condition is:
```
while <condition>:
    <block>
```

The way this loop works is that each time the loops finishes, it returns to the top of the while loop and checks whether the condition is still true. If it's true, the loop will run again. If it's false, it will begin exectuing the code after the end of the while block.

For example, the following code will continue to print numbers incrementing up to 10:
```
number = int(input("Please type a number: "))

while number < 10:
    print(number)
    number += 1

print("Execution complete.")
```
Once the number is inputted, the while loop checks if the given number is less than 10. If less than 10, the number will be printed then incremented up one, and the loop continues until the number is greater than or equal to 10.

#### Initialisation, Condition, and Update
Creating a loop usually includes three different steps.

**Initialisation**
This step sets up the variable(s), often called *iteration*/*iterator variables*, that will be used in the condition. Typically, this step occurs outside the loop.

**Condition**
The condition defines how long the loop will continue executing and is declared at the beginning of the while loop.

**Update**
This is the most important step in a loop, since without it, an executed loop will become an infinite loop. This step updates/changes the variables in the condition so that the loop gets closer to finishing. 

If we look at the previous example, we can identify each step of creating a loop:

1. Initialisation
    ```
    number = int(input("Please type a number: "))
    ```
2. Condition
    ```
    while number < 10
    ```
3. Update
    ```
    number += 1
    ```

Without even one of these, the loop will not work as intended.

#### Writing Conditions
Any Boolean expression or combo of such can be used as a condition. 

#### Building Strings
Earlier, the concept of building strings was introduced. The operator `+=` is also able to be used to make these strings.
```
words = "pride"
words += ", prejudice"
words += " and python"

print(words)
```

This also applies to f strings.
```
course = "Introduction to Programming"
grade = 4

verdict = "You have received "
verdict += f"the grade {grade} "
verdict += f"from the course {course}"

print(verdict)
```

### Working with Strings
Earlier, the concept of concatenation was introduced, which allows for combining of two strings to build one using the `+` operator. 
```
begin = "ex"
end = "ample"
word = begin + end
print(word)
```

However, the `*` operator can also be used to duplicate the string a given number of times.
```
word = test
print(test*3)
```
Output:
```
testtesttest
```
Combining these operators, a program creating a period with n levels is possible:
```
n = 10 # number of layers in the pyramid
row = "*"

while n > 0:
    print(" " * n + row)
    row += "**"
    n -= 1
```
Output:
```
          *
         ***
        *****
       *******
      *********
     ***********
    *************
   ***************
  *****************
 *******************
```
> The `print` command in the loop prints spaces `n` times before printing the asterisk(s)

#### Length and Index of a String
The function `len` gives the number of characters in a string as an integer. If `len("hi")` were used, the integer `2` would be returned since two characters make up the string `"hi"`.
> The number returned includes **ALL** characters, so things such as spaces and punctuation would be counted.

Strings are basically just a sequence of characters, so any single character can be retrieved. Using the `[]` operator finds the character at the given index within the brackets. The *index* is the position of the character in the string starting at 0 as the first index. 

Example:
```
string1 = "cha cha real smooth"
print(string1[1])
print(string1[5])
print(string1[7])
```
Output:
```
h
h
 
```
> The second line seems blank, but it printed out the space, which is at index 7.

Since the first character is at index 0, the last character has the index of *length - 1*. So we can just find the last character of a string by: `string1[len(string1) - 1]`

We can use the following program to loop through all the characters of a given string.
```
input_string = input("Type in a string: ")
index = 0
while index < len(input_string):
    print(input_string[index])
    index += 1
```
Example Output:
```
Please type in a string: test
t
e
s
t
```

Another way to access the characters in a string is by ***negative indexing***. The way this works the last character of the string has the index of `-1` and the second-to-last character has the index of `-2`. Using this method, the first character would have the index of the negative of the length of the string. One way to look at this is that `input_string[-1] == input_string[len(input_string) - 1]`.

#### IndexError: String Index Out of Range
If you try to access a character with an index that is not within the string's index range, an error will occur. 
```
input_string = input("Please type in a string: ")
print("The tenth character: " + input_string[9])
```
Example:
```
Please type in a string: python

Traceback (most recent call last):
File "", line 1, in 
IndexError: string index out of range
```

#### Substrings and Slices
A **substring** of a string is a sequence of characters that forms a part of the string. For example, the word `cringe` contains the substrings `cri`, `nge`, `ring`, and many others. **Slicing** is the process of selecting substrings, and the substring is also referred to as a *slice* of a string.

To take the substring of a string, you would use the notation `[a:b]`, where `a` is the beginning index of the substring and `b` is the index after the last character included in the substring. For example, if a string `trying` exists, [1,4] of that string would give `ryi`. 

Another example:
```
input_string = "presumptious"

print(input_string[0:3])
print(input_string[4:10])

# if the beginning index is left out, it defaults to 0
print(input_string[:3])

# if the end index is left out, it defaults to the length of the string
print(input_string[4:])
```
Output:
```
pre
umptio
pre
umptious
```
> If "half intervals" are used, `[a:] or [:b]`, either the slice starts at index `a` and includes all following characters or starts at the very beginning and takes all characters up to but not including the character at index `b`.

#### Searching for Substrings
The `in` operator can tell us if a string contains a particular substring. For example, the expression `a in b` will return true if `b` contains the substring `a`.
Example:
```
input_string = "test"

print("t" in input_string)
print("x" in input_string)
print("es" in input_string)
print("ets" in input_string)
```
Output:
```
True
False
True
False
```
The `in` operator only tells us if a certain substring is in a string, but nothing else. Another operator, the `find` method, can tell us where a certain substring of a string is located. Taking the substring being searched for as an argument, it either returns the first index where it is found or `-1` if the substring is not found within the string. 

A sample usage of this operator is: `example_string.find("str")`
- 'example_string' - the string being checked for a given substring.
- `.find("str")` - method call, which takes `"str"` as the substring being located within the string.

Example:
```
input_string = "test"

print(input_string.find("t"))
print(input_string.find("x"))
print(input_string.find("es"))
print(input_string.find("ets"))
```
Output:
```
0
-1
1
-1
```
> **Function VS Method**
> 
> A method must be called with an object attached to it, where the object is "the entity named before the method in the method call." A function does not require an object attached to it.
## Part 4

## Part 5

## Part 6

## Part 7