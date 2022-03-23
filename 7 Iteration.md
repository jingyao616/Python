# 7 Iteration

# 7.1 Introduction: Iteration

A basic building block of all programs is to be able to repeat some code over and over again. Whether it is updating the bank balances of millions of customers each night, or sending email messages to thousands of people programming involves instructing the computer to do many repetitive actions. In computing, we refer to this repetitive execution as **iteration**.

<aside>
❗ iterable = sequence. sth. that you iterate through. (goes after `in`)
iterator variable = sth. that will be bound each time to one item from the iterable(sequence).

</aside>

# 7.2 The `for` LOOP

```python
for name in ["Joe", "Amy", "Brad", "Angelina", "Zuki", "Thandi", "Paris"]:
    print("Hi", name, "Please come to my party on Saturday!")
```

- **name** in this `for` statement is called the **loop variable** or, alternatively, the **iterator variable**.
- The list of names in the square brackets is the sequence over which we will iterate.
- Line 2 is the **loop body**. The loop body is always indented. The indentation determines exactly what statements are “in the loop”. The loop body is performed one time for each name in the list.
- On each *iteration* or *pass* of the loop, first a check is done to see if there are still more items to be processed. If there are none left (this is called the **terminating condition** of the loop), the loop has finished. Program execution continues at the next statement after the loop body.
- If there are items still to be processed, the loop variable is updated to refer to the next item in the list. This means, in this case, that the loop body is executed here 7 times, and each time `name` will refer to a different friend.
- At the end of each execution of the body of the loop, Python returns to the `for` statement, to see if there are more items to be handled.

<aside>
💡 The overall syntax is for `<loop_var_name>` in `<sequence>`:

</aside>

- Between the words for and in, there must be a variable name for the loop variable. You can’t put a whole expression there.
- A colon is required at the end of the line
- After the word in and before the colon is an expression that must evaluate to a sequence (e.g, a string or a list or a tuple). It could be a literal, or a variable name, or a more complex expression.

# 7.3 Flow of Execution of the for Loop

![7%20Iteration/Screen_Shot_2021-03-26_at_3.12.07_PM.png](7%20Iteration/Screen_Shot_2021-03-26_at_3.12.07_PM.png)

# 7.4. Strings and for loops

Since a string is simply a sequence of characters, the `for` loop iterates over each character automatically.

```python
for achar in "Go Spot":
    print(achar)
```

How many times is the word HELLO printed by the following statements? 

```python
s = "python rocks"
for ch in s:
   print("HELLO")

#Answer: 12 times.There are 12 characters, including the blank.
```

# 7.5. Lists and `for` loops

```python
fruits = ["apple", "orange", "banana", "cherry"]

for afruit in fruits:     # by item
    print(afruit)
```

## 7.5.1. Using the range Function to Generate a Sequence to Iterate Over

```python
print("This will execute first")

for _ in range(3):
    print("This line will execute three times")
    print("This line will also execute three times")

print("Now we are outside of the for loop!")
```

The `range` function takes an integer n as input and returns a sequence of numbers, starting at 0 and going up to but not including n. Thus, instead of `range(3)`, we could have written `[0, 1, 2]`.

## 7.5.2. Iteration Simplifies our Turtle Program

```python
import turtle            # set up alex
wn = turtle.Screen()
alex = turtle.Turtle()

for i in [0, 1, 2, 3]:      # repeat four times
    alex.forward(50)
    alex.left(90)

wn.exitonclick()
```

The values [0,1,2,3] were provided to make the loop body execute 4 times. We could have used any four values. For example, consider the following program.

```python
import turtle            # set up alex
wn = turtle.Screen()
alex = turtle.Turtle()

for aColor in ["yellow", "red", "purple", "blue"]:      # repeat four times
    alex.forward(50)
    alex.left(90)

wn.exitonclick()
```

```python
import turtle            # set up alex
wn = turtle.Screen()
alex = turtle.Turtle()

for aColor in ["yellow", "red", "purple", "blue"]:
    **alex.color(aColor)   #will change the color of the square**
    alex.forward(50)
    alex.left(90)

wn.exitonclick()
```

# 7.6. The Accumulator Pattern

**The anatomy of the accumulation pattern includes:**
• **initializing** an “accumulator” variable to an initial value (such as 0 if accumulating a sum)
• **iterating** (e.g., traversing the items in a sequence)
• **updating** the accumulator variable on each iteration (i.e., when processing each item in the sequence)

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
accum = 0
for w in nums:
    accum = accum + w
print(accum)
```

```python
for i in range(5):
    print(i)

for i in range(2, 5):
    print(i)

# Notice the casting of `range` to the `list`
print(list(range(5)))
print(list(range(2,5)))
```

<aside>
❗ One important thing to know about the range function in python3 is that if we want to use it outside of iteration, we have to cast it as a list using `list()`. Inside the textbook you’ll notice that `range` works with or without casting it as a list but it is best for you to try and get into the habit of casting it as a list.

</aside>

# Practice

Count the number of characters in string `str1`. Do not use `len()`. Save the number in variable `numbs`.

```python
str1 = "I like nonsense, it wakes up the brain cells. Fantasy is a necessary ingredient in living."
numbs = 0
for w in str1:
    numbs = numbs +1
	# numbs += 1
print(numbs)
```

# 7.7. Traversal and the for Loop: By Index

Sometimes, it is natural to think about iterating through the *positions*, or *indexes* of a sequence, rather than through the items themselves.

For example, consider the list `['apple', 'pear', 'apricot', 'cherry', 'peach']`. ‘apple’ is at position 0, ‘pear’ at position 1, and ‘peach’ at position 4.

In order to make the iteration more general, we can use the `len` function to provide the bound for `range`. This is a very common pattern for traversing any sequence by position. Make sure you understand why the range function behaves correctly when using `len` of the string as its parameter value.

```python
fruits = ['apple', 'pear', 'apricot', 'cherry', 'peach']
for n in range(len(fruits)):
    print(n, fruits[n])
```

# 7.8. Nested Iteration: Image Processing

# 7.10. 👩‍💻 Naming Variables in For Loops

Here are some tips to make your for loops more readable for yourself and anyone else who may read your programs:

1. Use singular nouns for the iterator variable, which is also called the loop variable (things like “song”, “book”, “post”, “letter”, “word”).
2. Use plural nouns for the sequence variable (things like “songs”, “books”, “posts”, “letters”, “words”).

# 7.11. The Gory Details: Iterables

Technically, the range function doesn’t actually return a list. That is, range(3) doesn’t actually create the list [0, 1, 2]. It returns an object that acts just like the list [0, 1, 2], when used in a for loop. The difference is that the numbers 0, 1, and 2 are produced as they are needed rather than all created in advance.