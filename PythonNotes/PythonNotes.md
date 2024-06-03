# Python Notes

## Part 1
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