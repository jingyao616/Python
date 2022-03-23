# 3 Debugging

# 3.3 Syntax Errors

Syntax refers to the structure of a program and the rules about that structure. For example, in English, a sentence must begin with a capital letter and end with a period.

```python
print("Hello World!"    #lack of closing parentheses
```

# 3.4 Runtime Errors

The second type of error is a runtime error, so called because the error does not appear until you run the program. These errors are also called exceptions because they usually indicate that something exceptional (and bad) has happened.

```python
print(3/0)       #illegal to print it
```

# 3.5 Semantic Errors

The third type of error is the semantic error. If there is a semantic error in your program, it will run successfully in the sense that the computer will not generate any error messages. However, your program will not do the right thing.

The problem is that the program you wrote is not the program you wanted to write.

# 3.6 Know your Error Message

```python
current_time_str = input("What is the current time (in hours 0-23)?")
wait_time_str = input("How many hours do you want to wait")

current_time_int = int(current_time_str)
wait_time_int = int(wait_time_int)         #should be: wait_time_int = int(wait_time_str)

final_time_int = current_time_int + wait_time_int
print(final_time_int)
```

## 3.6.1 SyntaxError

## 3.6.2 Type Error

TypeErrors occur when you you try to combine two objects that are not compatible.

eg. try to add together an integer and a string.

```python
a = input('wpisz godzine')
x = input('wpisz liczbe godzin')
int(x)
int(a)
print(x, type(x))
h = x // 24
s = x % 24
print (h, s)
a = a + s
print ('godzina teraz', a)
```

```python
a = input('wpisz godzine')
x = input('wpisz liczbe godzin')
x= int(x)       #corect
a= int(a)       #corect
print(x, type(x))
h = x // 24
s = x % 24
print (h, s)
a = a + s
print ('godzina teraz', a)
```

## 3.6.3 NameError

Name errors almost always mean that you have used a variable before it has a value. Often NameErrors are simply caused by typos in your code. They can be hard to spot if you don’t have a good eye for catching spelling mistakes.

```python
present_time = input("Enter the present timein hours:")
set_alarm = input("Set the hours for alarm:")
int (present_time, set_time, alarm_time)   
alarm_time = present_time + set_alarm
print(alarm_time)
```

Correction:

```python
present_time = input("Enter the present timein hours:")
set_alarm = input("Set the hours for alarm:")
int(present_time)
int(set_alarm)
alarm_time = present_time + set_alarm
print(alarm_time)
```

## 3.6.4 ValueError

Value errors occur when you pass a parameter to a function and the function is expecting a certain limitations on the values, and the value passed is not compatible. We can illustrate that with this particular program in two different ways.

```python
current_time_str = input("What is the current time (in hours 0-23)?")
current_time_int = int(current_time_str)

wait_time_str = input("How many hours do you want to wait")
wait_time_int = int(wait_time_int)

final_time_int = current_time_int + wait_time_int
print(final_time_int)

#if run the program but not type anything to the dalog box then click OK
#will get the following error message. 
```