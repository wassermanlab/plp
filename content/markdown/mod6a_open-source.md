# a. Introduction to Open-Source Libraries

# Chapter Summary

- [“**Don't Reinvent The Wheel**”](https://www.notion.so/a-Introduction-to-Open-Source-Libraries-91a4097328794f818ca0da89086e2bb1)
- [Using Libraries: Import Statements](https://www.notion.so/a-Introduction-to-Open-Source-Libraries-91a4097328794f818ca0da89086e2bb1)
- [Example: Creating A Basic Bar Graph](https://www.notion.so/a-Introduction-to-Open-Source-Libraries-91a4097328794f818ca0da89086e2bb1)
- [Example: Creating A Basic Line Plot](https://www.notion.so/a-Introduction-to-Open-Source-Libraries-91a4097328794f818ca0da89086e2bb1)

# “**Don't Reinvent The Wheel**”

- A popular saying amongst programmers is not to reinvent the wheel, referring to the idea that we shouldn’t duplicate methods that already exist
- In programming, we often reuse code that others have already created, which is offered for free and publicly distributed as “open-source” resources
- We can refer to these code repositories as “libraries”
- You may have heard of other programming languages, such as JavaScript, C, and C++. However, one of Python’s greatest strengths is that it has large standard library that comes with built-in functions you can use in your own code!

# Using Libraries: Import Statements

- In real world terms, a library is a collection of books that are stored and accessed at your own convenience
- Similarly, in programming, a library is a collection of precompiled code that can be used in programs for specific operations
- In order to use these libraries, we need to:
    1.  `import` the library into the code, so your file understands what to use 
        - `import` tells the user what the custom statements used mean, otherwise, your computer will not know what certain keywords are referring to because it’s not built into Python
    2.  `install` the library onto your computer
- For this module, we will be focusing solely on MatPlotLib, but there are thousands of open-source libraries out there, which is what makes Python such a popular and useful language!

### Why MatPlotLib?

- MatPlotLib is one of the most popular 2D data visualization libraries in Python
- It is a tool used to graph data visually, and is actually built on other popular libraries, such as NumPy and SciPi. Think of these different libraries like a tree hierarchy, where the roots (ie. other libraries) are the foundation for some of MatPlotLib’s functions
- Plots, bar charts, histograms, pie charts, and scatterplots are some of the graphs you can make using MatPlotLib
    
    ![Untitled](a%20Introduction%20to%20Open-Source%20Libraries%2091a4097328794f818ca0da89086e2bb1/Untitled.png)
    
- Check out the different plots you can make [here](https://matplotlib.org/stable/plot_types/index.html)!

# Example 1: Creating A Basic Bar Graph 📊

- Bar graphs help to visualize trends and patterns in categorical data
    - Some examples of bar graphs might be:
        - The number of red, blue, and yellow marbles in a jar
        - The favorite ice cream flavour of students in a class of 30
        - The number of male and female graduating students for each bachelor’s degree
- Let’s begin creating our own bar graph using the example code below!

### Example

- Usually we would have to install the Matplotlib library, but your Raspberry Pi comes with it already installed!
- Copy this code into your IDE and run the code to see what happens

```python
# importing matplotlib module 
from matplotlib import pyplot as plt
  
# x-axis values
x = [5, 2, 9, 4, 7]
  
# y-axis values
y = [10, 5, 8, 4, 2]
  
# function to plot the bar
plt.bar(x,y)
  
# function to show the plot
plt.show()
```

- You should see something similar to this
    
    ![Bar graph corresponding to code above](a%20Introduction%20to%20Open-Source%20Libraries%2091a4097328794f818ca0da89086e2bb1/Untitled%201.png)
    
    Bar graph corresponding to code above
    

- If nothing appears, it may be that Matplotlib wasn’t installed. If your code runs, you can skip this part. If your code didn’t run, expand the toggle icon and follow the installation process below.
    
    <aside>
    1️⃣ The structure of the `import` declaration is as follows:
    
    - `from matplotlib import pyplot as plt`
    - `import matplotlib.pyplot as plt`
    </aside>
    
    <aside>
    2️⃣ Either of the above work to import MatPlotLib, and **you only need to declare one** of those lines **at the top of your code file**
    
    - `plt` is the “parent” class that runs the functions you call, so you must also install it into your own computer
    - The easiest way is to use the built-in terminal available on your IDE
        
        ![Untitled](a%20Introduction%20to%20Open-Source%20Libraries%2091a4097328794f818ca0da89086e2bb1/Untitled%202.png)
        
    </aside>
    
    <aside>
    3️⃣ Copy and paste the following into terminal: `python -mpip install -U matplotlib`
    
    </aside>
    
    <aside>
    4️⃣ Watch as it installs what is called the library dependencies
    
    </aside>
    
    <aside>
    5️⃣ This installs the actual code instructions you need for the file to understand what to do when it is declared in your code
    
    </aside>
    
- Notice how `plt` is called to create the bar graph using `plt.bar(x, y)` and displays it onto your screen using `plt.show()`
- Explain to your partner how Python knows which x-axis value corresponds to which y-axis value!

### Exercise

- Notice how `x` and `y` represent the values of the bars, try changing the values and see what happens when you change `x`, `y`, or both

## Adding Titles and Axes Labels

- Graphs come with a title and axes labels so that we know what sort of data the graph is trying to summarize

### Exercise

- You will need the following page to do the next few exercises.
    
    [Matplotlib Labels and Title](https://www.w3schools.com/python/matplotlib_labels.asp)
    
- Create your own bar graph summarizing whatever data you like. You can use the given examples above for inspiration if you have trouble coming up with your own
- Add a title, x-axis label, and y-axis label to your graphs
- Try customizing the font, colour, and size of your text so that the graph clearly displays the data and is visually appealing. You can also try changing the location at which the labels are positioned.

# Example 2: Creating A Basic Line Plot 📈

- Similar to the bar graph, we will be creating our own line plot using the example code below

### Example

- Once you have run the library installation, you do not need to import it again unless you decide to create a file in a different folder (we will include it here for now)
- Run this code and see what is produced!
    
    ```python
    # importing matplotlib module 
    from matplotlib import pyplot as plt
      
    # x-axis values
    x = [5, 2, 9, 4, 7]
      
    # Y-axis values
    y = [10, 5, 8, 4, 2]
      
    # Function to plot
    plt.plot(x,y)
      
    # function to show the plot
    plt.show()
    ```
    
    - You should see something similar to this
        
        ![Line plot corresponding to code above ](a%20Introduction%20to%20Open-Source%20Libraries%2091a4097328794f818ca0da89086e2bb1/Untitled%203.png)
        
        Line plot corresponding to code above 
        

- Notice how `plt` is called to create the line plot using `plt.plot(x, y)` and displays it onto your screen using `plt.show()`, just like the bar graph previously

### Exercises

- Try changing the values of `x` and `y` to see what happens
- Notice how the code is almost identical to the previous bar graph, but looks completely different! Can you figure out what the small difference is between the code of the bar graph vs the line plot?
- Give the x and y axes appropriate labels and title your line plot accordingly

# Abstraction: A Powerful Tool in Software Design

- Abstraction in Python is when unecessary information or parts of code is hidden from the user, essentially running in the background
- We don’t always need to know what each line of code does in order to use an already existing function, especially when the function is complex and long
- Libraries are examples of function abstraction. We know **what the code does and how to use it**, but we **don’t necessarily need to understand how it works** to use it
- This makes things more efficient and less complex

# Unit Project — Do Sharks Eat Ice Cream?  🦈

After the fifth recorded shark attack on Beach Newport, you were contacted by John, a lifeguard that works at the beach, to conduct an investigation into the incident. Once there, you noticed the sheer amount of ice cream stalls located around the perimeter of the beach 🏖️. 

John comes up to you and says: “It’s crazy. They were all just eating ice cream and having fun before they got attacked!” Thinking to yourself that this is a most peculiar coincidence, you decide to collect data on the number of ice cream sales and the number of shark attacks that occurred each month throughout the year. 

What if, you thought, sharks were being baited by the beachgoers’ irresistable ice cream treats 🍦? After a year of fruitful investigation, this is the data that you’ve gathered:

| Month | # of ice cream sales | # of shark attacks |
| --- | --- | --- |
| January | 8 | 0 |
| February | 10 | 0 |
| March | 11 | 1 |
| April | 14 | 1 |
| May | 20 | 2 |
| June | 50 | 4 |
| July | 90 | 7 |
| August | 120 | 9 |
| September | 100 | 5 |
| October | 30 | 3 |
| November | 25 | 1 |
| December | 5 | 0 |

Using your newly gained knowledge of MatPlotLib, you are going to find out whether there is any basis to the correlation that you’ve made between ice cream and sharks. Do sharks just enjoy ice cream 🤔? 

Here are some things to consider:

- What sort of plot/graph would represent this data most effectively?
- Note how there are now two variables we need to plot — the number of ice cream sold and the number of shark attacks
    - How can we distinguish between the two sets of data clearly (think of colours, markers, legends, text size, etc.)?
    

You print out your graph and eagerly rush down to Beach Newport to inform John of your conclusion. 

Based on your graph, what news do you bring to him? Choose one of the following.

1. Sharks eat ice cream 😎
2. Sharks are lactose intolerant 😔 

This is a clear example of how correlation does not equal causation. Despite the strong correlation between the number of ice cream sold and shark attacks each month, they are not actually causing one another. A more plausible reason is that during the warmer months, more people are likely to visit the beach and buy ice cream, thus increasing the chances of a shark attack occuring. The confounding variable in this scenario is the climate. 

Although graphs appear objective at first, it is important to keep in mind that they can be manipulated and may not represent the full picture!

# Additional Exploration (optional but highly recommended!)

- These projects use the Python Turtle module. You’ll be able to draw shapes, patterns, and spirals of different colours and sizes.
    
    [Projects | Computer coding for kids and teens | Raspberry Pi](https://projects.raspberrypi.org/en/projects/turtley-amazing/3)
    
    Draw patterns and spirals
    
    [Projects | Computer coding for kids and teens | Raspberry Pi](https://projects.raspberrypi.org/en/projects/turtle-snowflakes/5)
    
    Learn to draw snowflakes
    

- This website goes into detail about the Turtle module and is a great resource if you’re looking for additional methods (like animation and colour control)
    
    [turtle - Turtle graphics - Python 3.10.5 documentation](https://docs.python.org/3/library/turtle.html)
    

# Feedback Form

Please take a moment to provide your thoughts on this module

[Module 6a (libraries) - Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSeQqfdUMYsraNknDY8ISkCtIVXBoU_rZ-Bg1L-mGRLiil5oDQ/viewform?usp=sf_link)

# Further Readings / Additional Content

Check out this website for other fun and wacky correlations!

[15 Insane Things That Correlate With Each Other](https://www.tylervigen.com/spurious-correlations)

Scroll through the left side legend of this website to find out more ways in which you can customize your graphs/plots! 

[Matplotlib Tutorial](https://www.w3schools.com/python/matplotlib_intro.asp)

[Understanding Abstraction in Python - AskPython](https://www.askpython.com/python/oops/abstraction-in-python)

Skim these websites if you like! (no need to go in detail)

[The Python Standard Library - Python 3.10.5 documentation](https://docs.python.org/3/library/)

Object Oriented Programming (OOP)

[Python Object Oriented Programming](https://www.programiz.com/python-programming/object-oriented-programming)