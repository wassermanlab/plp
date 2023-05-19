# Introduction to Variables: Number Data Types

# New Data Type: `int`s and `float`s

- In the last module we introduced `str`(strings),  which are messages surrounded by quotation marks that represent text
- What if instead of words or text, we wanted to represent a number, like 0, 100, or 3.14?
- Python stores its numbers in many different types — we'll be exploring two of those: `int` and `float`

## `int` Data Type

### What is an `int`?

- `int`s, also known as an integer, represent non-decimal numbers
- Unlike `str`, they do not need to be surrounded by quotation marks and can simply be left on their own

### Examples of the `int` Data Type

```python
3
0
-10
456123911235
```

In fact, just like with `str` we can assign data of type `int` to a variable 

```python
x = 3
y = 0
degrees_in_celsius = -10
burgers_eaten = 456123911235
```

## `float` Data Type

### What is a `float`?

- `float`s represent all numbers, including decimal numbers

### Examples of the `float` Data Type

For example, the following are data of `float` type: 

```python
x = 3.0
y = 0.00
degrees_in_celsius = -10.48129982
pizza_slices_eaten = 456123911235.2
```

### Exercise:

Which of the following are `int`s? Which are `float`s? 

```python
a = 4.5
b = 4.0
c = 4
d = "2.9"
e = -4.5
f = -4
```

# Casting

### Why use casting?

- As a motivating example, consider a program that takes in two different numbers as inputs and prints their sum
- We might write something like this:
    
    ```python
    num_1 = input("Enter one number: ")
    num_2 = input("Enter another number: ")
    print(num_1 + num_2)
    ```
    
    ### Exercise:
    
    What is the data type of `num_1` and `num_2`?
    
- So if we put in `3` and `4`, we should get back  `7` as our sum right?
    
    ```python
    >>> Enter one number: 3
    >>> Enter another number: 4
    '34'
    ```
    
    - No! What did we do wrong?
    - Remember that to add numbers, we need them to be of a number data type, either an `int` or a `float`
- We can use the function `type()` around a variable (or data) to see what type it is!
    
    ```python
    >>> type(num_1)
    <class 'str'>
    >>> type(num_2)
    <class 'str'>
    ```
    
    - So because our variables are a `string` type, we can't add the two numbers together
    - Instead, we are performing **concatenation**  —  the action of combining strings
- So how can we add the two inputs?
    - Let’s turn them into `int`s, or in other words, **cast them into `int`s.**

## Casting

- Casting is the process of transforming data from one variable type to another
- In Python, we cast to a specific type using the format `data_type(data)`

### Exercise

Try running the following code. What data type is the code going to and from?

```python
>>> int(2)   

>>> int("2") 

>>> int(2.9) 
```

- If we try casting our variables to `int` and check the type, we see
    
    ```python
    >>> type(int(num_1))
    <class 'int'>
    >>> type(int(num_2))
    <class 'int'>
    ```
    
- We can also cast individual data before being assigned to variables, so to fix our original code we can cast the input to an `int` before assigning it to a variable

```python
num_1 = int(input("Enter one number: "))
num_2 = int(input("Enter another number: "))
print(num_1 + num_2)
```

## Different forms of casting

- Based on the different data types we’ve seen so far, we can change the variable type in different ways

### `str()`

- Changing from the number to string representation is easy!
- If we pass in the number it just changes it to a string, essentially adding quotation marks to all the numbers

```python
>>> str(3)
'3'
>>> str(3.14)
'3.14'
```

### `float()`

- If you are casting from an `int` to a `float`, it simply adds a decimal point and a 0 at the end

```python
>>> float(3)
3.0
```

- If you are casting from a `str` to a `float`, it’ll get rid of the quotation marks

```python
>>> float('3')
3.0

>>> float('3.4')
3.4
```

- But be careful, if the contents contain anything that makes it not possible to be a float, Python will run into an error!

```python
>>> float('hi')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: could not convert string to float: 'hi'
```

### `int()`

- If you are casting from a `float` to an `int`, Python just cuts off everything from the decimal point onwards, meaning all the numbers would be rounded down

```python
>>> int(3.14)
3
```

- Casting from a `str` to an `int` is similar to that of a  `str` to a `float`, but your string needs to only include digits to be casted successfully

```python
>>> int('3')
3

>>> int('3.0')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '3.0'

>>> int('hi')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'hi'
```

# Project: Calculator

**Step 1:** Ask for 3 inputs and store them in 3 separate variables: the first number, the second number, and the operator 

**Step 2:** Calculate the value using `eval()`. You learn how to use it [here](https://www.programiz.com/python-programming/methods/built-in/eval)

**Step 3:** Print back their evaluated number in the form of an equation.

Examples of your calculator:

| first number | second number | operator | output |
| --- | --- | --- | --- |
| 1 | 2 | + | 1 + 2 = 3 |
| 100 |  0.5 | * | 100 * 0.5 = 50.0 |

# Feedback Form

Please take a moment to provide your thoughts on this module.

[Module 2 (Number data types) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSdQEOcTyQP3hMC_8hOWPoAxNtIZawz2Yq6i37NL-m5K30y5Lw/viewform?usp=sf_link)