# 8 Conditionals

# 8.1 Intro: What we can do with Turtles and Conditionals

## **8.1.1. Learning Goals**

- To understand boolean expressions and logical operators
- To understand conditional execution
- To be able to write a boolean function
- To know when to use binary, unary, chained and nested conditional statements

## **8.1.2. Objectives**

- To properly evaluate a (compound) boolean expression
- To use parenthesis to properly demonstrate operator precedence
- To use conditional statements to properly branch code

# 8.2 Boolean Values and Boolean Expressions

The Python type for storing true and false values is called `bool`

There are only two boolean values. They are `True` and `False`.

```python
Compair one thing on the LEFT, another thing on the RIGHT.
x == y
x != y               # x is not equal to y
x > y                # x is greater than y
x < y                # x is less than y
x >= y               # x is greater than or equal to y
x <= y               # x is less than or equal to y
```

<aside>
❗ Remember that `=` is an **assignment** operator and `==` is a **comparison** **operator**.

</aside>

# 8.3. Logical operators

There are three logical operators: `and`, `or`, and `not`.

![8%20Conditionals/Screen_Shot_2021-03-27_at_10.54.25_PM.png](8%20Conditionals/Screen_Shot_2021-03-27_at_10.54.25_PM.png)

# 8.4. The in and not in operators

The `in` operator tests if one **string** is a **substring** of another, and the `not in` operator returns the logical opposite result of `in`.:

```python
print('p' in 'apple')
print('i' in 'apple')
print('a' in 'a')
print('x' not in 'apple')
```

We can also use the `in` and `not in` operators on lists!

```python
print("a" in ["a", "b", "c", "d"])
print("a" in ["apple", "absolutely", "application", "nope"])
```

# 8.5. Precedence of Operators

Python will always evaluate the arithmetic operators first (** is highest, then multiplication/division, then addition/subtraction). Next comes the relational operators. Finally, the logical operators are done last.

![8%20Conditionals/Screen_Shot_2021-03-27_at_11.06.03_PM.png](8%20Conditionals/Screen_Shot_2021-03-27_at_11.06.03_PM.png)

<aside>
❗ **Common Mistake!**

Students often incorrectly combine the in and or operators. For example, if they want to check that the letter x is inside of either of two variables then they tend to write it the following way: `'x' in y or z`

Written this way, the code would not always do what the programmer intended. This is because the `in` operator is only on the left side of the or statement. It doesn’t get implemented on both sides of the or statement. In order to properly check that x is inside of either variable, the in operator must be used on both sides which looks like this: `'x' in y or 'x' in z`

</aside>

# 8.6. Conditional Execution: Binary Selection

**Selection statements**, sometimes also referred to as **conditional statements.**

```python
if BOOLEAN EXPRESSION:
    STATEMENTS_1        # executed if condition evaluates to True
else:
    STATEMENTS_2        # executed if condition evaluates to False
```

![8%20Conditionals/Untitled.png](8%20Conditionals/Untitled.png)

# 8.7. Omitting the else Clause: Unary Selection

when the condition evaluates to `True`, the statements are executed. Otherwise the flow of execution continues to the statement after the body of the `if`.

```python
x = -10
if x < 0:
    print("The negative number ",  x, " is not valid here.")
# there is no "else" here 

print("This is always printed")

```

# 8.8. Nested conditionals

```python
x = 10
y = 10

if x < y:
    print("x is less than y")
else:
    if x > y:
        print("x is greater than y")
    else:
        print("x and y must be equal")
```

# 8.9. Chained conditionals

`elif` is an abbreviation of `else if`.

```python
if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x and y must be equal")
```

![8%20Conditionals/Screen_Shot_2021-03-27_at_11.35.39_PM.png](8%20Conditionals/Screen_Shot_2021-03-27_at_11.35.39_PM.png)

```python
# you can use x.append(y) to add y into list x.

x = 64
output = []

if x > 63:
    output.append(True)
elif x > 55:
    output.append(False)
else:
    output.append("Neither")

if x > 67:
    output.append(True)
else:
    output.append(None)
print (output)
output = []

if x > 63:
    output.append(True)
elif x > 55:
    output.append(False)
else:
    output.append("Neither")

if x > 67:
    output.append(True)
else:
    output.append(None)
print (output)
```

# 8.10. The Accumulator Pattern with Conditionals

1. **initialize** the accumulator variable
2. **iterate** through the sequence
3. **update** accumulator variable

```python
phrase = "What a wonderful day to program"
tot = 0
for char in phrase:
    if char != " ":
        tot = tot + 1
print(tot)
```

## 8.10.1. Accumulating the Max Value

Eg. Find the max value:

```python
nums = [9, 3, 8, 11, 5, 29, 2]
best_num = 0

#You may notice that the current structure could be a problem. If the numbers were all negative what would happen to our code?
#change to: 
#**best_num = nums[0]**

for n in nums:
    if n > best_num:
        best_num = n
print(best_num)

```

# Challenge

For each word in `words`, add ‘d’ to the end of the word if the word ends in “e” to make it past tense. Otherwise, add ‘ed’ to make it past tense. Save these past tense words to a list called `past_tense`.

```python
words = ["adopt", "bake", "beam", "confide", "grill", "plant", "time", "wave", "wish"]

past_tense=[]

for i in words:
    if i[-1] == 'e':
        past_tense += [i+'d']
    else:
        past_tense += [i+'ed']
print (past_tense)
```

`rainfall_mi` is a string that contains the average number of inches of rainfall in Michigan for every month (in inches) with every month separated by a comma. Write code to compute the number of months that have more than 3 inches of rainfall. Store the result in the variable `num_rainy_months`. In other words, count the number of items with values `> 3.0`

```python
rainfall_mi = "1.65, 1.46, 2.05, 3.03, 3.35, 3.46, 2.83, 3.23, 3.5, 2.52, 2.8, 1.85"
a= rainfall_mi.split(',')
num_rainy_months = 0
for i in a:
    if float(i) > 3.0:
        num_rainy_months +=1
print (num_rainy_months )
```

Write code to count the number of strings in list `items` that have the character `w` in it. Assign that number to the variable `acc_num`.

```python
items = ["whirring", "wow!", "calendar", "wry", "glass", "", "llama","tumultuous","owing"]

acc_num=0
for i in items:
    if 'w' in i:
        acc_num+=1
```