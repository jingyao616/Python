# 5 Python Turtle

Tags: turtle

## 5.3 instances: A herd of Turtles

![5%20Python%20Turtle/Screen_Shot_2021-03-03_at_2.46.42_PM.png](5%20Python%20Turtle/Screen_Shot_2021-03-03_at_2.46.42_PM.png)

## 5.4. Object Oriented Concepts

### 5.4.3 Attributes

Each instance can have attributes, sometimes called instance variables. These are just like other variables in Python. We use assignment statements, with an =, to assign values to them. Thus, if alex and tess are variables bound to two instances of the class Turtle, we can assign values to an attribute, and we can look up those attributes. For example, the following code would print out 1100.

```python
alex.price = 500
tess.price = 600
print(alex.price + tess.price)
```

## 5.5 Repetition with a For Loop

```python
print("This will execute first")

for _ in range(3):
    print("This line will execute three times")
    print("This line will also execute three times")

print("Now we are outside of the for loop!")
```

```python
import turtle
wn = turtle.Screen()

summer=turtle.Turtle()

distance=50

summer.right(180)
for _ in range(2):
    summer.forward(distance) 
    summer.left(90)
for _ in range(2):   
    summer.forward(distance)
    summer.right(90)
summer.forward(distance)
```

![5%20Python%20Turtle/Untitled.png](5%20Python%20Turtle/Untitled.png)

A turtle’s pen can be picked up or put down. This allows us to move a turtle to a different place without drawing a line. The methods are `up` and `down`. Note that the methods `penup` and `pendown` do the same thing.

Every turtle can have its own shape. The ones available “out of the box” are `arrow`, `blank`, `circle`, `classic`, `square`, `triangle`, `turtle`.

You can speed up or slow down the turtle’s animation speed. (Animation controls how quickly the turtle turns and moves forward). Speed settings can be set between 1 (slowest) to 10 (fastest). But if you set the speed to 0, it has a special meaning — turn off animation and go as fast as possible.

```python
alex.speed(10)
```

Example:

```python
import turtle
wn = turtle.Screen()
wn.bgcolor("lightgreen")
tess = turtle.Turtle()
tess.color("blue")
tess.shape("turtle")
tess.speed(10)

dist = 5
tess.up()                     # this is new

for _ in range(30):    # start with size = 5 and grow by 2
    tess.stamp()                # leave an impression on the canvas
    tess.forward(dist)          # move tess along
    tess.right(24)              # and turn her
    dist = dist + 2
tess.color("red")      # this is real tess, not its stamp footprint

wn.exitonclick()
```

![5%20Python%20Turtle/Untitled%201.png](5%20Python%20Turtle/Untitled%201.png)

## 5.7. Summary of Turtle Methods

[Summary of Turtle Methods](5%20Python%20Turtle/Summary%20of%200e1cf.csv)

## 5.8 Incremental Programming

```python
import turtle
import math
wn = turtle.Screen()
bob = turtle.Turtle()
bob.right(90)
bob.forward(50)
for _ in range (3):
bob.left(90)
bob.forward(50)
bob.right(135)
dist = math.sqrt(50*50/2)
bob.forward(dist)
bob.right(90)
bob.forward(dist)
bob.up()
```

![5%20Python%20Turtle/Screen_Shot_2021-03-08_at_7.11.25_PM.png](5%20Python%20Turtle/Screen_Shot_2021-03-08_at_7.11.25_PM.png)