# Module 4

# Margaret Hamilton

- As we begin designing, developing, and testing code, we are becoming software engineers
- Software engineering is a field of engineering for designing and writing programs for computers or other electronic devices
- One of the most renowned software engineers is Margaret Hamilton, who led the NASA Software Team that took humans to the moon
- She is one of the people credited with coining the term "software engineering”
- When the Apollo missions were planned, the process of writing code began on large sheets of paper. Here is Margaret standing next to the code she wrote

![Untitled](Python%20Learning%20-%20Useful%20Links%20Resources%2000b79b353feb40c29a5ba43a7a1c5e25/Modules%208325427536c941ad87910bb453b2969b/Module%204%2005b2a8ab34324a689d1c8567f1870b4f/Untitled.png)

# Chapter Summary

- [While Loops](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [For Loops](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [Range](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [Modules and Imports](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)

# Motivating Example

- Say we want to print a simple statement like ‘Hello World’ 5 times, it’s as simple as repeating some code 5 times right?
    
    ```python
    print('Hello World')
    print('Hello World')
    print('Hello World')
    print('Hello World')
    print('Hello World')
    ```
    
- However, what if we wanted to print ‘Hello World’ 100 times? 1000 times? Or even 1 million times?
- Should we be copy and pasting the same message hundreds of times?
- There is a far simpler solution! There is a way for us to run code repeatedly in Python

# If Statements: Repeated

- Remember using `if` statements in the last unit to make code execute conditionally? Similarly, we can use another statement to make code execute repeatedly
- A `while` statement executes over and over again as long as a certain condition is True

### Syntax

- The structure of the `while` statement is as follows:
    - The while keyword
    - A boolean statement (an expression that evaluates to True or False)
    - A colon
    - Indented starting on the next line
- The structure is actually very similar to an if statement, we can look at both side to side:

```python
num = 0
if num == 0:
    print('Hello World')
```

```python
num = 0
while num == 0:
    print('Hello World')
```

- As you can see, the if statement prints the message only once, while (pun intended) the while statement continues printing `Hello World`
- The if statement only checks the condition once and executes the indented block
- The while statement will finish executing the code, check if the boolean statement is true or not, and then execute again if the statement is true

## Solving the Problem at the Beginning

- So, now that we’ve introduced the while loop, let’s try to see how we can print something a set number of times
- If the while loop will keep executing as long as the statement is true, we simply need to make the condition false after a set number of times
- Let’s say we want to print 100 times, we can count up from 0 to 100 and stop the loop once the count has reached 100

```python
count = 0
if count < 100:
	print('Hello World')
	count++
```

- At the end of each loop, we increase the `count`, so that after it’s 100th loop, increasing count to 100, the condition becomes False and the loop ends

### Exercises

- Try to print `Hello World` 1 million times
- Try to print the numbers from 0 to 100,000 each on one line
- Try to print the even numbers from 1 to 100 each on one line
- I’ve encountered an error in my code! I’m trying to print the numbers backwards from 100 down to 1, but my code is not working. Can you find the error?
    
    ```python
    count = 100
    if count < 0:
    	print(count)
    	count--
    ```
    

## Using `while` with Inputs

- We can also use the `while` loop to have the user continue to enter something if their input is invalid
- We can create some code to make sure the user’s invalid inputs don’t cause further bugs with the code
- For example, consider a program that asks you to enter your age

```python
response = input("Please enter your age: ")

if response > 18:
 print("You are an adult")
else:
	print("You are only " + age + " years old. You are not yet an adult")
```

- What if they entered a word, or a negative number?
- We should prompt the user again to make sure we get a valid answer.
- Try this exercise yourself first! Try and write a program using a while loop to make sure the user inputs a valid number before the code continues.
    - The `isdigit()` String method would be useful for this scenario. Check out some of its methods [here](https://www.programiz.com/python-programming/methods/string/isdigit):
    - Exercise Solutions
        
        ```python
        response = -1  # make a placeholder so the while loop runs
        while response.isdigit() and response > 0:
        	response = input("Please enter your age: ")
        
        if response > 18:
         print("You are an adult")
        else:
        	print("You are only " + age + " years old. You are not yet an adult")
        ```
        

### Exercises

- Get the user to enter their first name, making sure it’s properly capitalized and there are no numbers in the input. If you need help, the following link can help you find string methods.
    
    [Python String Methods](https://www.programiz.com/python-programming/methods/string)
    

# For Loops

- The `while` loop continues to execute while the condition is True, but what if we already know how many times we want the loop to go on for?
- Introducing the `for` loop!
- In code, a for statement looks something like for i in range(5): and includes the following:
    - The `for` keyword
    - A variable
    - The `in` keyword
    - A sequence to iterate through
    - A colon
    - An indented block of code
    
    ```python
    for <variable_name> in <sequence_name>: 
    	<statements to run>
    ```
    
- Say we want to print all the characters of `Hello World` one by one, we know we want to go through the entire string of Hello World
- Thus we write the code
    
    ```python
    for character in 'Hello World':
    	print(character)
    ```
    
- The variable `character` would take on the value of the characters of `Hello World`, so first the `H`, then the `e`, then the `l`, and so on, until the string is over

### Exercise

- Try to print the letters of your name one by one

# Printing Numbers: `range()`

- What if we want to print numbers instead?
- `range()` generates a range of numbers depending on the inputs
- Try and see what range does in each scenario, with one input, two inputs, and three inputs

```python
for i in range(5):
	print(i)

for i in range(5, 10):
	print(i)

for i in range(0, 10, 2):
	print(i)
```

### Review: `range()`

- `range(x)`: gives numbers from `0` up to `x`
- `range(x, y)`: gives numbers from `x` up to `y`
- `range(x, y, z)` giving numbers `x` up to `y`, incrementing by `z`

# Importing Modules

- Although Python has a lot of useful functions and methods built in, there are many others that can be used
- Python also comes with a set of modules called the standard library
- Some common modules we’ll see are the `math` module, with the mathematics-related functions, and the `random` module, with its random number-related functions
- To use the functions in a module, you must import the module with an import statement
    - `import` keyword
    - The name of the module
    
    ```python
    import random
    ```
    
- Only after you import a module can you use the functions
- The `random` module has the `random.randint()` function, let’s see how it works
- Since `randint()` is in the random module, you must first type random
- Let’s try running the code a few times and see what happens

```python
for _ in range(0, 10):
	print(random.randint(1, 10))
```

- The output should have printed 10 numbers randomly between 1 and 10
- The `random.randint()` function call evaluates to a random integer value between the two integers that you pass it

# Unit Project: Number Guessing Game

- Now let’s try to create our project: a number guessing game!
- Our program should look something like this
    
    ```
    Welcome to the number guessing game!
    Enter your first guess from 1 - 20: **10**
    Your guess is too low. Try again: **15**
    Your guess is too low. Try again: **17**
    Your guess is too high. Try again: **16**
    You got it right!
    ```
    

### Basic Structure of the Code

1. Import the random module so we can use `random.randint()` function to generate a number from 1-20
    - Answer
        
        ```python
        import random
        
        answer = random.randint(1, 20)
        ```
        
2. Let the player enter a guess and `while` their guess is not the randomly generated number, give them a hint depending on if the number is too low or too high 
    - Answer
        
        ```python
        guess = int(input('Enter your first guess from 1 - 20: '))
        while guess != answer:
        	if number < guess:
        		guess = int(input('Your guess is too low. Try again: '))
        	else:
        		guess = int(input('Your guess is too high. Try again: '))
        ```
        
3. After the while loop ends, let the user know they got the answer right! 
    - Answer
        
        ```python
        print('You got it right!')
        ```
        

### Now All Together:

```python
import random

answer = random.randint(1, 20)
guess = int(input('Enter your first guess from 1 - 20: '))

while guess != answer:
	if number < guess:
		guess = int(input('Your guess is too low. Try again: '))
	else:
		guess = int(input('Your guess is too high. Try again: '))

print('You got it right!')
```

## Additional Features to Implement for the Game:

- Give the user a minimum number of guesses, ending the game if they fail to guess the correct number within the amount of guesses given.
- Add some difficulties! Let the user choose the range of numbers they would guess from.
- In addition, let them choose how many guesses they get.
- Let the user choose if they want to play the game again after the game ends

# Chapter Summary

- [While Loops](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [For Loops](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [Range](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)
- [Modules and Imports](https://www.notion.so/Module-4-05b2a8ab34324a689d1c8567f1870b4f)

# Further Readings/Additional Content

### Python `break` and `continue` statements

[Python break and continue](https://www.programiz.com/python-programming/break-continue)

## Python Lists

[Python Lists | Python Education | Google Developers](https://developers.google.com/edu/python/lists)

### More about the `random` module

[Python Random Module](https://www.w3schools.com/python/module_random.asp)

### List Comprehensions

[Python - List Comprehension](https://www.w3schools.com/python/python_lists_comprehension.asp)

# Sample Exercises:

- The number guessing game is adapted from some of my previous lessons, taught to one of my students about 14 years old. These were his solutions to the games we came up with and can be adapted to other units

## Rock Paper Scissors

```python
import random
while 0 == 0:
  user_move=input('Enter your move (Options: rock paper or scissors): ')
  computer_move=random.choice(['rock', 'paper', 'scissors'])

  if user_move == 'rock':
    if computer_move == 'rock':
     print('computer chose rock its a tie')
    elif computer_move == 'paper':
     print('computer chose paper you lose')
    else:
     print('computer chose scissors you win')

  elif user_move == 'scissors':
    if computer_move == 'scissors':
     print('computer chose scissors its a tie')
    elif computer_move == 'rock':
     print('computer chose rock you lose')
    else:
     print('computer chose paper you win')

  if user_move == 'paper':
    if computer_move == 'paper':
     print('computer chose paper its a tie')
    elif computer_move == 'scissors':
     print('computer chose scissors you lose')
    else:
     print('computer chose rock you win')
```

## Number Guessing Game

```python
import random 

print('welcome to the number guessing game!')
print('chose your settings')

difficulty = input('choose a difficulty, hard or easy? ')
max_tries = int(input('how many tries do you want? '))

print('Let\'s start!')
print(40 * '-')

if difficulty == 'hard':
  number = random.randint(1, 1000)
  guess = int (input('enter your first guess from 1 - 1000: '))
else:
  number = random.randint(1, 100)
  guess = int (input('enter your first guess from 1 - 100: '))

guesses = []
tries = 10
print(40 * '-')
while guess != number and tries < max_tries :
  if guess in guesses:
   input('you already guessed that try again: ')
  else:
    tries += 1
    guesses.append (guess)
    if number < guess:
      guess = int (input('guess lower: '))
    else:
      guess = int (input('guess higher: '))
  print(40 * '-')

guesses.append(guess)
guesses.sort()
print('List of previous guesses:', guesses)

if guess == number and tries < max_tries:
  print('you got it right!')
else:
  print ('you ran out of guesses')
```

## Hangman

```python
import random
words = ["forest", "house", "tree", "coding"]
word = random.choice(words)
word_list = []
guess_list = []

for letter in word:
  guess_list.append("_")
  word_list.append(letter)

print(' '.join(guess_list))
wrong = 0
while guess_list != word_list and wrong < 7:
  guess=input("guess a character: ")
  if guess not in word_list:
    wrong += 1

  for i in range(len(word_list)):
    if word_list [i] == guess:
      guess_list [i] = guess

  print(' '.join(guess_list))

if wrong >= 7:
  print('you ran out of guesses')
else: 
  print('you win')
```