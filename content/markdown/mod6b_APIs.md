# b. More Libraries: APIs and Console Applications

# Chapter Summary

## A Refresher on Libraries

- We learned in the previous module that libraries are abstracted code that others have created, which are meant to be reusable and have easily understandable functions
- Libraries are interesting because we don’t necessarily need to understand exactly how a function works — what is important is knowing how to use it, and its resulting output
- Libraries can be used together simultaneously with other libraries, including the standard libraries built into Python to create something entirely new
- In this module, we will be demonstrating how we can use different libraries and their pre-built functions to create a simple game, and even create our own unique twist!

### Revisiting Previous Modules

- This game tutorial assumes you have already completed the previous modules, and will require your understanding on how the following is implemented and used:
    - loop statements
    - conditional statements
    - user-defined functions
    - import statements
- You will also be learning to incorporate libraries through the use of something called an API, which will be explained in the next section

## Using Libraries: API Interfaces

- **API** stands for “Application Programming Interface” which can be thought of as a way to communicate between two applications using each other’s requests and responses
    - For example, think of a restaurant setting. The menu provides you with a list of food options, the waiter will take your request and send it to the kitchen, and the kitchen will process that request. The waiter in this case is comparable to an API.
    - An API is essentially a software intermediary that allows two different applications to communicate with each other
- APIs typically have a way to `GET` information, `DELETE`, `POST`, and `PATCH` information — these are the standard request conventions for most APIs
    - For our purposes and to simplify this module, we will only be focusing on `GET` requests, which means we will be using an API call to `GET` certain kinds of information for us to use

# Final Project: Creating a Wordle-Esque Game  💬

- For this module, we will have you follow along to create your own (terminal) console-based word guessing game, similar to the popular ‘Wordle’ phone game!

- [Wordle](https://www.nytimes.com/games/wordle/index.html) is a word-guessing game where a random 5 letter word is generated, and the user has a limited number of turns to guess the word. We recommend taking a few minutes to [play the game](https://www.nytimes.com/games/wordle/index.html) to understand how it works!
    - If a correct letter is guessed in the correct spot, it will appear green
    - If a correct letter is guessed in the wrong spot, it will appear yellow
    - If an incorrect letter is guessed, it will appear grey
    - The game ends when:
        - the user has correctly guessed the word, with all letters in the correct spots, or
        - the user has made 6 incorrect guesses

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled.png)

- Since we will be creating this on the terminal’s console, we don’t have the option to use colour at the moment to signify correct spots, so instead, we’ll be modifying our game a bit to still have a similar functionality
- Before we begin writing code, the most important part of creating software is to plan out and understand the steps we need to take to get to the end result of a working game
- We need to identify what questions to ask and what steps to take in what order — which we can do by brainstorming some questions:
    - **What are we trying to build?**
    - **What should our game do?**
    - **What are the steps to get our game to work?**

### Exercises

- Try to think about how you would answer these questions on your own if you were to build a Wordle game. Once you’ve thought about it, move on to the next step where we’ll try to brainstorm some solutions
    - Think about each step needed to build a guessing game and how we can determine if someone’s guess is correct or incorrect
    - **Thinking and planning is key to becoming an efficient programmer!**

## 1. Planning: Identifying Our Questions

- Let’s try to resolve each question in depth so we understand exactly how to tackle this game and have a good plan for where to start:
- **What are we trying to build?**
    - We will be building a Wordle-esque game where the user will be guessing a random 5 letter word and be told if they guessed a correct letter in the correct spot, a correct letter in an incorrect spot, or an incorrect letter
    - Since we cannot use the colour system that Wordle originally uses, we will need to brainstorm or search for a different method, but *this will be done as an added feature later* on — for now, it’s most important to get the base game to work
    - The game will end after 6 incorrect turns or a correct word guess
- **What should our game do?**
    - Our game will need to generate a random 5 letter word
    - Our game will need to allow the player to guess 5 letter words — no more or less
    - Our game will need to determine if the player’s answer is correct
    - Our game will need to keep track of the number of attemps, and end after 6 incorrect guesses or if a correct guess was made before the 6th turn
- **What are the steps to get our game to work?**
    - Building off of our goals for the game in the previous question, we can expand further on the steps we need to take to get our base game to work — don’t worry about fancy features for now, what’s most important is going through each step and brainstorming some code so we get a better sense of how to begin building our game.
    - *Our game will need to generate a random 5 letter word*
        - We need to figure out a way to get random 5 letter words that are real dictionary words; in this case, our best bet would most likely be to find and use a free `API`
    - *Our game will need to allow the player to guess 5 letter words — no more or less*
        - We need an `input` statement to let the player enter their guesses
        - We need to write an `if` condition to check that the player has only inputted words that are 5 letters, and reject their word otherwise
    - *Our game will need to determine if the player’s answer is correct*
        - We need to check the player’s guess each time to see if it matches the random word generated earlier, which will use an `if` condition to return `True` if correct
    - *Our game will need to keep track of the turns, and end after 6 incorrect guesses or a correct guess before the 6th turn*
        - We need a counter to keep track of how many incorrect guesses the player has made, and automatically `exit` the game when they have reached 6
        - We need to `exit` the game when the player has guessed the correct answer
        - We need to make sure the invalid guesses (not 5 letter words) are not counted towards the turn counter
- Now that we have a plan for the most basic aspects of the gameplay, we need to begin figuring out how to implement these steps; [Google](http://google.ca/) will be your best friend when you’re stuck on something or you experience a strange error!
    - If you are stuck or are experiencing any issues in the coding, please don’t hesitate to contact our TAs, we will be happy to assist you! 😊

## 2. Implementation: Putting Our Steps to Work

- Before we start, we will need to create a new project in our `IDE` to hold the code and libraries that we will be putting in, you can name it anything you’d like or use `guessingGame`

### Generating A Random 5-Letter Word

<aside>
⭐ *Our game will need to generate a random 5 letter word*

- We need to figure out a way to get random 5 letter words that are real dictionary words; in this case, our best bet would most likely be to find and use a free `API`
</aside>

- Take a look at [this free and open-source API](https://pypi.org/project/Random-Word/) that can generate a random dictionary word
    - This `API` allows single and multiple random words to be generated, along with specific `parameters` that can be added to specify word length, commonality, and other filters

### Random-Word API: Install and Import

- In order to use this API, we will need to install the library package in order to use its functions
    - Copy and paste  `sudo pip3 install random-word` in your terminal and to install the packages
    - When completed, this will create a random_word folder under your project’s libraries that will allow you to use these already defined functions
    - We will not be concerned about how the library’s functions are implemented, rather, we will be focusing on the documentation provided on the [API’s website](https://pypi.org/project/Random-Word/) to understand how to use these functions and its parameters
- In order to use the libraries’ functions in our code, we will need to create a new python file, which you can name `guessingGame.py` then copy this code as the first line:

```python
from random_word import RandomWords
```

> tells the `guessingGame.py` file that we will be using random_word functions from the library we just installed
> 
- Upon browsing the examples and documentation on the site, we can see how to use the basics of the API, and how it can return either a list of words or a single word
- In our case, we only want to return a single word, so we can start the code by writing:

```python
# creates an object instance from the library used to generate words
random_words = RandomWords() 

# calls the API to return a random word, which we print out onto the console
print(random_words.get_random_word())
```

### Exercises

- Run this code a few times and take a look at the words that get generated
    - Is there anything you notice that might be a problem for our game?
    - What should the generated words be instead in order to work for our game?

### Random-Word API: Establishing Parameters for Filters

- What you might have noticed if you ran the code a few times is that:
    - (1) The words that get generated seem a little bizarre and/or uncommon
    - (2) The words that get generated are not 5-letter words
- So, how can we fix this?
    - What we can do using the established API’s `parameters` is to set up `filters` for the words that are generated — meaning, we can set certain conditions so all words that don’t meet those conditions will not be shown
    - The website’s documentation gives us this list of `parameters` for a single word generation, along with an example code snippet to show us how to use them

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%201.png)

```python
r.get_random_word(hasDictionaryDef="true", includePartOfSpeech="noun,verb", 
minCorpusCount=1, maxCorpusCount=10, minDictionaryCount=1, 
maxDictionaryCount=10, minLength=5, maxLength=10)

# Output: pediophobia
```

- To solve our issue, we will need to use the `minLength`, `maxLength`, `hasDictionaryDef`, and `minCorpusCount` in order to resolve the issues we were having when testing the words given
    - `minLength` and `maxLength` sets the length of the words generated
        - For us, we need to set both parameters to the same number so only words with that number of letters will be shown
    - `hasDictionaryDef` will generate only real words from a dictionary
    - `minCorpusCount` will set the commonality of the words; the higher the number, the more common in everyday language the words generated will be
- Our word generator code using the parameters will be the following:

```python
from random_word import RandomWords

random_words = RandomWords()
print(random_words.get_random_word(minLength=5, maxLength=5, hasDictionaryDef="true", 
			minCorpusCount=150000))
```

- You are welcome to play around with the `minCorpusCount` - it could also be a potential feature you can add in the future to create higher ‘difficulty’ levels for this game!

### Exercises

- Once again, run this code a few times and see if you can find any issues or errors that we might need to fix up for our game to run properly
    - Is the code consistently generating words with these parameters?
    - Are the words generated appropriate for our game?

### Random-Word API: Creating Conditions

- What you might have noticed this time around is that more common 5-lettered words are being generated. Our first two problems are solved ✅
- However, there seems to be a few new problems as a result of narrowing the filter to fewer words that can be chosen:
    - (1) The words generated are sometimes “None” instead of a real word
    - (2) The words generated sometimes include punctuation marks or numbers
        - (for example: 1960s, isn’t)
- So, how can we fix these new problems?
    - What we can do with “None” issue is create an `if-condition` to check if the word being generated will be a real word, along with a `while-loop` to keep generating a new word until it is deemed valid (not “None”)
    - We’ll start with the code for the first problem and move onto the next problem after:
        
        ```python
        # first, declare a word variable that we will store the generated word in
        word = ""
        
        # next, create the while loop to keep looping if no word is stored in the variable
        while not word:
        
        	# create an if-condition to prevent "None" from being a word saved in the variable
        	if "None" in random_words.get_random_word(minLength=5, maxLength=5, 
        	hasDictionaryDef="true", minCorpusCount=150000):
        
        		# continue the loop if "None" is generated
        		continue
        
        	# if a valid word is returned, then we will store it into the word variable and 
        	# this will break out of the loop
        	else:
        		word = random_words.get_random_word(minLength=5, maxLength=5, 
        		hasDictionaryDef="true", minCorpusCount=150000)
        
        print(word)
        ```
        
- This solves our first issue ✅
- Now lets fix our code so it only displays words that use the alphabet, which can be done with the built-in python function: `isalpha()`
    - `isalpha()` is a function that returns `true` if the word contains all alphabetical letters
    - We can simply add it as an `if-condition` to the word generator call:

```python
word = ""

while not word:
	if "None" in random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000) 
	# we can chain if-conditions by continuing with connective statements like 'or', 'and'
	or not random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).isalpha():
		continue
	else:
		word = random_words.get_random_word(minLength=5, maxLength=5, 
		hasDictionaryDef="true", minCorpusCount=150000)

print(word)
```

- This solves our second problem ✅
- However, notice that our code is a bit messy and hard to read with all the different parameters and conditional statements — this is where something called `refactoring` can help!
- `Refactoring` code is essentially a way to restructure the code to make it much easier to read.
    - This can be done in multiple ways but one of the most common ways is to create a custom user-defined `function` for reusable code

### Exercises

- Take a look at the code we have so far and try to find where code is repeated
    - Are there lines that use the exact same code multiple times?
- Review how to create user-defined functions
    - Try to guess what part of our code we should put into a custom function, and try it out for yourself before moving onto the next step!

### Random-Word API: Refactoring with User-Defined Functions

- Here is our current code we’ve been working on:

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""

while not word:
	if "None" in random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000) 
	or not random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).isalpha():
		continue
	else:
		word = random_words.get_random_word(minLength=5, maxLength=5, 
		hasDictionaryDef="true", minCorpusCount=150000)

print(word)
```

- As stated previously, we will be `refactoring` certain parts using user-defined `functions` to create cleaner, more readable code
- Notice this line that gets repeated multiple times: `random_words.get_random_word(minLength=5, maxLength=5, hasDictionaryDef="true", minCorpusCount=150000)`
    - It’s extremely long, and difficult to understand, which we can fix by creating our own function, that we can name to be easy to understand
- We can create a new function using `def function_name():` and `return` for the value
- It’s important to name our functions something simple and easy to understand but still purposeful
    - When naming a function, think about if someone else were to read your code — a person should be able to understand exactly what your function does at one glance!
- In our case, we will name our function `get_wordle_word`:

```python
# this function returns a random word with our specific parameters
def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)
```

- This is how our code looks in comparison when we replace the code with our new function:

```python
# our code **before** refactoring
from random_word import RandomWords

random_words = RandomWords()

word = ""

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)

while not word:
	if "None" in random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000) 
	or not random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).isalpha():
		continue
	else:
		word = random_words.get_random_word(minLength=5, maxLength=5, 
		hasDictionaryDef="true", minCorpusCount=150000)

print(word)
```

```python
# our code **after** refactoring
from random_word import RandomWords

random_words = RandomWords()

word = ""

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)
```

- Notice how much shorter and easier to read our new code is!

### Exercises

- What might be some advantages to refactoring code using our own named functions?
- Even though there is no change in the functionality of our code, what problems do you think we might run into if we left it as it was originally, before refactoring?
    - Think about what challenges we might face if we continue to add more features or code blocks into the existing if-conditions or while-loops in the future

## 3. Inputting the Player’s Guesses

<aside>
⭐ *Our game will need to allow the player to guess 5 letter words — no more or less*

- We need an `input` statement to let the player enter their guesses
- We need to write an `if-condition` to check that the player has only inputted words that are 5 letters, and reject their word if otherwise
</aside>

- For the `input` statement, we can review back to our earlier module on how to create an input and store the value that is given, using `input()`
- We can also create an `if-condition` to check the length of the word the player has inputted and ensure it meets our 5-letter requirement

### Player Guess Input: Creating the Input Message

- Using the `input` syntax, we can create a message to prompt the player to make a guess, and store this value into a variable to use later: `guess = input("Enter your guess: ")`

### Player Guess Input: Checking Letter Count

- Since we need the word to be exactly 5-letters, we can check the length of the player’s word guess using a built-in python command: `len()`
    - `len()` returns an integer of the length of the word you use the function on
- We must create an `if-condition` using the length, and reject any inputs that don’t meet our 5-letter requirement: `if len(guess) != 5:`
- In this `if-condition`, we need to let the player know if their guess is invalid:

```python
guess = input("Enter your guess")

if len(guess) != 5:
	print("Invalid guess. Must be 5 letters")
```

### Exercises

- Try inputting different guesses for different lengths, see if it works properly!
- Try inputting non-alphabetical characters such as numbers and symbols
    - Does it accept these characters, and do you think the game should allow this?
    - What could we do to fix this problem?

### Player Guess Input: Alphabetical Letters Only

- What you might have noticed when playing around with the input is that it allows any character, even non-alphabetical to be entered
    - This is a problem since we know that the only words generated are purely alphabetical, so it would not make sense to allow non-alphabetical letters to be entered by the player
- In order to check that the guess is all alphabetical letters, we can use the same function we used previously, `isalpha()` to also reject the guess when non-alphabetical characters are entered
- Similar to the previous section, we can chain this condition, and keep the message:

```python
guess = input("Enter your guess")

if len(guess) != 5 or not guess.isalpha():
	print("Invalid guess. Must be 5 letters")
```

- Our code so far looks like this:

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)

guess = input("Enter your guess")

if len(guess) != 5 or not guess.isalpha():
	print("Invalid guess. Must be 5 letters")
```

## 4. Determining A Winner

<aside>
⭐ *Our game will need to determine if the player’s answer is correct*

- We need to check the player’s guess each time to see if it matches the random word generated earlier, which will use an `if-condition` to return `true` if correct
</aside>

### Player Wins: Checking for the Correct Answer

- We can check if the player’s guess is correct through comparison of the generated word, by seeing if it is the same word using an `if-condition`

```python
if guess == word:
	print("Congrats! You guessed the correct word.")
```

- Our current code that we have so far, when putting the last few sections together is as follows:

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)

guess = input("Enter your guess")

if len(guess) != 5 or not guess.isalpha():
	print("Invalid guess. Must be 5 letters")

if guess == word:
	print("Congrats! You guessed the correct word.")
```

- Since our code still prints out the randomly generated word, we can easily check if our winning conditions are working — your console should look something like this with the code above:

![(replace with screenshot from raspberry pi console)](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%202.png)

(replace with screenshot from raspberry pi console)

- An important aspect of programming is to work on each feature step-by-step, which allows you to make sure each item works individually. This will save you from headaches when trying to debug bigger projects

### Exercises

- Try out the guessing game we have so far — since you can see the answer, try typing it out
    - Does it work correctly when typing in uppercase?
    - Why do you think this problem occurs, and what could we do to fix it?

### Player Wins: Case Sensitivity

- When entering the same word with any uppercase letters, you might have noticed that the answer is still considered incorrect, likewise when you get a random word with an uppercase and you enter an answer that is fully lowercase
    - This is because in programming languages, uppercase and lowercase letters are encoded separately, and are not considered the same letter
- This means we need to account for and resolve two potential problems:
    - (1) When the player enters a guess with different case sensitivity than the answer
    - (2) When the word generated has uppercase values
- We can actually solve both problems using a single solution, since they are both tied to the same issue — the matter of case sensitivity mismatching in both the player guess and the word generated by the API
    - We can resolve this issue by deciding to change both the guess and generated word into the same case-type for every letter, which means the letters will always match correctly
    - In our case, we will be changing every letter to lowercase using the function:  `lower()`
- Our fixed code, when all is changed to lowercase, will be as follows:

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).lower()

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)

guess = input("Enter your guess").lower()

if len(guess) != 5 or not guess.isalpha():
	print("Invalid guess. Must be 5 letters")

if guess == word:
	print("Congrats! You guessed the correct word.")
```

### Exercises

- All letters, characters, and symbols in programming are encoded in something called `ASCII` values, which gives each character a unique code
    - You can actually use the `ord()` function to see the code that is represented by a letter
    - Try seeing what the `ASCII` values are for the same letter in uppercase and lowercase - notice how they are completely different values, which is what the `==` comparison uses to compare equality
    - For example: `print(ord('A'))`

## 5. Tracking the Number of Player’s Guesses

<aside>
⭐ *Our game will need to keep track of the turns, and end after 6 incorrect guesses or a correct guess before the 6th turn*

- We need a counter to keep track of how many incorrect guesses the player has made, and automatically `exit` the game when they have reached 6
- We need to `exit` the game when the player has guessed the correct answer
- We need to make sure the invalid guesses (not 5 letters) are not counted towards the turn counter
</aside>

- In order to keep track of the turns, we will need to implement a counter that can count each guess that the player makes, as well as keep a variable that tells us the maximum number of total guesses for each game instance (in our case is 6 guesses max. before the game ends)

### Tracking Guess Count: Current Guess Counter

- We can implement the current turn counter by creating a variable to keep track, and increase the counter by 1 for every valid guess the player makes
- We can do this by declaring an integer variable called `num_of_guesses = 0`, and increase this number everytime the user enters an input
- We also need to add a variable to state the maximum guesses the player can have each game, which we can do by declaring `MAX_NUM_OF_GUESSES = 6`
    - Notice how this variable is all in capitals, this is a common programming syntax we use to tell people that this number is a `constant`, and will not change once declared
    - Since we know we will always have 6 turns, it makes sense to use a constant variable

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""
MAX_NUM_OF_GUESSES = 6
num_of_guesses = 0

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).lower()

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)

guess = input("Enter your guess").lower()

if len(guess) != 5 or not guess.isalpha():
	print("Invalid guess. Must be 5 letters")

# this is the equivalent expression for: num_of_guesses = num_of_guesses + 1
num_of_guesses += 1
print("---> number of guesses: ", num_of_guesses)

if guess == word:
	print("Congrats! You guessed the correct word.")
```

- We can add a statement:  `print("---> number of guesses: ", num_of_guesses)` to verify that this counter is working, you can choose to leave this in or take it out afterwards

### Exercises

- What you might have noticed is that the player can only enter one guess each game
    - How can we fix this issue so the player is able to continue guessing?
- What can we add to our code to check if they have hit their limit for guesses?

### Tracking Guess Count: Allowing Multiple Guesses

- Since we want our player to continue guessing while they still have guesses left and while the answer they have guessed is incorrect, we need to add another `while-loop` to our code
- We will add this loop to allow our guess input to continue cycling, while also keeping track of the number of guesses that the player has entered

```python
# we are letting the player continue guessing if their number of guesses is below
# the maximum allowed number of guesses we have set
while num_of_guesses < MAX_NUM_OF_GUESSES:

	guess = input("Enter your guess").lower()

	if len(guess) != 5 or not guess.isalpha():
		print("Invalid guess. Must be 5 letters")
	
	num_of_guesses += 1
	print("---> number of guesses: ", num_of_guesses)
	
	if guess == word:
		print("Congrats! You guessed the correct word.")
```

- After the player has entered their 6th guess, this no longer fits the condition, resulting in the program to break out of the loop and end the game

### Exercises

- Play around with the guessing system, try inputting a correct answer and see what happens
    - What can we add to the code so the game ends when the correct answer is guessed?
- Do you see any other issues with the guess counter when we enter inputs with numbers or other characters that are not all alphabetical letters?

### Tracking Guess Count: Handling Correct and Invalid Guesses

- Our guess counter seems to work so far with allowing 6 turns each game, however, what you might notice is that the game does not end with a correct guess
- What we can do to fix this is add a `break` line after the correct guess, which as you can guess (pun intended), breaks out of the loop and ends the game

```python
	if guess == word:
		print("Congrats! You guessed the correct word.")
		break
```

- Another issue you might have seen involves invalid inputs — if the player enters a guess that contains numbers or characters or other non-alphabetical letters, we consider it a turn used, which should not be the case
- Instead, we need to have it so the guess counter only increments with valid guesses
- We can actually do this by adding an `else` condition after our existing `if-statement` that checks for invalid inputs:

```python
while num_of_guesses < MAX_NUM_OF_GUESSES:

	guess = input("Enter your guess").lower()

	if len(guess) != 5 or not guess.isalpha():
		print("Invalid guess. Must be 5 letters")
	else:
		num_of_guesses += 1
		print("---> number of guesses: ", num_of_guesses)
	
	if guess == word:
		print("Congrats! You guessed the correct word.")
		break
```

- When you have an `if` and an `else` in succession, the program can only pick one or the other
- In this case, that means when the guess gets entered, either the program decides the guess is invalid and then continues the loop, OR the program decides the guess is valid, increasing the number of guesses and then continuing the loop
- We can even make this more efficient by moving the last if-statement that checks for the correct answer, `if guess == word` — since we know the correct answer can only be matched if the player’s guess is valid, we can move it inside the else statement so the program doesn’t bother checking when the player’s guess is invalid since it is impossible that it will be correct
- Overall, our current code looks like this so far when we add this refactoring stated above:

```python
from random_word import RandomWords

random_words = RandomWords()

word = ""
MAX_NUM_OF_GUESSES = 6
num_of_guesses = 0

def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).lower()

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()

print(word)

while num_of_guesses < MAX_NUM_OF_GUESSES:

	guess = input("Enter your guess").lower()

	if len(guess) != 5 or not guess.isalpha():
		print("Invalid guess. Must be 5 letters")
	else:
		num_of_guesses += 1
		if guess == word:
			print("Congrats! You guessed the correct word.")
			break

print("End of game.")
```

- At this point, it seems we’ve got a working base game 😁 Give yourself a pat on the back, you’ve done a great job!

### Exercises

- Play around with your game for a bit, try to find any errors or issues that occur
    - Keep running the code to generate different words, are there any issues that show up in the console?
    - If there is, what do you think the problem might be, based on the error message given?

## 6. Debugging: Fixing Possible Bugs

- `Debugging` your code, also known as quality assurance (QA) is an **extremely important** part of programming - we want our code to be as predictable as possible before moving onto adding more advanced features
- We can always add code on top, but every time we do this, we make it much more difficult to fix issues that previously existed since it is harder to pinpoint where the error is coming from
    - Sometimes new code we add does not work as intended because of the existing issues
    - You can see how it might be difficult to determine if the error lies in our new code or in our existing code — that is why it is important to make sure we check for any bugs beforehand
- Were you able to find any bugs in the previous exercise? Don’t be upset if your code isn’t working as intended sometimes, it’s pretty rare to be able to get your code perfect the first time
- There are situations called `edge cases` which are unlikely circumstances that happen, that a programmer might not have anticipated — these are the cases where bugs occur most often

### Learning to Read Error Messages

- Understanding the error messages in the console is another important skill in programming — in fact, you can solve majority of problems as long as you understand certain pieces of information
- One of the most valuable pieces of information is the **line number** that is given
    - This is the line the error occurs, and your first source of inspection when dealing with bugs
- The other valuable piece is the **error name** that is given
    - Even if you don’t quite understand what the name means, it gives you a key word that you can google and find further information on
- One thing to note is that you don’t necessarily need to solve errors in order. You can try tackling easier ones first!
    - We will be going through this error message, and resolving any additional bugs that show

### Error Debugging: `AttributeError ‘NoneType’`

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%203.png)

- We will begin with this line in the error message displayed, stating an `AttributeError`
- Even if you may not know what this means, this gives you a message that you can input into google for some further clarification

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%204.png)

- According to the first result, this error is happening because we tried to call the `lower()` method on a `None` value, when the `lower()` function is only applicable to string types
- Remember how we changed the word generated to lowercase values using `lower()`?
    - Let’s take a look at `line 11` that is given in the error message

```python
# line 11: error in our return value	
return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).lower()
```

- What seems to be happening is that the random word that gets returned is sometimes `None`, which actually only gets checked later on, **after** this function has already been executed

```python
def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000).lower()

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()
```

- We can see that when `get_wordle_word()` is called, it already tries to change the randomly generated word to lowercase even before our `if-statement` checks if the word is `None`, thus causing the error
- What we can do to fix this is refactor our code so that we change the word generated into lowercase only **after** our checks have occurred
    - We can move the `lower()` function into the very last statement, where we will know for sure that the value will be a valid word:

```python
def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)~~.lower()~~
          

while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word().lower()
```

### Exercises

- After solving an error, make sure to check that your solution works by running the program many times and seeing if any additional errors come up
    - Are there any other errors that occur when you generate different words?

### Error Debugging: Logic Errors

- Although we solved the first error, it seems the **same** error occurs twice further down the code, after our `if-statement` checks should have caught it — but why is this happening?

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%205.png)

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%206.png)

- In programming, there are many types of errors that can occur, including the `AttributeError` we solved previously, and the `TypeError` stated above
    - Although the new errors above seem to be the same error as the previous one, sometimes we programmers need to take a step back and see if the code we wrote is functioning the way we intend it to — in this case, the error messages above seem to be a symptom of a different problem that we need to solve
- The most difficult (and most common) errors to solve are logic errors, meaning there doesn’t seem to be a specific error type but rather a problem with the actual steps and output of the code you wrote, which is giving unexpected behaviour
- Each logic error can be caused by something completely different, and it is up to the programmer to go through each line of code, step by step, to understand where things are going wrong
- In both these errors, the messages are related, in that they both are associated with our function call to `get_wordle_word()`; so we will begin with that function to try to debug the issue:

```python
def get_wordle_word():
	return random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)
```

- We know our function call returns either a `string` value or a `None` value; there doesn’t seem to be any issues here, so instead, let’s take a look at our statements that call the function:

```python
while not word:
	if "None" in get_wordle_word() or not get_wordle_word().isalpha():
		continue
	else:
		word = get_wordle_word()
```

- We see that the function gets called 3 different times in this code block; there are 2 possible behaviour scenarios
    - (1) The function call return value is the same in all 3 instance calls
    - (2) The function call return value is different in all 3 instance calls
- Let’s think about scenario (1):
    - If the function call for `get_wordle_word()` is the same for all 3 calls, then the value returned should be properly subjected to our first `if-statement` check, which will effectively prevent the `None` type from being assigned to our word variable, as well as prevent the second condition `isalpha()` from being executed
    - Note: `if-condition` checks in sequential order, if **one** condition in the chain returns true when there is an `or` connective, then it doesn’t bother checking the second condition since the condition has already decided the statement is true
    - If this is confusing, then consider this example: “You are tall **or** you like animals”
        - This condition will first check if you are tall, and if this is true and you are indeed tall, then it will not bother checking the second condition since it will return true regardless
        - However, if you are not tall, the statement will move onto the second condition to check if you like animals. If you like animals, then the condition returns true
        - If you are both tall and like animals, then the statement will only check the first condition, and will never check for the second condition since it only needs one part of the condition to be true
- If our program were to follow scenario (1) and have the same return value in all 3 instance calls, then the program should be running as expected, without errors
- Instead, let’s take a look at scenario (2):
    - If the function call for `get_wordle_word()` is different for all 3 calls, then the `if-statement` checks would end up being skipped, since it would be a different word for all 3 calls
    - Since this seems to be the most likely scenario, let’s explore how we can determine if this is actually the case, through the use of `print` statements
    - Let’s add a print statement in the actual function for `get_wordle_word()`:

```python
def get_wordle_word():
	debug_word = random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)
	print(debug_word)
	return debug_word
```

- We can store the generated word into a variable, then print it out and return that same word
    - What this shows us, is how many times this function gets called and what values it is returning to the function call each time

### Exercises

- What happens when you run the program with our modified function?
- What should be happening instead, if it were scenario (1)?
- What should we do to fix this problem, so it can return the same word?

## Error Debugging: Refactoring

- What you might notice is that the code ends up printing out 3 different words, like so:

![Untitled](b%20More%20Libraries%20APIs%20and%20Console%20Applications%20e30e876b76a64d1baaac016ca43d926e/Untitled%207.png)

```python
while not word:
								 # prints "score"          # prints "trick"
    if "None" in get_wordle_word() or not get_wordle_word().isalpha():
        continue
    else:
						  # prints "equal"
        word = get_wordle_word().lower()

# prints "equal" again since it is the same as the word variable
print(word)
```

- This confirms that scenario (2) is happening, where a different word gets generated each time, messing up our `if-statement` checks
    - So how do we fix this so our word generated is the same for all 3 calls?
- One solution to fix this problem is to only call the function once, store it in a variable, and use that variable for the if statements instead, like so:

```python
def get_wordle_word():
	debug_word = random_words.get_random_word(minLength=5, maxLength=5, 
	hasDictionaryDef="true", minCorpusCount=150000)
	print(debug_word)
	return debug_word

while not word:
	temp_word = get_wordle_word()
	if "None" in temp_word or not temp_word.isalpha():
		continue
	else:
		word = temp_word.lower()

print(word)
```

- Now, try running the code a few times, and you’ll see that because the function is called once, it will use the same `temp_word` to check the conditions, and only when it is valid, will it be stored into our word variable to be changed into lowercase
- Our program no longer prints out 3 different words, instead, it prints out the same word twice because of the first call:  `temp_word = get_wordle_word()` and then the `print(word)` statement
- This solves our issue, but it is not the only solution — an amazing thing about programming is there is always different ways to solve the same problem

- Consider this as an **alternative solution:**

```python
def get_wordle_word():
# while True will forever loop unless it hits a break or a return statement
	while True:
		temp_word = random_words.get_random_word(minLength=5, maxLength=5, 
		hasDictionaryDef="true", minCorpusCount=150000)
		if "None" in temp_word or not temp_word.isalpha():
			continue
		else:
		# the loop will only stop when the else statement is reached, and it will return
		# a valid word that is converted to all lowercase
			return temp_word.lower()

word = get_wordle_word()
print(word)
```

- In this solution, we refactor our `get_wordle_word()` function, so that anything related to generating the word, including the loop, will be within that specific function
- Then, we simply call `get_wordle_word()` once and store the returned value into the `word` variable

### Exercises

- Which solution do you prefer and why?
- Can you come up with a different solution that fixes our problem?

# Overall: What Did You Learn?

- Congratulations! You’ve created a working word game in Python 🥳 🥳 🥳
- To summarize our completed, working code:

```python
from random_word import RandomWords

random_words = RandomWords()

MAX_NUM_OF_GUESSES = 6
num_of_guesses = 0

def get_wordle_word():
	while True:
		temp_word = random_words.get_random_word(minLength=5, maxLength=5, 
		hasDictionaryDef="true", minCorpusCount=150000)
		if "None" in temp_word or not temp_word.isalpha():
			continue
		else:
			return temp_word.lower()

word = get_wordle_word()
print(word)

while num_of_guesses < MAX_NUM_OF_GUESSES:
	guess = input("Enter your guess").lower()
	if len(guess) != 5 or not guess.isalpha():
		print("Invalid guess. Must be 5 letters")
	else:
		num_of_guesses += 1
		if guess == word:
			print("Congrats! You guessed the correct word.")
			break

print("End of game.")
```

### Exercises:

- What did you find most interesting or most difficult when working on this module?
- What features should be added in the next part of this game?
- What new things did you learn through this module?
- What sort of things would you like to try to create next?

# Next Module Preview: Adding Correct Letter Hints

- Now, although this game is working, it’s not very playable since once you delete the `print` statement showing the word generated, it is extremely difficult to guess the word without any hints
- Not to worry, for our next module, we will continue working on our wordle game — we will be adding our first feature update to show the player hints when they guess the correct letter in the right spot, in the wrong spot, and when the letter is fully incorrect!

# Feedback Form

Please take a moment to provide your thoughts on this module

[Module 6a (libraries) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSdA9BQdqqvlrba2LiMz2b2FlCVqmKVnGPljMSjktu8eZqtSqQ/viewform?usp=sf_link)