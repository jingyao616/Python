# 9 Transforming Sequences

# 9.2 Mutability

## 9.2.1 Lists are Mutable

Lists are **mutable**. This means we can change an item in a list by accessing it directly as part of the assignment statement.

```python
fruit = ["banana", "apple", "cherry"]

fruit[0] = "pear"
fruit[-1] = "orange"

fruit.append("lalalala")  #add an element!
print (fruit)
```

Update several elements at once:

```python
alist = ['a', 'b', 'c', 'd', 'e', 'f']
alist[1:3] = ['x', 'y']
print(alist)
```

Remove elements from a list:

```python
alist = ['a', 'b', 'c', 'd', 'e', 'f']
alist[1:3] = []
print(alist)
```

Insert elements into a list by squeezing them into an empty slice at the desired location:

```python
alist = ['a', 'd', 'f']
alist[1:1] = ['b', 'c']
print(alist)
alist[4:4] = ['e']
print(alist)
```

## 9.2.2. Strings are Immutable

Strings are **immutable**, which means you cannot change an existing string. The best you can do is create a new string that is a variation on the original.

```python
greeting = "Hello, world!"
newGreeting = 'J' + greeting[1:]
print(newGreeting)
print(greeting)          # same as it was
```

it could become difficult to keep track of them all.

```python
phrase = "many moons"
phrase_expanded = phrase + " and many stars"
phrase_larger = phrase_expanded + " litter"
phrase_complete = "M" + phrase_larger[1:] + " the night sky."
excited_phrase_complete = phrase_complete[:-1] + "!"
```

## 9.2.3. Tuples are Immutable

As with strings, if we try to use item assignment to modify one of the elements of a tuple, we get an error. In fact, that’s the key difference between lists and tuples: tuples are like immutable lists.

```python
julia[0] = 'X'  # TypeError: 'tuple' object does not support item assignment
```

# 9.3 List Element Deletion

The `del` statement removes an element from a list by using its position.

```python
a = ['one', 'two', 'three']
del a[1]
print(a)
del a[1]
print(a)

alist = ['a', 'b', 'c', 'd', 'e', 'f']
del alist[1:5]
print(alist)
```

# 9.4 Objects and References

```python
a = "banana"
b = "banana"

print(a is b)
```

We can test whether two names refer to the same object using the ***is*** operator. The is operator will return true if the two references are to the same object. In other words, the references are the same. Try our example from above.

Python assigns every object a unique id and when we ask `a is b` what python is really doing is checking to see if id(a) == id(b).

Since strings are ***immutable***, the Python interpreter often optimizes resources by making two names that refer to the same string value refer to the same object.

This is **not** the case with **lists**, which never share an id just because they have the same contents.

```python
a = [81,82,83]
b = [81,82,83]

print(a is b)

print(a == b)

print(id(a))
print(id(b))
```

# 9.5 Aliasing

Since variables refer to objects, if we assign one variable to another, both variables refer to the same object:

```python
a = [81,82,83]
b = [81,82,83]
print(a is b)

b = a
print(a == b)
print(a is b)

b[0] = 5
print(a)
```

Although this behavior can be useful, it is sometimes unexpected or undesirable. In general, it is safer to avoid aliasing when you are working with mutable objects. Of course, for immutable objects, there’s no problem. That’s why Python is free to alias strings and integers when it sees an opportunity to economize.

# 9.6 Cloning List

The easiest way to clone a list is to use the slice operator.

```python
a = [81,82,83]

b = a[:]       # make a clone using slice
print(a == b)
print(a is b)

b[0] = 5

print(a)
print(b)
```

# 9.7 Mutating Methods

Methods are either mutating or non-mutating. Mutating methods are ones that change the object after the method has been used. Non-mutating methods do not change the object after the method has been used.

## 9.7.1 List Methods

```python
mylist = []
mylist.append(5)
mylist.append(27)
mylist.append(8)
mylist.append(12)
print(mylist)

mylist.insert(1, 12)
# insert 是把value夹个到第n个位置，后面全后移
print(mylist)
print(mylist.count(12))

print(mylist.index(8))
print(mylist.index(5))
# index 从左往右数，第一次碰到x的位置

mylist.reverse()
print(mylist)

mylist.sort()
print(mylist)

mylist.remove(5)
print(mylist)

lastitem = mylist.pop()
print(lastitem)
print(mylist)

lastitem1 = mylist.pop(0)
print(lastitem1)
print(mylist)
```

The following table provides a summary of the list methods shown above. The column labeled `result` gives an explanation as to what the return value is as it relates to the new value of the list. The word **mutator** means that the list is changed by the method but nothing is returned (actually `None` is returned). A **hybrid** method is one that not only changes the list but also returns a value as its result. Finally, if the result is simply a return, then the list is unchanged by the method.

![9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_10.23.05_PM.png](9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_10.23.05_PM.png)

<aside>
❗ It is important to remember that methods like `append`, `sort`, and `reverse` all return `None`. They change the list; they don’t produce a new list. So, while we did reassignment to increment a number, as in `x = x + 1`, doing the analogous thing with these operations will lose the entire list contents (see line 11below).

</aside>

```python
mylist = []
mylist.append(5)
mylist.append(27)
mylist.append(3)
mylist.append(12)
print(mylist)

mylist.sort()
print(mylist)

mylist = mylist.sort()   #probably an error
print(mylist)
```

# 9.8. Append versus Concatenate

It is  important to realize that with **append**, the original list is simply modified. On the other hand, with **concatenation**, an entirely new list is created.

![9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_10.42.52_PM.png](9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_10.42.52_PM.png)

```python
origlist = [45,32,88]
print("origlist:", origlist)
print("the identifier:", id(origlist))             #id of the list before changes
newlist = origlist + ['cat']
print("newlist:", newlist)
print("the identifier:", id(newlist))              #id of the list after concatentation
origlist.append('cat')
print("origlist:", origlist)
print("the identifier:", id(origlist))             #id of the list after append is used
```

<aside>
❗ We have previously described x += 1 as a shorthand for x = x + 1. With lists, += is actually a little different. In particular, origlist += [“cat”] appends “cat” to the end of the original list object. If there is another alias for `origlist, this can make a difference. SO, DON'T suggest to use += in list. See example below:

</aside>

```python
origlist = [45,32,88]
aliaslist = origlist
origlist += ["cat"]   # works like append in this case
origlist = origlist + ["dog"]
print (origlist)
print (aliaslist)
```

# 9.9. Non-mutating Methods on Strings

Remember Strings are non-mutable.

![9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_11.07.41_PM.png](9%20Transforming%20Sequences/Screen_Shot_2021-04-17_at_11.07.41_PM.png)

## 9.9.1. String Format Method

```python
name = "Rodney Dangerfield"
score = -1  # No respect!
print("Hello " + name + ". Your score is " + str(score))
```

```python
scores = [("Rodney Dangerfield", -1), ("Marlon Brando", 1), ("You", 100)]
for person in scores:
    name = person[0]
    score = person[1]
    print("Hello " + name + ". Your score is " + str(score))
```

In this section, you will learn to write that in a more readable way:

```python
scores = [("Rodney Dangerfield", -1), ("Marlon Brando", 1), ("You", 100)]
for person in scores:
    name = person[0]
    score = person[1]
    print("Hello {}. Your score is {}.".format(name, score))
```

<aside>
💡 The string method `format`, makes substitutions into places in a string enclosed in braces.

</aside>

The string for the `format` method has a special form, with braces embedded. Such a string is called a *format string*. Places where braces are embedded are replaced by the value of an expression taken from the parameter list for the `format` method. 

```python
origPrice = float(input('Enter the original price: $'))
discount = float(input('Enter discount percentage: '))
newPrice = (1 - discount/100)*origPrice
calculation = '${:.2f} discounted by {}% is ${:.2f}.'.format(origPrice, discount, newPrice)
print(calculation)
```

It is important to pass arguments to the `format` method in the correct order, because they are matched *positionally* into the `{}` places for interpolation where there is more than one.

```python
name = "Sally"
greeting = "Nice to meet you"
s = "Hello, {}. {}."

print(s.format(name,greeting)) # will print Hello, Sally. Nice to meet you.

print(s.format(greeting,name)) # will print Hello, Nice to meet you. Sally.

print(s.format(name)) # 2 {}s, only one interpolation item! Not ideal.
```

# 9.10. The Accumulator Pattern with Lists

```python
nums = [3, 5, 8]
accum = []
for w in nums:
    x = w**2
    accum.append(x)
print(accum)
```

Here, we **initialize** the accumulator variable to be an empty list, on line 2.

We **iterate** through the sequence (line 3). On each iteration we transform the item by squaring it (line 4).

The **update** step appends the new item to the list which is stored in the accumulator variable (line 5). The update happens using the .append(), which mutates the list rather than using a reassignment. Instead, we could have written `accum = accum + [x]`, or `accum += [x]`. In either case, we’d need to concatenate a list containing x, not just x itself.

# 9.11. The Accumulator Pattern with Strings

Strings are immutable, so we need to re-assign it's value to it every time we accumulated.

```python
s = "cat"
ac = ""
for c in s:
    ac = ac + c + "-" + c + "-"

print(ac)
```

![9%20Transforming%20Sequences/Screen_Shot_2021-04-18_at_12.45.13_AM.png](9%20Transforming%20Sequences/Screen_Shot_2021-04-18_at_12.45.13_AM.png)

# 9.12. 👩‍💻 Accumulator Pattern Strategies

## 9.12.1. When to Use it

![9%20Transforming%20Sequences/Screen_Shot_2021-04-18_at_1.05.28_AM.png](9%20Transforming%20Sequences/Screen_Shot_2021-04-18_at_1.05.28_AM.png)

## 9.12.3. Choosing Good Accumulator and Iterator Variable Names

A good name can help remind you of what the value is assigned to the variable as well as what you should have by the end of your code.

For the **accumulator variable**, one thing that can help is to make the variable name end with “so_far”. The prefix can be something that helps remind you of what you’re supposed to end up with. For example: count_so_far, total_so_far, or cubes_so_far.

the **iterator** variable should be a singular noun

# 9.13. 👩‍💻 Don’t Mutate A List That You Are Iterating Through

You may be tempted now to iterate through a list and accumulate some data into it or delete data from it, however that often becomes very confusing. In the following code we will filter out all words that begin with P, B, or T.

```python
colors = ["Red", "Orange", "Yellow", "Green", "Blue", "Indigo", "Violet", "Purple", "Pink", "Brown", "Teal", "Turquois", "Peach", "Beige"]

for position in range(len(colors)):
    color = colors[position]
    print(color)
    if color[0] in ["P", "B", "T"]:
        del colors[position]

print(colors)

# ERROR 
```

In the code above, we iterated through `range(len(colors))` because it made it easier to locate the position of the item in the list and delete it. However, we run into a problem because as we delete content from the list, the list becomes shorter. Not only do we have an issue indexing on line 4 after a certain point, but we also skip over some strings because they’ve been moved around.  Note that each time we iterate through the list python does not reevaluate the iterator variable.

<aside>
❗ We recommend not iterating over a list that you will be mutating within the for loop.

</aside>