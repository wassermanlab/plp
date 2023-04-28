# b. Using Conditionals: if, elif, and else statements

<aside>
📌 **Key points: control flow, structuring conditional statements**

</aside>

In this module we will explore a conditional, or “control flow” command. A conditional statement is a “switch” in your code that will only perform some specific behaviour if a certain condition is satisfied. The simplest of these commands is the “if” statement.

- `if` statements are organized into “blocks”.
- Each “block” checks to see if a condition in your code is `True`. If true, one or more lines of code will be executed. If `False`, this code is skipped over.

## If, Elif, and Else Statements: **Controlling the “flow” of code**

### `if` clause

All the code we have written so far has:

- executed every single line (there are no “skipped” lines)
- produced the same result every time

With `if` statements, we can write code that will:

- execute a line of code in one circumstance and “skip” it in others
- perform different functions based on the data we input

`**if` clause syntax:**

```python
x = True

if (x):
	y = 1 + 2
	print(y)
```

- If statements can be read like a sentence: “If x is true, do y.” If x is `True`, the code underneath the if statement will be executed. In this case, x is `True` so `y = 1 + 2` will be executed and the number 3 will be printed. If x is `False`, nothing will happen.
- Note: The specified condition must result in a boolean data type. Otherwise, the compiler will throw an error message. Try it out yourself!

### `else` clause

What if we want to run one line of code if x is true, and a different line of code if x is false? One inefficient way to do this would be to include a second “if” statement that only executes if x is false:

```python
x = 8

if (x < 10):                                    # first if statement
	print("input is less than 10")
if (x >= 10):                                   # second if statement
	print("input is greater than or equal to 10")
```

However, there is a simpler way to implement our desired behaviour by using an `else` operator.

`**else` operators:**

- are placed at the bottom of an `if` statement “block”
- will execute only if all conditionals in the `if` statement “block” above evaluate to false.

`**else` clause syntax**:

```python
x = 12

if (x < 10):
	print("input is less than 10")
else:
	print("input is greater than or equal to 10")
```

Code involving if-else statements can be read: “if x is true, do y*,* otherwise do z”.

### `elif` clause

So far, we have seen that `if` and `else` statements can be used to evaluate if a value satisfies a single truth condition. However, what if a value needs to be evaluated against multiple different but related truth conditions?

In this case, we would use  `elif` statements to consider multiple conditions of an if/else statement. 

`elif` **statements:**

- have their own associated condition
- can be added an arbitrary number of times after an `if` statement but before the `else` statement
- will only execute if all the conditional “if” statements above it are false.

An elif statement is added between  `if` and `else` statements. The group of statements, referred to as a “block”, will evaluate from top to bottom until one condition produces true or there are no clauses left to evaluate, in which case the `else` statement would be executed. 

`**elif` clause syntax:**

```python
month = "February"
looking_forward_to = ""

if month == "December":               # first if clause
	looking_forward_to = "Winter Break"
elif month == "February":             # elif clause 1
	looking_forward_to = "Valentines Day"
elif month == "January":              # elif clause 2
	looking_forward_to = "New Years"
else:                                 # else clause
	looking_forward_to = "the weekend"

print("I am looking forward to " + lookingForwardTo + "!") #print statement
```

<aside>
💡 **Once an if or elif statement evaluates to true, all subsequent elif or else statements in that block will not be evaluated.**

</aside>

### `elif` vs `else` Clauses

- We can think of an else clause as an elif clause that has its conditional set to `True` so that it always executes when reached.
- `elif` clauses can evaluate to `True` or `False`. If `True`, the code underneath that elif statement is executed. If `False`, the compiler jumps to the next code block.
- `else` clauses are only executed after every code statement above it has evaluated to False.

## Structuring Conditional Code

Now that we have looked at the basic “block” structure of `if` statements, we can begin to think about how we can organize multiple “blocks” to give our code more complex behavior.

There are two main structures we can use to organize `if` “blocks”:

1. Chained if statements
2. Nested if statements

### Chained `if` Statements

As mentioned above, each `if` statement defines a single “block” of code that will evaluate from top to bottom until one of its conditionals produces `True` or if there are no clauses left to evaluate. 

We can refer to multiple adjacent `if` statements as a “chain”:

```python
height1 = 150.8
height2 = 160.3
fiveFeet = 152.4

if height1 > fiveFeet:
	print("person1 is ", height1 - fiveFeet, " cm above five feet tall")
if height2 > fiveFeet:
	print("person 2 is ", height2 - fiveFeet, " cm above five feet tall")
```

Adjacent `if` statements are completely independent of each other, making it possible for the body of each `if` statement to be executed separately. 

This is useful in situations where we want to make multiple related but independent comparisons. 

### Nested `If` Statements

It also possible to place an `if` statement within the body of another `if` statement. This is called “nesting” code. Nesting `if` statements allow us to make context-dependent comparisons. 

For example, rain would only be surprising if we were in the desert and not the rainforest. So, we would need to first determine our location before we made a decision about the rarity of the weather. 

```python
biome = "Desert"   # assume biome are only "Desert" and "Rainforest"
weather = "Rain"   # assume weather can only be "Rain", "Sun", or "Dry"

if biome == "Desert":                       # asks if biome is "Desert"
	if weather == "Rain":                     # asks if biome is "Desert" and the weather is "Rain"
		print ("This weather is very rare!")    # if so, prints this line
	else:                                     # if biome is "Desert" and weather is not "Rain"
		print ("Hot as usual!")                 # prints this line 
else:                                       # asks if biome is other than "Desert", in this case our only other option is "Rainforest"    
  if weather == "Rain":                     # asks if biome is "Rainforest" and weather is "Rain"
		print ("This weather is quite common!") # if so, prints this line
	else:                                     # if biome is "Rainforest" and weather is not "Rain"
		print ("The rain has stopped. Hooray!")	# prints this line
```

This code is a little complex but try to break them down into smaller pieces. Reading the comments helps as well!

Here is a piece of code with the same behavior that does not require any nested `if` statements:

```python
biome = "Desert"   # assume biome are only "Desert" and "Rainforest"
weather = "Rain"   # assume weather can only be "Rain", "Sun", or "Dry"

if biome == "Desert" and weather == "Rain":
	print ("This weather is very rare!")
elif biome == "Desert":
	print ("Hot as usual")
elif weather == "Rain":
	print ("This weather is quite common!")
else:
	print ("The rain has stopped. Hooray!")
```

Now, since we are only using one layer of `if` statements, the code is much simpler and easier to read. 🙂

# Unit Project: Does the student pass the course?

For this unit project you will be determining if a student passes a course. The course’s marking scheme is as follows:

- Midterm: 20%
- Final: 40%
- Project: 15%
- Homework assignments (2): 20% (each assignment is worth 10%)
- Participation: 5%

Here are a few requirements for your program

- A passing grade is ≥50%
- The weighted average of the final and midterm must be ≥50%
    - (0.20 * midterm_exam_grade + 0.40 * final_exam_grade) / 0.60
- You must pass the final exam
- You must pass the entire course
- If you do better on one assignment, your better assignment will be worth 15% and the worse one worth 5%
- A final message telling the student if they passed or not and the percentage they earned for the course
    - If they didn’t pass, the message should explain why
- If the student’s total grade is ≥50%, but they did not meet at least one of the requirements, their final grade will be capped at 45%
- If the student’s total grade is ≤50%, print their total grade
- The final grade, weighted MT and final grade, and final exam grade should be rounded to the nearest whole number (49.5 would be rounded to 50 —> Pass) when determining if the student passes (but not during intermediate calculations)

# Feedback Form

Please take a moment to provide your thoughts on this module.

[Module 3b (if, elif, else statements) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSe6cDe2fUepFzRyUM81xOjzqxNWRPV5WjfdOoOHp0S9TT3DCA/viewform?usp=sf_link)