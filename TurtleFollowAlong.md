# Python Coding Activity - Turtle Graphics
![](https://i.imgur.com/zVWdA5m.png) <- (not this kind of turtle)

In this activity, write a **Python** application and play around with some two-dimensional graphics. It will provide a glimpse into the power of programming and show how fun it can be to write code!

## Python Introduction
>Note: Skip this section if the lecture already introduced Python

<iframe width="560" height="315" src="https://www.youtube.com/embed/o9VO1g1S64U" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Python is a popular programming language used by developers all over the world. It is a _general-purpose_ language, which means that developers can use it to write **scripts** that do almost anything: create websites, analyze large data sets, control robots, design video games... the list goes on and on!

### trinket
trinket is a website that allows a developer to write and run code in a web browser. It works in any browser, on any device! This makes it easy to practice coding and show off any programs that are created. During this activity, trinket will be used to build some cool Python programs.

### First Python Program - Hello World
The first program a developer normally writes when learning a new programming language is a "Hello World" program. The goal of these programs is to display a message of "Hello World" to the user. In Python, that program is fairly simple. Follow the steps below to create a Python "Hello World" program:

1. Navigate to [bit.ly/PyTrinket](https://bit.ly/PyTrinket) to start building the program
1. Open the hamburger menu in the upper left, and select "Fullscreen" so it is easier to use
1. In the `main.py` file, type the Python command to print a message to the screen:   
    ```python
    print("Hello World")
    ```
1. Click the "Run" button to _run_ the program!

When a developer "runs" their program, they are telling the computer to execute all the code they wrote, and perform the commands they specified. **Commands** are like instructions in a recipe; they tell the computer what to do. Running the "Hello World" program in Python will print the message on the console screen.

#### Challenge: Change the Message
Update the simple "Hello World" program so that instead of saying "Hello World" it says something else!

## Python Library - Turtle Graphics Introduction

<iframe width="560" height="315" src="https://www.youtube.com/embed/ltFJoths2po" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Python has a multitude of **libraries** that allow developers to use pre-existing code to build their own applications. One such library is for [turtle graphics](https://en.wikipedia.org/wiki/Turtle_graphics), which are vector graphics that use a cursor (or "turtle") to create images on a Cartesian plane.

### First Turtle Program
Remove any code from the `main.py` file so it is totally blank. Then, on the first line of the file, add the following command:  
```python
from turtle import *
```

This command tells the computer to bring in all the code from the `turtle` library so it is usable in the program! The next step is to create the turtle. First, add a blank line underneath the first line. Then, on the third and fourth lines of the file, add the following commands:
```python
koopa = Turtle()
koopa.shape("arrow")
```

These lines create a turtle and set its shape. In this case, the turtle is `koopa`, but the turtle could have any name. Click the "Run" button to see the "turtle" appear on the page!

#### Challenge: Change the shape to "turtle"
Update the code so that instead of setting the shape to `"arrow"`, it sets the shape to `"turtle"`. Run the program again to see the shape shift!

### Adding Color
Black and white is boring, so add some color to the program! On the next line of the `main.py` file, add the following command:  
```python
koopa.color("green")
```

This command will turn the turtle green! Next, change the background color. Add a blank line, and then add the following commands:
```python
paper = koopa.getscreen()
paper.bgcolor("black")
```

These commands get the screen and set its background color to black. Run the program again to see the new colors on the page!

#### Challenge: Change the Colors
Update the code so that instead of green and black, the turtle and the background have different colors. For example, the turtle could be blue, and the background could be pink!

#### OPTIONAL: Allow the user to decide the color
Instead of using only one static color, use `input` to ask the user which color to use for the turtle. Replace the static color with the color the user enters:
```python
turtle_color = input("Enter a color for the turtle:")
koopa.color(turtle_color)
```

Comment out this code after making sure it works; otherwise it would prompt every time the program runs, which could slow things down.

## Turtle Graphics - Moving the Turtle

<iframe width="560" height="315" src="https://www.youtube.com/embed/_2v6igbsblU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

One of the most useful turtle abilities is the ability to move across the screen and draw like a pen! Create a blank line in the `main.py` file, and then add the following command on the next line:
```python
koopa.forward(50)
```

When the program runs, the turtle moves across the screen! Specifically, it moves **forward** `50` pixels in the direction it is currently facing (90 degrees).

It is also possible to turn the turtle. Add the following command on the next line:
```python
koopa.right(90)
```

This command turns the turtle `90` degrees to the **right**. Previously the direction of the turtle was 90 degrees (pointing to the right), so after turning 90 degrees to the right, the turtle should face down (180 degrees).

Run the program to see the turtle move to the right, then turn to face down!

### Drawing a Square
Add the following commands to the file, under the existing commands:
```python
koopa.forward(50)
koopa.right(90)
koopa.forward(50)
koopa.right(90)
```

Run the program to see what this code does. It should draw part of a square! How does that work? On a piece of paper, or on a whiteboard, try to draw the same square as the turtle:

1. Draw the top side from left to right
1. Turn the writing utensil and draw the right side from top to bottom
1. Turn the writing utensil and draw the bottom side from left to right

So, the turtle moves `50` pixels to the right, turns `90` degrees to face down, moves `50` pixels down, turns `90` degrees to face left, moves `50` pixels to the left, and then turns `90` degrees to face up!

#### Challenge: Finish the Square
Add code to tell the turtle to complete the square! Use the same commands, `forward` and `right`, to accomplish this.

#### OPTIONAL Challenge: Make the square bigger
Currently, the square will be `50` pixels tall and `50` pixels wide. Try to change some of the numbers so that instead, the square is `100` pixels tall and `100` pixels wide!

## Turtle Graphics - Multiple Turtles

<iframe width="560" height="315" src="https://www.youtube.com/embed/mJqI-00DVRY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

So far, the program has used one sole turtle to carry out all of the commands. However, it is also possible to create more than one turtle, and each turtle can do different things! Let's create a new turtle, and have it draw a **triangle**!

### Creating the Turtle
Creating the _new_ turtle will be very similar to creating the original turtle. The only difference will be the name of the turtle (turtles are not allowed to have the same name in Python). Copy the commands used to create the `koopa` turtle, and update them to create a turtle named `shelly`. Add the following commands at the bottom of the `main.py` file:
```python
shelly = Turtle()
shelly.shape("turtle")
shelly.color("white")
```

Run the program to see the new white turtle appear at the end!

### Drawing the Triangle
Shelly should draw three lines of equal length `100`, turning `120` degrees between each line. Add the following commands at the bottom of the `main.py` file:
```python
shelly.forward(100)
shelly.right(120)
shelly.forward(100)
shelly.right(120)
shelly.forward(100)
shelly.right(120)
```

Run the program to see Shelly draw the triangle!

#### OPTIONAL Challenge: Make the Triangle Bigger
Currently, the triangle will have sides of length `100`. Try to change some of the numbers so that instead, the triangle has sides that are `150` pixels in length!

#### OPTIONAL Challenge: Tilted triangle
The triangle is tilted so that instead of being flat on the bottom, it is flat on the top. Add an additional command _before_ Shelly starts drawing so that the triangle is rotated and becomes flat on the bottom.

>HINT: One way to do it is to use `shelly.right` and an appropriate number for the angle!

### Changing the Starting Point
In the current program, Shelly draws all over the existing shape. Instead, the program should move Shelly to another position _before_ drawing anything.

_Before_ the commands that make Shelly draw, add the following command:
```python
shelly.setpos(-100, 100)
```

Run the program to see what happens. Shelly moves, but there is another issue now!

### Removing the Extra Pen Marks
When Shelly moves to the starting point, the pen draws an extra line! Instead of doing this, the program should lift up the pen before this movement.

When working with turtles, it is possible to control whether the pen is "up" or "down" (like real life drawing). _Before_ the `shelly.setpos` command, add the following command:
```python
shelly.penup()
```

This will allow Shelly to move without drawing anything! Run the program to see what happens.

### Putting the Pen Back Down
Oh no! After lifting up the pen, Shelly no longer draws the triangle! Fix this by adding the following command _after_ the `shelly.setpos` command:
```python
shelly.pendown()
```

This way, Shelly will pick up the pen when moving to the starting point, and then put it back down before moving in the triangular fashion. Run the program again to see it work properly!

#### Challenge: New Starting Point
Instead of starting Shelly at a position of `(-100, 100)`, move the starting point to be directly above the square!

## Loops

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZrZOVXtvNAY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Loops are a very powerful programming tool. They allow developers to repeat blocks of code automatically, without having to write the commands over and over again. One of the major benefits is that if the developer needs to change something, they only have to change it in one place!

In the turtle code, there are a couple of blocks of code that could be improved with loops. Where do those repetitive commands occur?

### Drawing the Square
```python
koopa.forward(50)
koopa.right(90)
koopa.forward(50)
koopa.right(90)
koopa.forward(50)
koopa.right(90)
koopa.forward(50)
koopa.right(90)
```

The two lines, `koopa.forward` and `koopa.right`, are repeated four times here. It takes up extra space in the file, and in order to update the program, each individual line would require update. For example, to make the square bigger, each `100` would have to change. Imagine if, instead of four times, the developer had to change four _hundred_ lines! Or, if the program needed to dynamically update the number of times to repeat the code, that would be impossible without loops.

### Looping the Square
Use a `for` loop to automatically repeat the `forward` and `right` lines. Replace the square-drawing code with the following set of commands:
```python
for x in range(4):
  koopa.forward(50)
  koopa.right(90)
```

This will make the two lines repeat `4` times!

Note that the two lines are _indented_; this is how the loop knows which commands should repeat. The `for x in range()` part is the same for any number of repetitions; the `4` specifies that the loop should repeat four times.

#### Making the Square Bigger
Now, it is simpler to change the size of the square. Update the forward `50` so the turtle moves forward a different amount each time! 

#### Challenge: Looping the Triangle
Apply the same looping technique for Shelly and the triangle. Replace the repeated lines of code with a new loop! It should look a lot like the `for` loop for the square, but it should repeat a different number of times, and the angle should be different as well.

With the use of loops, the file is much shorter, and easier to maintain. Loops are one of the most important parts of programming!

## Conclusion

<iframe width="560" height="315" src="https://www.youtube.com/embed/nPGP-Fk0I1I" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## OPTIONAL: Pen Fills
There is a command that will make the pen drawing fill with the color of the turtle (like a paint bucket tool). In the `main.py` file, add the following commands around the drawing commands:
```python
koopa.begin_fill()

# ... drawing code ...

koopa.end_fill()
```

This will fill in the shape the turtle draws! It can be used with any shape by running the `begin_fill` command before drawing and the `end_fill` command after.

### More Colors
Although there are many built-in colors, sometimes it is necessary to find a very specific color. In addition to using color names (like "red", "orange", etc), turtles can take color values in RGB format! The [RGB color model](https://en.wikipedia.org/wiki/RGB_color_model) is an additive color model in which red, green and blue light are added together in various ways to reproduce a broad array of colors. Basically, it is possible to create any digital color with a combination of red, green, and blue!

Each color (R, G, and B) can take a number from 0 to 255. This represents the amount of the color in the mix. For example, a color with a Red value of 255, a Green value of 0, and a Blue value of 0 would be red.

Try to guess how the following colors would look:
- Red 255, Green 0, Blue 255
- Red 255, Green 255, Blue 0
- Red 0, Green 0, Blue 255
- Red 255, Green 255, Blue 255
- Red 0, Green 0, Blue 0
- Red 255, Green 128, Blue 0

The combinations are almost endless! Google has a [built-in color picker](https://www.google.com/search?q=color+picker) that developers and designers can utilize to find the perfect color. It displays RGB colors in this format:
```
rgb(92, 144, 66)
```

To translate that into Python code, do the following:
```python
koopa.color(92, 144, 66)
```

This will set the color of the turtle to a dark green. The RGB method allows for much more specific colors, so developers can use precisely the color they need!

## OPTIONAL: Turtle speed
There is a command that will change the speed of a turtle. In the `main.py` file, _above_ the commands that make the turtle move, add the following command:
```python
koopa.speed(8)
```

Run the program to see the speed change!

### Dynamic speed
Instead of using a static value for speed, ask the user if they want to go fast! If the user says `"yes"`, set the speed to `10`. If they say anything else, set the speed to `2`.

Use `input` to ask the user the question. Then, use an `if`/`else` to check the value the user entered.

## Final Code
```python
from turtle import *

koopa = Turtle()
koopa.shape("turtle")

go_fast = input("Do you want to go fast?")
if go_fast == "yes":
  koopa.speed(10)
else:
  koopa.speed(2)

koopa.color("green")

paper = koopa.getscreen()
paper.bgcolor("black")

koopa.begin_fill()

for x in range(4):
  koopa.forward(100)
  koopa.right(90)
  
koopa.end_fill()
  
shelly = Turtle()
shelly.shape("turtle")
shelly.color("white")

shelly.penup()
shelly.setpos(50, 100)
shelly.pendown()

shelly.right(60)
for x in range(3):
  shelly.forward(100)
  shelly.right(120)
```

## Additional Challenges
Check out the [Turtle Challenges](TurtleChallenges.md) to see some practice problems and examples!