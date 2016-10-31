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

