# Writing and Documenting Functions

# What is a Function?

## Motivating Example - La Caf**é Ophidien**  ☕

Imagine that you run a café and you just hired your first employee to prepare bread every morning before you open. In order to train them, you take them step-by-step through your patented bread-making recipes, which takes your whole morning. 

Afterwards, you expect them to be able to bake certain amounts and quantities of bread every morning based on your instructions. To do this, they need to be able to recreate your recipes on their own. If we hadn’t trained them, we would need to walk them through the appropriate process every time you needed a new loaf of bread. So inefficient!

Thinking about this programmatically, the employee is responsible for a number of different bread-making tasks that we specified for them at the beginning of their employment. In coding, we use functions to efficiently refer to certain standard behaviours that are repeated multiple times throughout our code.

Functions eliminate a lot of unnecessary repetition and make our code **easier to read, write, and maintain.**

```python
#instructions to an untrained employee:

print("day 1")
print ("add eggs and flour to bowl")
print ("let dough rise for 30 minutes")
print ("cook for 2 hours")
print ("remove and place on cooling rack")
print ("add eggs and flour to bowl")
print ("let dough rise for 30 minutes")
print ("cook for 2 hours")
print ("remove and place on cooling rack")

print("day 2")
print ("add eggs and flour to bowl")
print ("let dough rise for 30 minutes")
print ("cook for 2 hours")
print ("remove and place on cooling rack")
print ("add eggs and flour to bowl")
print ("let dough rise for 30 minutes")
print ("cook for 2 hours")
print ("remove and place on cooling rack")

print("day 3")
#it goes on like this for years...
```

```python
#instruction to a trained employee

def make_whole_wheat(): #teaching employee to make bread first
	print ("add eggs and flour to bowl")
	print ("let dough rise for 30 minutes")
	print ("cook for 2 hours")
	print ("remove and place on cooling rack")

print("day 1")
make_whole_wheat()
make_whole_wheat()
print("day 2")
make_whole_wheat()
make_whole_wheat()
print("day 3")
make_whole_wheat()
make_whole_wheat()
#much more efficient 🥖...
```

 

## Functions allow us to:

1. **Take advantage of code that has already been written.**
    - The same function can be re-used multiple times during the execution of your code.
    - Less words are required to do the same thing.
2. **Create readable code.**
    - Functions allow anybody reading your code to easily notice patterns and repetitions.
3. **Encapsulate complex behaviour**
    - Many times, programmers will “hide” very complex programming inside a function. All anybody using it has to know is the effect that the function has on their program rather than how the code itself works.
    - Using our bakery example, imagine a customer ordering a loaf of bread. They don’t need to understand how it is baked, just how much to pay and what they will receive in return. 🍞
    

### Example

Functions can also be used in calculations. Here’s a function that adds two to a number.

```python
def add_two(num):
	return num + 2  

# to call this function, we could write add_two(3), where 3 is the argument 
# passed for the parameter num 
```

# Functions in Python

### Basic syntax

- In Python, a function is defined using `def`
- Let’s use the `add_two` function above as an example. We first write `def` to define the function we want to call `add_two` followed by **parentheses** and a **colon**
    
    ```python
    def add_two():
    ```
    

- We pass the parameter, `num` into the function inside the parentheses. The function will operate on this parameter.
    
    ```python
    def add_two(num):
    ```
    

- Then, we want to write code for what we want this function to do. In this case, we want to add 2 to the given parameter.
    
    ```python
    def add_two(num):
    	return num + 2
    ```
    

- Passing arguments into function
    - The number of arguments you pass must equal the number of parameters you defined in your function.
    
    ### Example
    
    ```python
    # this example takes 2 numbers and returns the smallest of the two
    
    def smaller_num(num1, num2):
    	if num1 < num2:
    		return num1
    	else: 
    		return num2	
    ```
    

- To call on your function, you would use the function name you just defined followed by the appropriate number of arguments
    
    ```python
    # try running the following lines of code
    
    add_two(0.1)
    
    smaller_num(-1, -0.2)
    
    smaller_num(1, 1)
    ```
    

Remember how we looked at the `random` module in Module 4? Now lets take a look at the `math` module and use their functions.

As always, we need to first `import` the library we want.

The math module has many functions that we can use to perform calculations. Some you can try are `math.sqrt()`and `math.pi`. Try playing around with other functions in the math module as well!

```python
import math

print(math.sqrt())

print(math.pi)
```

 You can find a list of math functions here:

[math - Mathematical functions - Python 3.10.4 documentation](https://docs.python.org/3/library/math.html)

### Exercises

1. Write a function called `larger_num` that returns the larger number out of two numbers or the first number if they are the same.
2. Write a function called `is_string` that produces true if the input is a `str`

# Documenting Functions 📝

Despite giving your function a descriptive name, its purpose may not be clear to another person. That’s why we want to keep a documentation of what our functions do as we write them.

### **Docstrings**

- Docstrings provide a brief summary of how your function works. They are written between triple double-quotation marks.
    - Since Docstrings are supposed to be a brief summary, we want to keep them to one line.
    
    ```python
    """This is an example of a Docstring"""
    ```
    
- Notice that the Docstring comes after defining the function and before the function body.
    
    ```python
    def smaller_num(num1, num2):
    """
    returns smaller of two given numbers, returns second number if equal
    """
    	if num1 < num2:
    		return num1
    	else: 
    		return num2
    	
    ```
    

### **help() function**

- Sometimes we know the name of a function but are unsure about how it works or how many arguments it takes in.
- We can use the `help()` function where we pass in the name of the function we want to look up in the parentheses
- Copy the updated `smaller_num()` function into your text editor then try running `help(smaller_num)`. What do you notice?

**What makes for good documentation?**

- The Docstring should be simple and concise one-line explanation of what the function does. It can span multiple lines if more details are needed.
- Make sure to document any assumptions/constraints so that the person using the function will have all the necessary information
    
    ```python
    def hello_message(name):
    """
    returns a greeting message. 
    assumes name is always greater than 0 characters (not an empty string). 
    """
    return "Hello " + name + " !" 
    ```
    

### Exercise

- Go back to two functions: `larger_num` and `is_string` and write Docstrings for them.

# Unit Project: Does the student pass? Revisited!

Remember the unit project we did in module 3b? Lets first take a look at our solution to determine whether or not the student passed.

```python
midterm_exam_grade = input("student's midterm grade: ")
final_exam_grade= input("student's final grade: ")
project_grade = input("student's project grade: " )
assignment1_grade = input("student's Assignment 1 grade: ")
assignment2_grade = input("student's Assignment 2 grade: ")
participation_grade = input("student's participation grade: ")

midterm_weight = 0.20
final_weight = 0.40
project_weight = 0.15
assignment_weight = 0.20
participation_weight = 0.05

passing_grade = 50

weighted_mt_and_final_grade = (midterm_weight * float(midterm_exam_grade) + final_weight * float(final_exam_grade)) / (midterm_weight + final_weight)

# assignment weighted grade
if float(assignment1_grade) > float(assignment2_grade):
    weighted_assignment_grade = (float(assignment1_grade) * 0.15 + float(assignment2_grade) * 0.05) 
elif float(assignment2_grade) > float(assignment1_grade):
    weighted_assignment_grade = (float(assignment2_grade) * 0.15 + float(assignment1_grade) * 0.05) 
else:
    weighted_assignment_grade = (float(assignment1_grade) * 0.10 + float(assignment2_grade) * 0.10)

# total grade
total_grade = (float(midterm_exam_grade) * midterm_weight) + (float(final_exam_grade) * final_weight) + (float(project_grade) * project_weight) + weighted_assignment_grade + (float(participation_grade) * participation_weight)

# determine if student passes
if round(weighted_mt_and_final_grade) >= passing_grade and round(float(final_exam_grade)) >= passing_grade and round(total_grade) >= passing_grade:
    print("Congratulations! You passed the course! Your final grade is " + str(round(total_grade)))
elif round(weighted_mt_and_final_grade) < passing_grade and round(float(final_exam_grade)) < passing_grade:
    print("You did not pass the weighted average of your midterm and final and did not pass the final. Your final grade is 45%")
elif round(weighted_mt_and_final_grade) < passing_grade:
    print("You did not pass the weighted average of your midterm and final. Your weighted average was " + str(round(weighted_mt_and_final_grade)) + "%" + " and your final grade is 45%")
elif round(float(final_exam_grade)) < passing_grade:
    print("You did not pass the final. Your final exam grade was " + str(round(float(final_exam_grade))) + "%" + " and your final grade is 45%")
else:
    print("You did not pass the course. Your final grade is " + str(total_grade) + "%")
```

That’s a lot of code isn’t it? Now that we know functions, let’s try and simplify this code! 

1. First, write a function called `weighted_mt_and_final_grade` that simplifies the following code. Your function should take in a midterm grade, final grade, midterm weight, and final weight.
    
    ```python
    weighted_mt_and_final_grade = (midterm_weight * float(midterm_exam_grade) + final_weight * float(final_exam_grade)) / (midterm_weight + final_weight)
    ```
    

1. Next, write a function called `weighted_assignment_grade` that simplifies the following code. The function should take in two assignment grades and the assignment weight.
    
    ```python
    # assignment weighted grade
    if float(assignment1_grade) > float(assignment2_grade):
        weighted_assignment_grade = (float(assignment1_grade) * 0.15 + float(assignment2_grade) * 0.05) 
    elif float(assignment2_grade) > float(assignment1_grade):
        weighted_assignment_grade = (float(assignment2_grade) * 0.15 + float(assignment1_grade) * 0.05) 
    else:
        weighted_assignment_grade = (float(assignment1_grade) * 0.10 + float(assignment2_grade) * 0.10)
    ```
    

1. Next, write a function called `total_grade` that simplifies the following code. Your function should take in a midterm grade, midterm weight, final grade, final weight, project grade, project weight, both assignment grades, assignment weight, participation grade, and participation weight. Make sure to call on `weighted_assignment_grade` in your new function
    
    ```python
    total_grade = (float(midterm_exam_grade) * midterm_weight) + (float(final_exam_grade) * final_weight) + (float(project_grade) * project_weight) + weighted_assignment_grade + (float(participation_grade) * participation_weight)
    ```
    

1. Finally, write a function called `does_student_pass` that simplifies the following code. Your function should call on previously defined functions. Your function should take in a midterm grade, midterm weight, final grade, final weight, project grade, project weight, both assignment grades, assignment weight, participation grade, participation weight, and minimum passing grade.
    
    ```python
    # determine if student passes
    if round(weighted_mt_and_final_grade) >= passing_grade and round(float(final_exam_grade)) >= passing_grade and round(total_grade) >= passing_grade:
        print("Congratulations! You passed the course! Your final grade is " + str(round(total_grade)))
    elif round(weighted_mt_and_final_grade) < passing_grade and round(float(final_exam_grade)) < passing_grade:
        print("You did not pass the weighted average of your midterm and final and did not pass the final. Your final grade is 45%")
    elif round(weighted_mt_and_final_grade) < passing_grade:
        print("You did not pass the weighted average of your midterm and final. Your weighted average was " + str(round(weighted_mt_and_final_grade)) + "%" + " and your final grade is 45%")
    elif round(float(final_exam_grade)) < passing_grade:
        print("You did not pass the final. Your final exam grade was " + str(round(float(final_exam_grade))) + "%" + " and your final grade is 45%")
    else:
        print("You did not pass the course. Your final grade is " + str(total_grade) + "%")
    ```
    

# Feedback Form

Please take a moment to provide your thoughts on this module.

[Module 5 (Functions) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSe_Kbzu6jktyMxRIbQhm361aFJc7TSZd19hzTnnFa-7jcR27Q/viewform?usp=sf_link)