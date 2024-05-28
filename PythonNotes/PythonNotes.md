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