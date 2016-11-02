# Python Notes

## Characteristics

* Whitespace is important
* No trailing semicolons

## Variables
```
my_int = 7
my_float = 1.23
my_bool = True
```
## Comments
```
# This is a comment
"""This is a
multi-line comment.
"""
```
## Math
```
addition = 72 + 23
subtraction = 108 - 204
multiplication = 108 * 0.5
division = 108 / 9
exponentiation = 2 ** 3        # 2^3
modulo = 3 % 2
```
## Strings
```
message = "Hello world!"
h = message[0]
substr = message[1:4]
len(message)
message.lower()
str(2) == "2"
concat = "Monty" + " Python"
```
_Why do some methods have dots while others don't?_
The methods with dot notation only work with strings, while others (like len) can work on other data types

## String Formatting
```
name = raw_input("What is your name?")
print "Your name is %s." % (name)
```
## Conditionals
```
1 < 2 and 2 < 3         # True
1 > 2 or 2 > 3          # False
not False               # True
```
Precedence: not > and > or

## if
```
if some_function():
    # block line 1
    # block line 2
    # ...
elif:
    # code
else:
    # code
```

## Functions
```
def function_name():
    """ Some comments
    """
    # body
```
##Imports

### Generic Import
```
import math
print math.sqrt(25)
```
###Function Import
```
from module import function
from math import sqrt
print sqrt(25)
from module import *            # universal import
```
###Built-in Functions
```
max(a,b,c,d)
min(a,b,c,d)
abs(-17)
type(3.14)      # <type 'float'>
```
## Lists
```
list_name = [item_1, item_2, item_3]
print list_name[0]
empty_list = []
empty_list.append('item')
print len(list_name)
print list_name
slice = list_name[a:b]  # from a to before b
my_list[:2]             # beginning to before index 2
my_list.index(item)
my_list.insert(index, item)
my_list.sort()
my_list.remove(item)
my_list.pop(index)      # removes item at index (and returns)
del(my_list[index])     # deletes but doesn't return
```
## Dictionaries
```
d = {'key1' : 1, 'key2' : 2, 'key3' : 3}
empty_dict = {}
print d['key1']
dict_name[new_key] = new_value
del dict_name[key_name]
```
## For Loops
```
for variable in list_name:         
for number in range(0, 10):
for index, item in enumerate(list_name):
for itema, itemb in zip(list_a, list_b):  # stops at end of shorter list
```
##While/Else, For/Else
else is executed if loop is not entered, or if loop exits normally (not break)



