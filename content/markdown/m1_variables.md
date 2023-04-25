# 1b. Variables

<aside>
📌 Key points: What is a variable, writing variables in Python, naming conventions.

</aside>

# Introducing: Variables

### Intro - the first computer program

![Portrait of Ada (c. 1836)](images/Ada-Lovelace.jpg.webp)

Portrait of Ada (c. 1836)

![Portrait of Charles Babbage (c. 1820)](images/British_(English)_School_-_Charles_Babbage_(17921871)_-_814168_-_National_Trust.jpg)
Portrait of Charles Babbage (c. 1820)

> “Imagination is the Discovering Faculty, pre-eminently. It is that which penetrates into the unseen worlds around us, the worlds of Science.” - Ada Lovelace
> 

Augusta Ada King, Countess of Lovelace, or Ada Lovelace for short, was an early 19th century English mathematician and writer. 

She is perhaps best known for her work with the English polymath Charles Babbage on one of the world’s first computers, called the difference machine, a machine for performing complex mathematical calculations. 

Ada saw the potential of such a machine to carry out operations beyond numerical calculation and wrote the first computer algorithm for a newer machine called the analytical engine. As a result, she is seen today as the first true computer programmer! 

![Part of Charles Babbage’s Difference Machine](images/440px-Difference_engine_plate_1853.jpg)

Part of Charles Babbage’s Difference Machine

Take a look at Ada’s algorithm below. What parts you recognize? How do you think the code is executed? What do you think it’s purpose is? Her code, written in 1840, is very similar to the modern programs that we write in languages like Python today.

![Ada Lovelace’s first program](images/Diagram_for_the_computation_of_Bernoulli_numbers-2.jpg)

Ada Lovelace’s first program

Notice that many of the column’s labels include the word “variable”. This concept was one of the core ideas of Ada and Babbage’s work and is a core concept in modern programming.

## What is a variable?

A variable is something that is used to store information. Here are some examples.

```python
animal = "bat"                    # this is a **string** data type

is_it_afternoon = True            # this is a **boolean** data type

temp = -109                       # this is a **integer** data type

distance_from_sun = 29283.19      # this is a **float** data type

# you'll learn about the different data types in the upcoming modules :)
```

We give variables unique names that are referenced later on in our code. When referenced, we can use the variable as a stand-in for the data contained by the variable.

```python
animal = "bat" 

"Hello " + "my favourite animal is a " + animal    # reference to animal variable 
```

While you might not have used variables in the context of computer programming before, you already use them all the time in your daily life.

- In math, x and y are common names for variables that reference a particular number or equation
- In English, we use “they”, “them”, “he”, “she”, or any other pronouns as variables that can be used to reference particular people

Similarly, we “assign” some data to a variable in a computer program. After the “assignment”, we can use the variable’s name to reference the stored data.

## Variables in Python

In Python, we name a variable and assign data to it at the same time.

The syntax for this is:

```python
name = data
```

**Name** always comes first and can be any combination of letters, numbers, and underscores. Names are case-sensitive, so Python will see “name” and “NAME” as two different variables.

The **data** field can be of any type.

Variables can be re-assigned multiple times to different pieces of data. Re-assigning a variable replaces its previous value.

```python
x = "3"

print(x)    # output: 3

x = "5"     # the variable x now stores “5” instead of “3”

print(x)    # output: 5
```

### Naming Conventions

Programmers have adopted conventions that, while not necessary to make a program work, make code much easier to read and share with others. Have you noticed that readability and collaboration are very important themes in programming?

A couple adopted conventions for naming your variables:

1. Start all variable names with a lowercase letter or a number
2. If more than one word is in a variable name, separate words with an underscore. 

Try to explain why each of the following follows naming conventions or not!

<aside>
👍🏼  **Correct naming**

this_is_a_variable_name

test_file_small_1

garage 

</aside>

<aside>
👎🏼 **Incorrect naming**

Incorrect

this_Is_Incorrect

this-is-alsoIncorrect

</aside>

## Exercises

Copy each of the following exercises to your Raspberry Pi and complete.

**Exercise 1: Assigning Variables** 

```python
# Assign your name, the grade that you're in, and school that you attend to 
# variables named "name", "grade", and "school" (without the quotation marks). 
# Run the program after you have done so. If you successfully assigned all 
# variables, the program should print a short summary about yourself.

# Assign variables here. 

name = 

grade = 

school = 

def printSummary():
    print("My name is " + name + ",")
    print("and I am in grade " + grade + " at " + school + "." )

printSummary()
```

**Exercise 2: Following Assignment Statements** 

```python
# Consider the following variable assignments. 
# Please follow the instructions below. When you're done, run the code. 
# You should see 5 "true" statements printed to the console if correct.

x = "3"
y = "5"
z = "10"

x = "5"
# What value does x now contain? Replace ... with your answer.
x_answer1 = "..."

y = x
# What value do x and y now contain? Replace ... with your answer.
y_answer1 = "..."
x_answer2 = "..."

x = z
# What value does x now contain? Replace ... with your answer.
x_answer3 = "..."

z = y
z = x
x = z
# What value does z now contain? Replace ... with your answer.
z_answer1 = "..."

# code to check your answers (you can ignore):
print(str(bin(ord(x_answer1))) == "0b110101")
print(str(bin(ord(y_answer1))) == "0b110101")
print(str(bin(ord(x_answer2))) == "0b110101")
print((str(bin(ord(x_answer3[0]))) + str(bin(ord(x_answer3[1])))) == "0b1100010b110000")
print((str(bin(ord(z_answer1[0]))) + str(bin(ord(z_answer1[1])))) == "0b1100010b110000")

```

# Feedback Form

Please take a moment to provide your thoughts on this module.

[Module 1a (Introduction to Variables & Strings) - Feedback form](https://forms.gle/yVkU8mxvb6ZbVmWb6)
