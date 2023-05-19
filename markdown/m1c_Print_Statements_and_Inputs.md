# b. Print Statements and Inputs

# Chapter Summary

- [Print Statements](https://www.notion.so/b-Print-Statements-and-Inputs-f5bf9c009e2f41f1989b7a392a7ab6ef)
- [Concatenation of Strings](https://www.notion.so/b-Print-Statements-and-Inputs-f5bf9c009e2f41f1989b7a392a7ab6ef)
- [Inputting Values](https://www.notion.so/b-Print-Statements-and-Inputs-f5bf9c009e2f41f1989b7a392a7ab6ef)

# Print Statements

- Previously, we learned about how different values of strings can be assigned to variable names, such as: `name = “John”` or `name = 'John'`
- We know that the computer knows that, but how would other people see the name that you assigned to the variable?
- A great way to display things on the *console* (area where any outputs will be shown) is to use something called **print statements**
- For example, copy these lines of code into your IDE and run it to see what shows up:

```python
print("Hello World")
```

```python
print('The weather is rainy again today')
```

- We can see how the text we have entered inside the quotation marks (””) or apostrophes (’’) end up getting displayed in our IDE, called the *console*

## Syntax

- Try implementing your own `print` statements using the following syntax:

```python
print("text goes here")
```

```python
print('text goes here')
```

- For the statement to display properly, there must be a pair of quotation marks `''` or apostrophes `""` surrounding what you would like to print
- You can also input nothing into the print statement, which creates a new line space, similar to if you hit enter for a new paragraph on a text editor — try this out!

```python
# prints a blank line

print()
```

```python
# you can see the space between "Hello" and "World" 

print("Hello")
print()
print("World")
```

- Using what we’ve learned about variables in the previous module, we can even declare a string variable, store a message, and use the variable name to print it out!

```python
message = "This whole message can be printed by just typing in the variable name"
another_message = 'Try this out yourself!'

print(message)
print(another_message)
```

## Exercises

- Create some print statements that introduce yourself! Write your name, what grade you’re
in, and any hobbies/interests
    - If you’re stuck, you can try out this template to give yourself a start.
    
    ```python
    print("Hi everyone! My name is ________")
    print("I'm in grade ___ and I like to do __________ in my free time")
    ```
    
- Try putting some of these values in variables and then using the variable names in your introduction message. Are you able to create the same print outputs?
- What do you think the advantage of putting things in variables is versus writing everything out?

## String Formatting

- Along with letters and numbers, we might want to be able to format our strings in different ways, like adding new lines or new spaces without manually doing these things in our print statements
- Additionally, what do we do if we want to use quotation marks in our `print` statement?
    - Try printing a message that contains quotations marks, see what happens
    - You will notice that an error message is given, since python uses quotations as a special character to declare strings!
- In order to use special characters and add new lines/spaces, we need to use the escape character `\` in our strings to have it print out what we would like:

| String Formatting | Special Character | Usage Example | Output Example |
| --- | --- | --- | --- |
| New Line  | \n | “123\n45” | 123
45 |
| Tab Space | \t | "123\t45” | 123        45 |
| Backslash | \\ | "123\\45” | 123\45 |
| Quotation | \” | "123\”Hello\”45” | 122”Hello”45 |
| Multiple Lines | “” and “” | “Hello”
”World” | Hello
World |
- If we want our strings to span multiple lines, we can enclose each line in its own double quote, for example:

```python
# strings can span multiple lines

print("You can break up long strings"
      " into multiple lines, but "
			"remember to include spaces")
```

```python
# combining ' and " to print

print('"This will show as a quote"')
print("'This will show in apostrophes'")
print("\"Using escape before works too\"")
```

## Exercises

- Need to add Samuel’s previous exercises that cannot be accessed

# Concatenation of Strings

- When we merge two strings together, we call this string concatenation
- There are many ways to combine strings together to print out word combinations or even create entirely new strings that can be stored in different variables!
- We can use different operators to concatenate strings. Try running the following blocks of code and explain what they do. If you encounter any errors, try to explain why.

```python
print("Hello " + "World")
```

```python
str1="Hello"
str2="World"

str=str1+str2

print(str)
```

```python
print("Hi"*4)
```

```python
print(5 + "1")
```

# The `input()` function

- The `input()` function is one of Python’s many built-in functions
- It allows user input
- The syntax of the function is `input(*prompt*)` where the prompt is a `String`
- Take a look at the following examples

**Example 1**

```python
day = input("What day is it today?:")
print("Today is" + " " + day)
```

**Example 2**

```python
before_tax = input("How much does a milkshake cost? (approximately):")
tax = 1.05
total_after_tax = tax * float(before_tax)
print("Your milkshake after tax is " + "$" str(total_after_tax))
```

### **Exercise: Total after Tax**

- We will be building on example 2 in this exercise.
- Lets say a milkshake costs $8.11, but if we input that number, we will notice that after tax, the milkshake would cost $8.5155! Have you ever paid x.xxxx amount?
- Then try to value $0. You’ll notice that it only has one decimal place, but what if we wanted to keep it to two decimal places?
- Lets ensure that our total cost is rounded to two decimal places and has exactly two decimal places using the `str.format()` built-in function. You learn how to use it [here](https://www.adamsmith.haus/python/answers/how-to-print-a-float-with-two-decimal-places-in-python).

# Feedback Form

Please take a moment to provide your thoughts on this Module 1a.

[Module 1b (Using and Displaying Data: Print Statements and Inputs) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSfI_-IodU6mbMNONS5Qd33Tt4lEGB1s1LKl3x2tv6cs8VOISQ/viewform?usp=sf_link)