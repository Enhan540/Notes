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
    - Section 3: [More Loops](#more-loops)
    - Section 4: [Defining Functions](#defining-functions)
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

### More Loops
Earlier, the `break` command was introduced when the concept of looping was first introduced. It allows the code to immediately break out of the loop. An example of when it can be used is when the program asks for an input and only stops when a specific input is given.

However, the `break` command can be replaced with a condition. In the following example, two versions of a program, one with the `break` command and one without, are shown, which gives the sum of all the numbers given by the user until `-1` is given.
```
sum = 0

while True:
    number = int(input("Please type in a number. Type -1 to exit."))
    if number == -1:
        break
    sum += number
print(f"The sum is {sum}.")
```
```
sum = 0
number = 0

while number != -1:
    number = int(input("Please type in a number. Type -1 to exit."))
    if number != -1:
        sum += number
print(f"The sum is {sum}.")
```
Example Output:
```
Please type in a number, -1 to exit: 2
Please type in a number, -1 to exit: 4
Please type in a number, -1 to exit: 5
Please type in a number, -1 to exit: 3
Please type in a number, -1 to exit: -1
The sum is 14.
```
Both programs do the exact same thing, but the first method is easier, since the condition `number == -1` is only required once and the `number` variable does not need to be initialized before the loop.

The `break` command can be used with another condition when creating a loop. Using the same program as before, if we add another constraint where the program stops prompting the user for another number when the sum becomes larger than 100, we can use both a condition for the loop and the `break` command.
```
sum = 0

while sum < 100:
    number = int(input("Please type in a number. Type -1 to exit."))
    if number == -1:
        break
    sum += number
print(f"The sum is {sum}.")
```
#### The 'continue' Command
The `continue` command is another command that can change the way a loop is executed. When executed, the `continue` command jumps back to the beginning of the loop and checks the condition of the loop again. 

If we modify the previous example again by making it so a number greater than or equal to 10 will not be added to the sum, and will return to the beginning of the loop. 
```
sum = 0

while True:
    number = int(input("Please type in a number, -1 to exit: "))
    if number == -1:
        break
    if number >= 10:
        continue
    sum += number

print (f"The sum is {sum}")
```
Example Output:
```
Please type in a number, -1 to exit: 4
Please type in a number, -1 to exit: 7
Please type in a number, -1 to exit: 99
Please type in a number, -1 to exit: 5
Please type in a number, -1 to exit: -1
The sum is 16
```
#### Nested Loops
Similarly to `if` statements, loops can be placed and nested inside other loops. 

With nested loops, the `break` and `continue` commands work with the loop it is within.

#### More Helper Variables with Loops
We've used helper variables to help with iteration, increasing or decreasing every time a loop runs. The following example uses the helper variable `i`.
```
limit = int(input("Please type in a number: "))
i = 0
while i < limit:
    print(i)
    i += 2
```
Output:
```
Please type in a number: 8
0
2
4
6
```

If we implement a nested loop into the previous program to create a "number pyramid" based on the number given by the user, the code would look something like this:
```
number = int(input("Please type in a number: "))
while number > 0:
    i = 0
    while i < number:
        print(f"{i} ", end="")
        i += 1
    print()
    number -= 1
```
Output
```
Please type in a number: 5
0 1 2 3 4
0 1 2 3
0 1 2
0 1
0
```
> Two helper variables are used in this program: `number` and `i`. Each iteration of the loop decreases the value of `number` by 1 until it reaches 0. Inside the outer loop, the helper variable `i` is set to 0 just before the inner loop, which prints out the value of `i`, increases its value by one, and repeats until `i` is no longer less than number. 

### Defining Functions
We've used functions before, such as the `len`, `print`, and `input` functions, which are built into Python. However, it is possible to create/define your own functions.

#### The Function Definition
To use a function, it must be defined. The `def` keyword (short for define) is used when defining a function. Following the `def` keyword is the **function's name**. After the name, parentheses followed by a colon completes the heading. Then, the body, which is the part that actually is executed, follows the heading.

For example, this function called `testFunction`, prints the message `This is a test function.`
```
def testFunction():
    print("This is a test function.")
```

Nothing will happen until the function is called, which can be done by mentioning the name in the code:
```
def testFunction():
    print("This is a test function.")

testFunction()
```
Output:
```
This is a test function.
```

#### Function Arguments
Functions usually take arguments, which may change what the functionality of the function. The `print` and `input` both take arguments to be printed.

An example of a function using an argument:
```
def hello(target):
    print("Hello", target)
```
Calling this function twice would produce the following output:
```
hello("Emily")
hello("world!")
```
```
Hello Emily
Hello world!
```

If we take a look at the definition of the function, `target` is found within the parenthesis, which is normally left blank. In this case, `target` would be the function's parameter. 

The parameter is used when an *argument* is passed when the function is called, which is done by calling the function with the data in the parenthesis. 

In the previous function example, the `hello` function calls were given two different arguments: `Emily` and `world!` These arguments will be used by the function with the `target` parameter, which stores the argument's data.

> **Arguments vs Parameters**
> 
> They are pretty much interchangeable, but they're slightly different. 
> - the **argument** is the data passed *into* the function.
> - the **parameter** is the local variable used by the function which contains the argument as data

#### More Examples
Another function using an argument is the following:
```
def squared(x):
    print(f"The square of the number {x} is {x*x}")

squared(2)
sqaure(5)
```
Output:
```
The square of the number 2 is 4
The square of the number 5 is 25
```
## Part 4

### More Functions
Last section, the concept of defining and using functions was introduced.

Using the `def` keyword to create the function:
```
def message():
    print("This message was brought to you by a function.")
```
Then calling the function:
```
message()
```
Output:
```
This message was brought to you by a function.
```

#### Parameters and Arguments of a Function
A function can take one or more arguments which the function will use within its code. The arguments will be put into the function's parameters, which the function will use as its local variable(s). 

#### Function Calls Witihin Function Calls
It is possible to call other functions within a function's code. In the following example, the function `greet_many_times` calls the `greet` function:
```
def greet(name):
    print("Hello there,", name)

def greet_many_times(name, times):
    while times > 0:
        greet(name)
        times -= 1
```
Output:
```
Hello there, Emily
Hello there, Emily
Hello there, Emily
```

#### Return Value of a Function
On top of taking arguments, an function can also return a value. An example is the `print` commmand, which returns the user's input. 

Another is the `int` command, which takes in an argument and returns it as an integer if possible.

#### Return Statement
You can return values using the `return` keyword within the function. For example:
```
def my_sum(a, b):
    return a + b

result = my_sum(2, 3)

print("Sum:", result)
```
Output
```
Sum: 5
```
> Using the `return` statement completely ends the function. Meaning no other code in the function will be run once a value is returned.

Another example is:
```
def ask_for_name():
    name = input("What is your name? ")
    return name

name = ask_for_name()
print("Hello there,", name)
```
Output
```
What is your name? Anna
Hello there, Anna
```
Even if there is no value to be returned, the `return` command can be used to stop the function's execution.

#### Using Return Values from Functions
Return values can already be put into variables. Since it's just like any other value, it can just be directly used as another argument, like the `print` command.

Example:
```
def my_sum(a, b):
    return a + b

print("The sum is", my_sum(4, 6))
```
Another example of using the return values directly is:
```
def my_sum(a, b):
    return a+b

def difference(a, b):
    return a-b

result = difference(my_sum(5, 2), my_sum(2, 3))
print("The result is", result)
```
Output:
```
The result is 2
```
> In this example, the two function calls of `my_sum` returns two values, each being an argument for the function `difference`.

#### Difference Between Return and Print
There is a difference between returning a value versus printing a value inside a function. Take the following code for example:
```
def max1(a, b):
    if a > b:
        return a
    else:
        return b

def max2(a, b):
    if a > b:
        print(a)
    else:
        print(b)

result = max1(3, 5)
print(result)

max2(7, 2)
```
> Both functions `max1` and `max2` essentially do the same thing, just in different ways. `max1` returns a value, which is then printed by a command outside of the function. `max2` directly prints the value from within the function without returning any value.
> 
> Generally, it is better to use functions with return values since it is more versatile and allows for those return values to be used elsewhere and by other functions.

#### The Type of the Argument
The types of arguments we have seen so far are:
- integer
- float numbers
- strings
- Boolean values

A function can take any of these data types as an argument. When giving arguments to a function, it will run correctly if the parameters are the right type. Giving the wrong type of argument to a function may cause it to be unable to execute properly or even at all. 

To make sure a function receives the right type of argument, a *type hint* can be used to indicate what type of argument should be expected:
```
def print_many_times(message : str, times : int):
    while times > 0:
        print(message)
        times -= 1
```
> In this function, the arguments include a small extra portion which shows the expected argument type. The ` : str` after the `message` argument shows that message should be a string type.

The return type can also be indicated/hinted when defining the function. It can be done as shown:
```
def ask_for_name() -> str:
    name = input("Mikä on nimesi? ")
    return name
```
> The ` -> str` portion of the function header hints that the return value will be a string.

### Lists
So far, we've used variables to store data. But things get a bit clustered when too many variables need to be tracked and maintained.

Another method of storing data is by using a *list*. A list is a collection of values which is accessed via a single variable name. The contents of the list, which are referred to as the list's *elements* or *items*, are surrounded by brackets.

Creating a new, empty list can be done by:
```
my_list = []
```
and creating a list with items, in this case five items, can be done by:
```
my_list = [7, 2, 2, 5, 2]
```

#### Accessing Items in a List
Accessing items in a list can be done using an index, just like taking characters from a string. The first item has the index of 0, meaning the index is the order of the item minus 1. 

By placing the index inside brackets, you can access that certain item.
```
my_list = [7, 2, 2, 5, 2]

print(my_list[0])
print(my_list[1])
print(my_list[3])

print("The sum of the first two items:", my_list[0] + my_list[1])
```
Output:
```
7
2
5
The sum of the first two items: 9
```
To print the whole list, print the list with no bracket and index.
```
print(my_list)
```

With lists, the contents can be changed, even individual elements can be changed to something else. 
```
my_list = [7, 2, 2, 5, 2]
print(my_list)
my_list[1] = 3
print(my_list)
```
```
[7, 2, 2, 5, 2]
[7, 3, 2, 5, 2]
```

To find the number of items in a list, the `len` function can be used:
```
my_list = [7, 2, 2, 5, 2]
print(len(my_list))
```
```
5
```

#### Adding Items to a List
Using the `append` method adds items to the end of a list. For example:
```
numbers = []
numbers.append(5)
numbers.append(10)
numbers.append(3)
print(numbers)
```
```
[5, 10, 3]
```

#### Adding to a Specific Location
You can add an item into a specific location without removing any other items with the `insert` method. The way this method works is by placing the new item into the given position while moving all items at the given position and after down one position, or up one index. An example of this is:
```
# insert(index, value)

mylist = [1, 2, 3, 4, 5]
print(mylist)
mylist.insert(2, 6)
print(mylist)
```
```
[1, 2, 3, 4, 5]
[1, 2, 6, 3, 4, 5]
```

#### Removing Items From a List
There are two different methods that can remove items from the list:
- if the `index` of the item is known, the `pop` method should be used
- if the `contents` of the item are known, the `remove` method should be used

The `pop` method takes the index of the item to be removed as its argument.
```
mylist = [1, 2, 3]
print(mylist)
mylist.remove(1)
print(mylist)
```
```
[1, 2, 3]
[1, 3]
```
> Once this method removes an item, the other items in the list with a larger index drop to fill in the gap. 
> 
> On top of that, the `pop` method removes AND returns the value that was just removed.

The `remove` method takes the value of the item itself as the argument, and then removes that from the list.
```
my_list = [1, 2, 3, 4, 5, 6, 2]

my_list.remove(2)
print(my_list)
my_list.remove(5)
print(my_list)
```
```
[1, 3, 4, 5, 6, 2]
[1, 3, 4, 6, 2]
```
> This method removes the *first* occurrence of the value in the list. 

If the specified item is not in the list, the `remove` method causes an error. The `in` operator, the same one used with strings, can check whether a certain item is in a list:
```
my_list = [1, 3, 4]

if 1 in my_list:
    print("The list contains item 1")

if 2 in my_list:
    print("The list contains item 2")
```
```
The list contains item 1
```

#### Sorting Lists
The method `sort` rearranges the contents of a list from least to greatest.
```
my_list = [2,5,1,2,4]
my_list.sort()
print(my_list)
```
```
[1, 2, 2, 4, 5]
```

This method changes the original list. So, if the previous list is still needed, the `sorted` function can be used to return a sorted list:
```
my_list = [2,5,1,2,4]
print(sorted(my_list))
```
```
[1, 2, 2, 4, 5]
```

> Sort VS Sorted
> 
> The `sort` method sorts the list itself, while the `sorted` function returns a sorted list without altering the original list.


#### Maximum, Minimum, and Sum
The functions `max` and `min` return the greatest and smallest items in a list, respectively. The function `sum` gives the sum of all the items in a list.
```
my_list = [5, 2, 3, 1, 4]

greatest = max(my_list)
smallest = min(my_list)
list_sum = sum(my_list)

print("Smallest:", smallest)
print("Greatest:", greatest)
print("Sum:", list_sum)
```
```
Smallest: 1
Greatest: 5
Sum: 15
```
#### Methods VS Functions
**Methods** are one way to process lists. For example, the `append` and `sort` methods that are used on the list. To use methods, the dot operator and the method name are placed after the list that the method will be used on.

**Functions** are another way to process lists. They take lists as an argument and returns a result, just like the functions `len` and `sorted`.

#### A List as an Argument or a Return Value
When defining a new function, it is possible to set the argument type and/or return type as a list. For example, the following function takes in a list and returns the median value:
```
def median(my_list: list):
    ordered = sorted(my_list)
    list_centre = len(ordered) // 2
    return ordered[list_centre]
```
> This function sorts the given list and then returns the middle item. The `//` operator is used here since lists with an odd number of items would return a float and not an integer if the middle number was attempted to be found using the `/` operator.

An example of the function working is:
```
shoe_sizes = [45, 44, 36, 39, 40]
print("The median of the shoe sizes is", median(shoe_sizes))

ages = [1, 56, 34, 22, 5, 77, 5]
print("The median of the ages is", median(ages))
```
```
The median of the shoe sizes is 40
The median of the ages is 22
```

A function could also return a list. In the following example, the function returns a list after taking user inputs until a 0 is inputted:
```
def input_numbers():
    numbers = []
    while True:
        user_input = input("Please type in an integer, leave empty to exit: ")
        if len(user_input) == 0:
            break
        numbers.append(int(user_input))
    return numbers
```
An example usage of this function:
```
numbers = input_numbers()

print("The greatest number is", max(numbers))
print("The median of the numbers is", median(numbers))
```
```
Please type in an integer, leave empty to exit: 5
Please type in an integer, leave empty to exit: -22
Please type in an integer, leave empty to exit: 4
Please type in an integer, leave empty to exit: 35
Please type in an integer, leave empty to exit: 1
Please type in an integer, leave empty to exit:
The greatest number is 35
The median of the numbers is 4
```
> This example shows how functions can be useful: they make code more readable and compact in its own way.

These are only a few things that can be done with lists. The Python  documentation contains many more methods and functions that can be done with lists.

## Part 5

## Part 6

## Part 7