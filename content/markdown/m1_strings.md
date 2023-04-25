# 1a. Strings

<aside>
📌 Key points: data as information, the string data type, variables

</aside>

# Introducing Data Types

The information stored in a computer is collectively referred to as data. Data can be expressed in many different ways, which we refer to as “types”. Each type looks different and has different rules governing its usage.

At the most basic level, computers store data in binary form.

![Classic 1s and 0s you might have seen in movies.](images/binary.png)

Classic 1s and 0s you might have seen in movies.

However, this level of data is difficult to read and even harder to program in. Instead, programmers use more abstract forms of data represented in English when reading and writing code. These abstract instructions are then converted into binary by our coding software, which the computer can execute.

# New Data Type: `String`

### Intro - how to make a computer speak English

![YaleNews_hopper-grace.UNIVAC.102635875-CC_0.jpg](images/YaleNews_hopper-grace.UNIVAC.102635875-CC_0.jpg)

> “They told me computers could only do arithmetic…So I decided data processors ought to be able to write their programs in English, and the computers would translate them into machine code” - Grace Hopper
> 

### What is a string?

A string is a type of data that looks and reads like plain english. Each string contains a collection of characters that can be made up of letters, numbers, and/or punctuation. 

![Can you figure out how many characters are in this string?](images/Untitled.png)

Can you figure out how many characters are in this string?

### Strings in Python

In Python, and many other programming languages, strings are enclosed by either single or double quotes. The following are both valid strings.

```python
"Hello"

'Goodbye'
```

Strings can contain letters, numbers, and punctuation.

```python
"123 + 8 = 131"

'Jeff is eight (8) years old!'
```

**A few basic requirements:**

- Strings must start and end with the same “type” of quote
    
    ```python
    "Hello" # correct
    
    'Hello" # incorrect
    ```
    

- Double-quoted strings can only span one line of code.
    
    ```python
    "Hello my name is Alex" # correct 
    
    ****"Hello my
    name is alex" # incorrect 
    ```
    

- Characters inside a string cannot contain the same type of quote as the type of quote enclosing the entire string. If it does, the interpreter won’t be able to see where the string is supposed to start and where it is supposed to end.
    
    ```python
    "He said "goodbye""   # incorrect
    					  # The interpreter sees “He said “ and “” as two independent strings.
    "He said 'goodbye'"   # correct. 
    					  # We use "" to enclose the string because the string contains ''
    ```
    

**If you try to execute a program with an incorrectly formatted string, it will not run and Python will display an error message.**

```python
incorrectly_formatted_string = "hello' # our code
# running the code...
# error! we get back the message below:
  File "<stdin>", line 1
    incorrectly_formatted_string = "hello'
                                         ^
SyntaxError: EOL while scanning string literal
```

### Escape Character

So, what happens when we need to use both kinds of quotation marks in our string?

We can tell the interpreter that a quotation mark is part of a string by writing the backslash “\” before each quotation mark inside the string.

```python
"they said "hello" to james"   # incorrect
"they said \"hello\" to james" # correct
```

“\” is known as the “escape character”. The computer treats it differently than all the other characters in the string. If you want to include an escape character in a string, prefix it with another escape character.

```python
"this is an escape character: \"  # incorrect
"this is an escape character: \\" # correct
```

## Exercises:

**Converting to Strings** 

```python
# Convert the following data to string format **without deleting anything**
# The code should run once you have done this successfully

3 + 3

ILikeDoughnuts!

I am 6 feet 10 inches tall

She said "ouch!"

3*8=24

"The red dog was named "rufus" " 

"Good morning\"

'beebo went to the market and said 'bo' to the shopkeep who was named "obeeb"'
```

# Feedback Form

Please take a moment to provide your thoughts on this Module.

[Module 1a (Introduction to Strings) - Feedback form](https://forms.gle/PVF8R1WMNr1hJ8N28)
