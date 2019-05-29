# Extras
More complex examples!

## Colorful Umbrella
```python
# Import turtle AND math
from turtle import *
from math import *

tommy = Turtle()

def draw_shape(size):
  tommy.pendown()
  tommy.setheading(0)
  
  for x in range(8):
    tommy.forward(size)
    tommy.right(45.1)
    
  tommy.penup()
  
def get_color(x):
  return [100+((cos(pi+x/10)+1)/2)*155, 100+((cos(pi+x/80)+1)/2)*155, 100+((sin(x/11)+1)/2)*155]
  
tommy.penup()
tommy.pensize(3)
tommy.speed(0)
tommy.hideturtle()

# Set the background color to black
tommy.getscreen().bgcolor("black")

# Move the starting position
tommy.setpos(-60,150)

size = 118
tommy.setheading(0)

for x in range(40):
  tommy_color = get_color(x)
  tommy.color(tommy_color[0], tommy_color[1], tommy_color[2])
  
  draw_shape(size)
  
  size = size - 3
  
  tommy.sety(tommy.ycor()-5)
  tommy.setx(tommy.xcor()+1.5)
```

## Rainbow Snake Trails
```python
# Import turtle AND math AND random
from turtle import *
from math import *
from random import *

# Create turtle
tommy = Turtle()
tommy.hideturtle()
tommy.speed(0)
screen = tommy.getscreen()

red = 255
green = 0
blue = 0

def up(x):
  return x+1

def down(x):
  return x-1
  
def nothing(x):
  return x
  
states = {
  "Yellow": [nothing, up, nothing],
  "Green": [down, nothing, nothing],
  "Cyan": [nothing, nothing, up],
  "Blue": [nothing, down, nothing],
  "Magenta": [up, nothing, nothing],
  "Red": [nothing, nothing, down]
}

colors = []

for state in states:
  for x in range(256):
    colors.append([red, green, blue])
    red = states[state][0](red)
    green = states[state][1](green)
    blue = states[state][2](blue)

tommy.penup()
tommy.setpos(0, -200)
tommy.pendown()

tommy.pensize(40)
tommy.seth(90)

def right():
  tommy.setheading(0)

def left():
  tommy.setheading(180)
  
def up():
  tommy.setheading(90)
  
def down():
  tommy.setheading(270)

screen.onkey(right, "Right")
screen.onkey(left, "Left")
screen.onkey(up, "Up")
screen.onkey(down, "Down")
screen.listen()

x = 0
while True:
  color = colors[x % len(colors)]
  tommy.color(color[0], color[1], color[2])
  tommy.forward(1.5)
  
  x += 1
```