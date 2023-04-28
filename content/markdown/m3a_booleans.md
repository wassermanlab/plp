# a. Introduction to Variables: Boolean Data Type

# Chapter Summary

- [New Data Type: Boolean Values](https://www.notion.so/f5f23a119c9e47fc87766845eda927d2)
- [Boolean Operators](https://www.notion.so/f5f23a119c9e47fc87766845eda927d2)
- [Comparison Operators](https://www.notion.so/f5f23a119c9e47fc87766845eda927d2)
- [Combining Boolean and Comparison Operators](https://www.notion.so/f5f23a119c9e47fc87766845eda927d2)

# George Boole

- As we approach this module, we’ll be discussing Boolean values, named after George Boole, a famous mathematician who made significant contributions to algebra and logic.
- George Boole was born in England in the 1800s, to a typical working class family of not-so-successful cobblers.
- Although his family could only afford technical school, George’s love of education led him to consume works of famous mathematicians in his spare time, eventually securing teaching positions and opening his own school at age 19.
- George Boole is most known for his paper, 'An Investigation Into the Laws of Thought’, featuring many key concepts of computer science still used today.

![Portrait of George Boole](images/person1.png)

Portrait of George Boole

# The Lightbulb Example 💡

- When we flip the switch for a lightbulb in our house, there are usually only two states the light can be in:
  - On
  - Off
- We can’t really say that a light is both on AND off at the same time, right? Even if the light were flickering, it would still be either on or off at different times
- There is no way for a light to be both on and off at the same time. Similarly, we can apply this concept to the idea of True and False
- In real life, we can say things that might be both True and False, like, “February has 29 days”
  - This is both True and False because normally, February has 28 days, unless it is on a leap year, in which case February has 29 days — making the statement True and False
- However, in computer science, every statement that is made can only be either True or False. There is no in between, similar to the lightbulb example

# New Data Type: Boolean Values

- Remember in the previous modules, we learned how to assign different values to variables? We could make `x` equal a string, or different number data types like `int` and `float`
- A new data type we will be exploring in this module is the Boolean type, written as `bool`
- Unlike the other data types, the `bool` type only has two possible values:
  - `True`
  - `False`

### Syntax

- The structure of the `bool` declaration is as follows:
  - A variable name
  - A value stated as `True` or `False`
- The structure for declaring a boolean variable is the same as declaring any other variable, however, unlike strings, since `True` and `False` are special keywords in Python, `bool` variables do not need quotations or apostrophes surrounding the words:

```python
# string declaration needs "" or ''

x = "Hello"
y = 'World'
```

```python
# bool True / False are keywords

# note: both True and False need to be capitalized (true and false are not built
# into Python)

x = True
y = False
```

- Boolean values are considered a numeric type in Python, meaning they translate to numbers, where True = 1 and False = 0
- An empty `bool` variable is considered `False`
- This means you can perform numerical operations on `bool` values, just like `int` and `float`

```python
# num would print out 3
num = True + True + True
print(num)
```

### ‼️ Caution

- Since `True` and `False` are special keywords built-in to Python, you cannot use them as variable names to assign values to — this gives an error
- You can technically use `bool` as a variable name, but to avoid confusion, it’s not recommended

```python
# both of these gives a SyntaxError
True = 5
False = "Hello"
```

```python
# do not use bool as a variable name
bool = "Hello World"
bool = 5
```

### Creating a “Lightbulb Switch”

- We talked at the beginning about how a lightbulb can only be on or off, and how that is similar to how `bool` can only be `True` or `False`
- We can use this example and represent a lightbulb’s on/off state in code:

```python
# we must cast the bool value to a string to print it
switch = True
print("Lightbulb on: " + str(switch))
```

### Exercises

- Copy the “Lightbulb Switch” code and try changing the boolean value to see what happens
- Declare three additional variables as `True` or `False` and see what happens when you print them, here are some variables to get started:

```python
is_raining = False
likes_cake = True
is_student = False
# include your variables below here

print(is_raining)
print(likes_cake)
print(is_student)
```

- Try adding all these variables together and print them. What does this number represent?

# Boolean Operators

- We know that we can set variables to be `True` or `False`, but in the previous examples, we were only working with one variable
  - How do we work with more than one Boolean variable if we need to evaluate them together?
  - For example, how do we say that the weather outside is both raining AND cold at the same time? Both conditions are `True`
  - What if it is raining AND NOT cold? In this case, one condition is `True` and one condition is `False`
  - What if we don’t know the weather, so it can be either sunny OR rainy today?

### Syntax

- This is where understanding these 3 Boolean Logical Operators comes in:
  - `and` evaluates to `True` if all variables are `True` . `False` otherwise.
  - `not` evaluates to the opposite of the boolean value.
    - `not True` evaluates to `False`
    - `not False` evaluates to `True`
  - `or` evaluates to `True` when at least one variable is `True` . `False` otherwise.

### Summary of Boolean Operators

|     | Boolean Logical Operators | Evaluated Value |
| --- | ------------------------- | --------------- |
| and | True and True             | True            |
|     | True and False            | False           |
|     | False and False           | False           |
| not | not True                  | False           |
|     | not False                 | True            |
| or  | True or True              | True            |
|     | True or False             | True            |
|     | False or False            | False           |

Here are some examples using variables:

```python
is_raining = True
is_cold = True
is_sunny = False

raincoat = is_raining and is_cold
sweatshirt = not is_raining and is_cold
umbrella = is_raining or is_sunny

print("I need to grab my umbrella: " + str(umbrella))
print("I need to grab my raincoat: " + str(raincoat))
print("I need to grab my sweatshirt: " + str(sweatshirt))
```

### Exercises

- Try copying the code above and playing around with the different boolean values for `is_raining`, `is_cold`, and `is_sunny` to see how the print statements change
- Try writing your own version of different weather combinations using logical operators. Here are some examples to get you started, but try coming up with your own:

```python
sunny = True
humid = True
school_day = False

swimming = sunny and humid and not school_day
sunglasses = sunny and humid
sweater = not humid and not sunny
walk_home = not humid or school_day

print("I will go swimming today: " + str(swimming))
print("I will wear sunglasses today: " + str(sunglasses))
print("I should wear a sweater today: " + str(sweater))
print("I will go on a walk today: " + str(walk_home))
```

- Understanding why the result is `True` or `False` is extremely important in programming, that will come up again and again in the future
  - In the exercise below, read the values of a, b, c, and d, then answer what you think the expression will evaluate to for each question. After you have attempted this, run the program to check your answers.
  - For extra practice, you can change the boolean values for a, b, c, and d, which will create new questions you can try to solve.

```python
# DON'T RUN THE PROGRAM YET

a = True
b = False
c = True
d = False

# Determine if the following expressions will evaluate to true or false, then
# run the program to check!

first = a and (b or d)
# first answer:

second = (b or d) or c
# second answer:

third = (a or d) and (b or c)
# third answer:

fourth = not b and d
# fourth answer:

fifth = (d or not a) or not a
# fifth answer:

print("First expression: " + str(first))
print("Second expression: " + str(second))
print("Third expression: " + str(third))
print("Fourth expression: " + str(fourth))
print("Fifth expression: " + str(fifth))
```

# Comparison Operators

- We learned previously that logical operators can compare two Boolean variables using `and`, `or` as keywords to produce another Boolean output of `True` or `False`
- We can expand on this further by talking about comparison operators, which are similar to inequalities that you might have come across in math class
- Comparison operators are used to compare two values, which can also be variables
- Here is a table of comparison operators in Python that you can use:
  | Operator | Name                     | Example |
  | -------- | ------------------------ | ------- |
  | ==       | equal                    | x == y  |
  | !=       | not equal                | x != y  |
  | >        | greater than             | x > y   |
  | <        | less than                | x < y   |
  | >=       | greater than or equal to | x >= y  |
  | <=       | less than or equal to    | x <= y  |

### Syntax

- Comparison operators can only equal `True` or `False`

```python
# 0 is not greater than 2,
# so the result prints False
x = 0
y = 2
result = x > y
print("Is x greater than y? " + str(result))
```

```python
# x and y are both 5,
# so the result prints True
x = 5
y = 5
result = x == y
print("Is x and y the same? " + str(result))
```

- It is also possible to combine mathematical equations when using comparison operators:

```python
# the result prints True
result = (3 * 7) >= (2 * 9)
print("Is 3*7 greater than or equal to 2*9? " + str(result))
```

- In these examples above, we used `int` values, but comparisons also work well with `string`

```python
# joe and kate are not the same name, so the result prints True
name1 = "Joe"
name2 = "Kate"
result = name1 != name2
print("Do they have different names? " + str(result))
```

- You can even use `>` and `<` operators when comparing strings. In these cases, it would compare the words based on alphabetical order, similar to how you would organize book authors by a-zA-Z at the library
- ‘A’ would be considered the “smallest number”, and ‘Z’ would be the “largest number”
- However, lowercase letters are considered greater than uppercase letters. For example, ‘a’ would be greater than both ‘A’ and ‘Z’.

```python
author1 = "Rowling, JK"
author2 = "Christie, Agatha"
author3 = "clare, cassandra"

# the result is False, since C comes before R
result = author2 > author1
print("Does Christie's books go after Rowling? " + str(result))

# the result is True, since c comes before C
result = author3 > author2
print("Does Christie's books go after clare's? " + str(result))
```

### Exercises

- If `a = 5` and `b = 10`, how would you write, using comparison operators, that one variable is greater than the other?
  - What would be the output of `a == b`?
  - What would be the output of `a != b`?
- If the expression was `x > y > z`, what values could you declare for `x`, `y`, and `z` to make this statement print `True`? How about to make it print `False`?
- Try to determine what the result of the following questions below will be, then run the program to check your answers:

```python
# DON'T RUN THE PROGRAM YET

a = "Harry"
b = "Ron"
c = "Snape"
d = "Hermione"
e = "Harry"

# Determine if the following expressions will evaluate to true or false,
# then run the program to check!

first = a > b
# first answer:

second = c != d
# second answer:

third = a == e
# third answer:

fourth = d <= a
# fourth answer:

fifth = a >= e
# fifth answer:

print("First expression: " + str(first))
print("Second expression: " + str(second))
print("Third expression: " + str(third))
print("Fourth expression: " + str(fourth))
print("Fifth expression: " + str(fifth))
```

# Combining Boolean and Comparison Operators

- You can combine the two types of operators in order to create more complex expressions
- If we want to represent a very specific condition, we would need multiple phrases to get the result, similar to using boolean and comparison operators
- For example, think of snow days at school. For a snow day to happen, there is likely a certain criteria that needs to be met; we can specify the conditions ourselves in this example:
  - Let’s say the weather needs to be below -15 degrees Celsius
  - The roads have to have NOT been plowed
  - It needs to be on a weekday
  - It must be during the school semester
  - It cannot be on a holiday
- We can define these variables in code, like this:

```python
weather = -20
roads_plowed = False
weekday = True
school_semester = True
holiday = False

snowday = weather < -15 and not roads_plowed and weekday and school_semester and not holiday

print("Is today a snowday? " + str(snowday))
```

- Notice how we combined `<`, `not`, `and` keywords to create a `snowday` boolean variable that prints `True` if the conditions are met
- There are endless possibilities to how you can combine these operators and we hope you can see how useful they are for determining if conditions are met

### Exercises

- Try copying the above snowday code and change the variables of `weather`, `roads_plowed`, `weekday`, `school_semester`, and `holiday` to different values and see how that changes the result
- Create your own situation and write out different conditions that need to be met, similar to the example! Some topics to get you started could be:
  - How do you decide if it’s a good beach day?
  - What ingredients are needed to create your favorite dish?
  - What tasks do you do before you leave for school in the morning?

# Unit Project — Lightbulb Wiring

Scenario: You are an electrician. Somebody hires you to wire a new room in their house, which has two connected light switches. This client wants their room wired so **that flipping one of the light switches causes all the lights in the room to flip on or off.** Being the savvy electrician that you are, you decide to first test out your wiring in Python using a boolean expression.

![Untitled](images/light.png)

A boolean expression is a logical statement that is either TRUE or FALSE. It consists of multiple true/false statements connected by the logical connectors: `and`, `or`, or `not`.

For example, the following are boolean expressions:

- “I have access to a car AND I need groceries” gives a truth value for whether you will go drive to the grocery store.
- "I have eggs AND I have a stove AND (I have a pan OR I have a skillet)" gives a truth value for whether or not you can cook an omelette.
- "My tire pressure is low OR my check-engine light is on OR (NOT my radio works)" gives a truth value for whether something is wrong with my car.

```python
#we will call the two switches, switch 1 and switch 2.
switch_1 = False
switch_2 = False

#Using these values, you will construct a boolean expression (consisting of logical connectors)
#whose truth value represents the state of the lights in the room (on/off). Flipping a switch's truth value
#must always flip the truth value of your boolean expression.

is_room_lit = True #replace True with your boolean expression

#try to consider all the possible combinations of lightswitches!
```

<aside>
🤔 **Challenge!**

Once you figure out two light bulbs, try to model a three light-bulb system!

</aside>

# Feedback Form

Please take a moment to provide your thoughts on this module.

[Module 3a (Boolean Data Type) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSd5hHRxBN3zlGBm5MTvAFBOir5KAoP5oxIf0ocKXEU6eemoaw/viewform?usp=sf_link)

# Further Readings / Additional Content

### A Deeper Look into How String Comparisons Work

[Python Compare Strings | How does String Comparison Works in Python?](https://www.educba.com/python-compare-strings/)

### More About How Boolean Operator Values Work with Logic Gates

[Logic Gates in Python - A Beginner-Friendly Guide - JournalDev](https://www.journaldev.com/42242/logic-gates-in-python)
