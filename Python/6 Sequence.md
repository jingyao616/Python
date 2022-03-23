# 6 Sequences

# 6.1 introduction: Sequences

# 6.2 Strings and Lists

## 6.2.1 Strings

A string that contains no characters, often referred to as the empty string, is still considered to be a string. It is simply a sequence of zero characters and is represented by ‘’ or “” (two single or two double quotes with nothing in between).

## 6.2.2 Lists

A list is a sequential collection of Python data values, where each value is identified by an index. The values that make up a list are called its elements.

```python
my_list = []
my_list.append("nut")
my_tools = ["screwdriver","wrech"]
my_supplies = my_list + my_tools
my_supplies[2] = "screw"

len(my_supplies) 

my_supplies.count("screw")
```

## 6.2.3 Tuples

A tuple, like a list, is a sequence of items of any type. The printed representation of a tuple is a comma-separated sequence of values, enclosed in parentheses. In other words, the representation is just like lists, except with parentheses () instead of square brackets [].

```python
julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")
```

<aside>
💡 The key difference between lists and tuples is that a tuple is immutable, meaning that its contents can’t be changed after the tuple is created.

</aside>

To create a tuple with a single element (but you’re probably not likely to do that too often), we have to include the final comma, because without the final comma, Python treats the (5) below as an integer in parentheses:

```python
t = (5,)
print(type(t))

x = (5)
print(type(x))
```

# 6.3 Index Operator: Working with the Characters of a String

![6%20Sequence/Untitled.png](6%20Sequence/Untitled.png)

```python
school = "Luther College"
m = school[2]
print(m)

lastchar = school[-1]
print(lastchar)
```

# 6.4. Disabmiguating []: creation vs indexing

Square brackets `[]` are used in quite a few ways in python. When you’re first learning how to use them it may be confusing, but with practice and repetition they’ll be easy to incorporate!

You have currently encountered two instances where we have used square brakets. The first is creating lists and the second is indexing.

<aside>
💡 However, indexing requires referencing an already created list while simply creating a list does not.

</aside>

```python
lst = [0]
n_lst = lst[0]

print(type(lst))
print(type(n_lst))

print(lst)
print(n_lst)
```

# 6.5. Length

The `len` function, when applied to a string, returns the number of characters in a string.

```python
fruit = "Banana"
print(len(fruit))
```

```python
alist =  ["hello", 2.0, 5]
print(len(alist))
print(len(alist[0]))
```

# 6.6 The Slice Operator

The `slice` operator `[n:m]` returns the part of the string starting with the character at index n and go up to but not including the character at index m.

```python
singers = "Peter, Paul, and Mary"
print(singers[0:5])
print(singers[7:11])
print(singers[17:21])
```

## 6.6.1. List Slices

```python
a_list = ['a', 'b', 'c', 'd', 'e', 'f']
print(a_list[1:3])
print(a_list[:4])
print(a_list[3:])
print(a_list[:])
```

## 6.6.2. Tuple Slices

We can’t modify the elements of a tuple, but we can make a variable reference a new tuple holding different information.

```python
julia = ("Julia", "Roberts", 1967, "Duplicity", 2009, "Actress", "Atlanta, Georgia")
print(julia[2])
print(julia[2:6])

print(len(julia))

a = julia[:3] + ("Eat Pray Love", 2010) + julia[5:]
print(a)
print(type(a))
```

# 6.7. Concatenation and Repetition

Again, as with strings, the `+` operator concatenates lists. Similarly, the `*` operator repeats the items in a list a given number of times.

<aside>
💡 It is important to see that these operators create new lists from the elements of the operand lists. If you concatenate a list with 2 items and a list with 4 items, you will get a new list with 6 items

</aside>

<aside>
❗ Beware when adding different types together! Python doesn’t understand how to concatenate different types together. Thus, if we try to add a string to a list with `['first'] + "second"` then the interpreter will return an error. To do this you’ll need to make the two objects the same type. In this case, it means putting the string into its own list and then adding the two together like so: `['first'] + ["second"]`. This process will look different for other types though. Remember that there are functions to convert types!

</aside>

# 6.8 Count and Index

## 6.8.1. Count

It requires that you provide one argument, which is what you would like to count.

```python
z = ['atoms', 4, 'neutron', 6, 'proton', 4, 'electron', 4, 'electron', 'atoms']
print(z.count("4"))
print(z.count(4))
print(z.count("a"))
print(z.count("electron"))
```

## 6.8.2. Index

For both strings and lists, `index` returns the leftmost index where the argument is found. If it is unable to find the argument in the string or list, then an error will occur.

```python
music = "Pull out your music and dancing can begin"
bio = ["Metatarsal", "Metatarsal", "Fibula", [], "Tibia", "Tibia", 43, "Femur", "Occipital", "Metatarsal"]

print(music.index("m"))
print(music.index("your"))

print(bio.index("Metatarsal"))
	#Even though “Metatarsal” occurs many times in bio, the method will only return the location of one of them.
print(bio.index([]))
print(bio.index(43))
```

# 6.9 Splitting and Joining Strings

Two of the most useful methods on strings involve lists of strings. The `split` method breaks a string into a list of words. 

By default, any number of whitespace characters is considered a word boundary.

![6%20Sequence/Untitled%201.png](6%20Sequence/Untitled%201.png)

```python
song = "The rain in Spain..."
wds = song.split('ai')
print(wds)
```

<aside>
❗ The `.split()` method returns a list.

</aside>

---

![6%20Sequence/Screen_Shot_2021-03-21_at_12.53.55_AM.png](6%20Sequence/Screen_Shot_2021-03-21_at_12.53.55_AM.png)

```python
wds = ["red", "blue", "green"]
glue = ';'
s = glue.join(wds)
print(s)
print(wds)
```

<aside>
❗ The list needs to have strings when use `join`.

</aside>