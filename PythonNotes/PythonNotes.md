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
- [Part 3](#part-3)
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
## Part 3

## Part 4

## Part 5

## Part 6

## Part 7