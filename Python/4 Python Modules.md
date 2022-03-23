# 4 Python Modules

Property: https://docs.python.org/3.6/py-modindex.html

## 4.2 Modules

### 4.2.1 Our First Turtle Program

![4%20Python%20Modules/Untitled.png](4%20Python%20Modules/Untitled.png)

![4%20Python%20Modules/Untitled%201.png](4%20Python%20Modules/Untitled%201.png)

Methods(things can do):

Forward

Right

Left

Attributes:

Color

Heading

Position

Width

**Object.method()**

![4%20Python%20Modules/Screen_Shot_2021-03-03_at_2.38.36_PM.png](4%20Python%20Modules/Screen_Shot_2021-03-03_at_2.38.36_PM.png)



### 4.2.2 Syntax for Importing Modules and Functionality

1. The most common is `import morecode`. That imports everything in morecode.py. To invoke a function f1 that is defined in morecode.py, you would write `morecode.f1()`. Note that you have to explicitly mention morecode again, to specify that you want the f1 function from the morecode namespace. If you just write `f1()`, python will look for an f1 that was defined in the current file, rather than in morecode.py.
2. You can also give the imported module an alias (a different name, just for when you use it in your program). For example, after executing `import morecode as mc`, you would invoke `f1` as `mc.f1()`. You have now given the `morecode` module the alias `mc`. Programmers often do this to make code easier to type.
3. A third possibility for importing occurs when you only want to import SOME of the functionality from a module, and you want to make those objects be part of the current module’s namespace. For example, you could write `from morecode import f1`. Then you could invoke f1 without referencing morecode again: `f1()`.

## 4.3 The `random` module

```python
import random

prob = random.random()
print(prob)

diceThrow = random.randrange(1,7)       # return an int, one of 1,2,3,4,5,6
print(diceThrow)
```

Practice Questions:

1. For an instance of a class that is assigned to the variable `student`, what is the proper way to refer to the `title` attribute/instance variable?

A. student.title()  ✖️ This accesses the attribute but then tries to invoke it as a method, which will fail if title is not a method.

B. title.student()

C. title.student

D. student(title)

**E. student.title**

2. What is the name of jane’s attribute (not method) that is referred to in the following code?

```python
import turtle

jane = turtle.Turtle()
jane.forward(20)
print(jane.x)
```

The attribute is ____x______
