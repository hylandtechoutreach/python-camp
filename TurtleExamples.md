## Other turtle abilities
Turtles have many additional abilities! Try to incorporate some of these new commands into the existing turtle code.

### Turtle talk
Turtles have the ability to display messages on the screen. Add the following command in the `main.py` file:
```python
koopa.write("I am a turtle")
```

Run the program to see the message appear next to the turtle! 

### Turtle pen size
Turtles can change the size of the lines they draw. In the `main.py` file, _above_ the commands that make the turtle draw, add the following command:
```python
koopa.pensize(4)
```

Run the program to see the line thickness change! Try out some other values to see how they look.

### Hiding the turtle
There is a command that will make the turtle invisible. This can be very useful when drawing. In the `main.py` file, add the following command:
```python
koopa.hideturtle()
```

Run the program to see the turtle disappear!

It is also possible to **show** the turtle after it has hidden, using the following command:
```python
koopa.showturtle()
```

### Turtle circles
There is a command that will make the turtle draw a circle. In the `main.py` file, add the following command:
```python
koopa.circle(50)
```

Run the program to see the circle! It is also possible to change the size of the circle by using numbers other than `50`.

## Examples
### Circles
```python
from turtle import *

# Create turtle and set speed
robyn = Turtle()
robyn.speed(5)

# Loop 36 times
for x in range(36):
  # Draw a circle of size 60
  robyn.circle(60)

  # turn 10 degrees to the right
  robyn.right(10)
```

### Twisty lines
```python
from turtle import *

# Create turtle, set speed, and hide
ninja = Turtle()
ninja.hideturtle()
ninja.speed(0)

# Loop 90 times
for i in range(90):
    # Head in a new direction
    ninja.setheading(i*4)

    # Draw twisty lines
    ninja.forward(50)
    ninja.right(40)
    ninja.forward(25)
    ninja.left(60)
    ninja.forward(50)
    
    # Move back to the center
    ninja.penup()
    ninja.setposition(0, 0)
    ninja.pendown()
```

### Spiderman vortex
```python
from turtle import *

# Create turtle
t = Turtle()
t.hideturtle()
t.speed(20)
t.pensize(2)

# Loop 500 times
for x in range(500):
  # If current iteration is an even number...
  if x % 2 == 0:
    # Set the color to blue
    t.color("blue")
  else:
    # Otherwise, set the color to red
    t.color("red")

  # Move forward more each time
  t.forward(x)

  # Turn
  t.right(90.2)
```

### Gradient color
```python
from turtle import *

# Create turtle
reggie = Turtle()
reggie.pensize(4)
reggie.speed(30)

# Set turtle position
reggie.penup()
reggie.setpos(-145,200)
reggie.pendown()

# Point downward
reggie.setheading(270)

# Loop 255 times
for x in range(255):
  # Set pen color based on current iteration
  reggie.color(0, x, x)

  # Move up or down the screen
  reggie.forward(400)

  # Move to the right (current x coordinate plus 1)
  reggie.setx(reggie.xcor()+1)

  # Point in the opposite direction
  reggie.setheading(reggie.heading()+180)
```

### Random dots
```python
# Import turtle AND randint
from turtle import *
from random import randint

# Create turtle, set speed, and hide
dotty = Turtle()
dotty.hideturtle()
dotty.speed(0)

# Set pen color and fill color
dotty.pencolor("black")
dotty.fillcolor("white")

for x in range(10):
  # Generate a random x location (between -175 and 175)
  x_loc = randint(-175, 175)

  # Generate a random y location (between -175 and 175)
  y_loc = randint(-175, 175)
  
  # Move to the random location 
  dotty.penup()
  dotty.setpos(x_loc, y_loc)
  dotty.pendown()
  
  # Draw dot
  dotty.begin_fill()
  dotty.circle(10)
  dotty.end_fill()
```

### Color cycle spiral
```python
# Import turtle AND math
from turtle import *
from math import *

# Create turtle
tommy = Turtle()
tommy.speed(0)
tommy.pensize(3)
tommy.hideturtle()

# Set the background color to black
tommy.getscreen().bgcolor("black")

# Move the starting position
tommy.penup()
tommy.setpos(-60,160)
tommy.pendown()

# Loop 600 times
for x in range(600):
  # Set the color so that it cycles
  tommy.color(100+((cos(pi+x/80)+1)/2)*155, 100+((sin(pi+x/80)+1)/2)*155, 100+((sin(x/80)+1)/2)*155)
  
  # Move forward less each iteration
  tommy.forward(120-(x/5))
  
  # turn 40 degrees each iteration
  tommy.right(40)
```