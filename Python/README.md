# Python 3

## Contents

* [Comment](#comment)
* [Printing](#printing)
* [Variable Assignment](#variable-assignment)
* [Variable Interpolation](#variable-interpolation)
* [Type of a Value](#type-of-a-value)
* [Data Structures](#data-structures)
* [Conditionals](#conditionals)
* [Loops](#loops)
  * [While Loop](#while-loop)
  * [For Loop](#for-loop)
* [Control Flow](#control-flow)
  * [Break](#break)
  * [Continue](#continue)
  * [Else](#else)
  * [Pass](#pass)
* [Functions](#functions)
* [Generators](#generators)
* [Classes](#classes)
* [Modules](#modules)
* [Operators](#operators)
  * [Comparison Operators](#comparison-operators)
  * [Logical Operators](#logical-operators)
  * [Identity Operator](#identity-operator)
  * [Membership Operator](#membership-operator)
  * [Arithmetic Operator](#arithmetic-operator)
  * [Bitwise Operator](#bitwise-operator)
* [Exceptions](#exceptions)
  * [Handling Exceptions](#handling-exceptions)
  * [Raising an Exception](#raising-an-exception)
* [File I/O](#file-io)
* [Built-in Functions](#built-in-functions)
  * [Numeric Functions](#numeric-functions)
  * [String Functions](#string-functions)
  * [Container Functions](#container-functions)
  * [Object and Class Functions](#object-and-class-functions)
* [Reference](#reference)


## Comment

Comment is starting with a #.

```python
# This is a comment
```

## Printing

```python
print('This is a print function')
```

## Variable Assignment

An integer is immutable. Assigning a new value to an integer will create and entirely different object.

```python
x = 0   # creating a new object variable.
y = x 	# Referencing to the same object.
var='a' if True else 'b'   # Conditional variable.
```

## Variable Interpolation

```python
x=0; print('The value of x is {}'.format(x))
x=0; print(f'The value of x is {x}')
```

## Type of a value

Prints the class type of the value.

```python
type(x)
print(type(x))
```

```python
>>> x = 7.0
>>> print(type(x))
<class 'float'>
>>> y = ['a', 'b', 'c' ]
>>> print(type(y))
<class 'list'>
>>> 
```

## Data Structures

Lists and Dictionary are mutable. You can modify the items in position.</br>
Tuples and Range are immutable.</br>
Set in an unordered list.

```python
list=['a1', 'a2', 'a3']
tuple=('a1', 'a2', 'a3')
dictionary = { 'one': 1, 'two': 2, 'three': 3 }
set = { 1, 2, 3, 4, 5 }
x = range(5) # range(start, end, step)
```

## Conditionals

```python
if x>y:
    print('something')
elif x<y:
    print('something else')
else:
    print('no match')
```

## Loops

### While Loop

```python
while True:
    print('something')
while(n<5):
    print('n {}'.format(n))
```

### For Loop

```python
for n in arr:
    print(n) # print('{}'.format(n))
```

## Control Flow

### Break

Break out of a loop.

```python
>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             break
...     else:
...         # loop fell through without finding a factor
...         print(n, 'is a prime number')
...
2 is a prime number
3 is a prime number
5 is a prime number
7 is a prime number
```

### Continue

Skip the current execution.

```python
>>> for num in range(2, 10):
...     if num % 2 == 0:
...         print("Found an even number", num)
...         continue
...     print("Found a number", num)

Found an even number 2
Found a number 3
Found an even number 4
Found a number 5
Found an even number 6
Found a number 7
Found an even number 8
Found a number 9
```

### Else

Execute after normally completing the loop.

```python
while expression:
    "Code Block"
else:
    "Code Block"
```

```python
for target_list in expression_list:
    "Code Block"
else:
    "Code Block"
```

### Pass

The pass statement does nothing. It can be used when a statement is required syntactically but the program requires no action.

```python
>>> while True:
...     pass  # Busy-wait for keyboard interrupt (Ctrl+C)
...
```

```python
>>> class MyEmptyClass:
...     pass
...
```

## Functions     

Functions are procedures which returns null value by default.

```python
def function(n):
    print(n)

function(10)
```

Decorator will pass the function below as an argument to the decorator function.

```python
def f1(f):
    def f2():
        print('Start')
        f()
        print('End')

@f1
def f3():
    print('Something')

f3()
```

## Generators

Generators are a simple and powerful tool for creating iterators. They are written like regular functions but use the yield statement whenever they want to return data.

```python
def reverse(data):
    for index in range(len(data)-1, -1, -1):
        yield data[index]
```

```python
>>> for char in reverse('golf'):
...     print(char)
...
f
l
o
g
```

## Classes

Evertything in python is an object. A class is how an object is defined.

```python
class Classname():
    def function(self):
        print('first function')

x = Classname()
x.function()
```
An instance of a class is called an object.

```python
class Dog:
    kind = 'canine'         # class variable shared by all instances
    def __init__(self, name):
        self.name = name    # instance variable unique to each instance

>>> d = Dog('Fido')         # Object
>>> e = Dog('Buddy')
>>> d.kind                  # shared by all dogs
'canine'
>>> e.kind                  # shared by all dogs
'canine'
>>> d.name                  # unique to d
'Fido'
>>> e.name                  # unique to e
'Buddy'
```

Class inheritance.

```python
#!/usr/bin/env python3

class Animal:
    def __init__(self, name):
        self._name = name

    def Name(self):
        return self._name
    

class Dog(Animal):
    type = 'canine'
    def __init__(self, name):
        Animal.__init__(self, name)
    
    def Type(self):
        return self.type

def main():
    x = Animal("Buddy")
    y = Dog("Fido")
    print(x.Name())
    print(f'{y.Name()}, {y.Type()}')

if __name__ == '__main__': main()
```

## Modules

Importing a module.

```python
import <module>

or

from <module> import <function>
```
e.g:

```python
import sys  # from sys import *

v = sys.version_info
print('Python Version is {}.{}.{}'.format(*v))
```
Module Example.

```python
>>> import sys
>>> sys.version_info
sys.version_info(major=3, minor=6, micro=5, releaselevel='final', serial=0)
>>> sys.platform
'darwin'
>>>
>>> import os
>>> os.name
'posix'
>>> os.getenv('PATH')     # get path env variable.
'/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin'
>>> os.getcwd()           # Current working directory.
'/Users/gsree/Documents/Python'
>>> os.urandom(10)        # Get random string in hex bytes.
b'\xa5\xb2)\x10"\xe6\xce\xe8\xc2\x17'
>>> os.urandom(10).hex()  
'417249cb1b85e2437cec'
>>>
>>> import random
>>> random.randint(1, 100000)   # get random number between 2 numbers.
92867
>>> x = list(range(25))
>>> x
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24]
>>> random.shuffle(x)            # Shuffles the list.
>>> x
[7, 16, 13, 14, 23, 18, 5, 0, 10, 6, 20, 24, 2, 9, 11, 1, 22, 19, 4, 21, 15, 3, 17, 8, 12]
>>> 
>>> now = datetime.datetime.now()
>>> print(now)
2018-04-07 14:06:30.477743
>>> print(now.year, now.month, now.day, now.hour, now.minute, now.second, now.microsecond)
2018 4 7 14 6 30 477743
```

## Operators

### Comparison Operators

```
==    a == b      Equal
!=    a != b      Not Equal
<     a < b       Less than
>     a > b       Greater than
<=    a <= b      Less than equal
>=    a >= b      Greater than equal
```

### Logical Operators

```
and     x and y     True is both x and y
or      x or y      True if x or y
not     not x       Invert state
```

### Identity Operator

```
is        x is y        True if same object
is not    x is not y    True if not the same object
```

### Membership Operator

```
in        x in y        True if member of collection y
not in    x not in y    True if x not member of collection y
```

### Arithmetic Operator

```
+		Addition
-		Subtraction
*		Multiplication
/		Division
//		Integer Division
%		(Remainder) Modulo
**		Exponent
-		Unary negative
+		Unary positive
```

### Bitwise Operator

```
&		AND
|		OR
^		XOR
<<		Shift left
>>		Shift right
```
## Exceptions

Exceptions are an excellent way to report runtime errors.

### Handling Exceptions

syntax:

```python
try:                 	 # To catch the exception.
    "code block"
except <ExceptionName>:  # Handle a specifc Exception.
    "Code Block"
except:            	 # Handle all other exceptions.
    "Code Block"
else:
    "Code Block"
```

```python
import sys

def main():
    try:
        x = 5/0
    except ValueError:
        print('ValueError: Incorrect value')
    except:
        print(f'Unknown Error: {sys.exc_info()[1]}')
    else:
        print(x)

if __name__ == '__main__': main()
```
### Raising an Exception

Syntax:

```python
raise <ErrorType>
```
or 

```python
raise <ErrorType>(f'<Message>')
```

e.g:

```python
>>> x = -1
>>> if x < 0:
...     raise TypeError('Value of x cannot be less than zero')
... 
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: Value of x cannot be less than zero
>>> 
```
To handle the exception properly us 'try' block.

```python
x = -1
try:
    if x < 0:
        raise TypeError(f'Value of x cannot be less than zero')
except TypeError as e:
    print(f'Value Error: {e}')
```

## File I/O

```python
>>> f = open('a.txt')
>>> for line in f:
...   print(line)
... 
Hello World !

Hello World !!

>>> 
>>> f = open('a.txt')            # Same as, f = open('a.txt', 'r')
>>> for line in f:
...   print(line.rstrip())      # Reading line by line stripping spaces and newline.
... 
Hello World !
Hello World !!
>>> f = open('a.txt', 'w')       # Open in write mode. Will clear the file.
>>> f = open('a.txt', 'a')       # Open in append mode.
>>> f = open('a.txt', 'r+')      # Open in read and write mode.
>>> f = open('a.txt', 'r+b')      # b for binary, t for text mode
```

Line ending is represented by a '\n' (newline character) or single line feed (LF) character, ASCII 10 decimal, or zero A hex. This will take 1 byte. In other systems, a new line is represented by a carriage return (CR) character, ASCII 13 decimal, or zero D hex.

```python
>>> f = open('a.txt','rt')
>>> o = open('b.txt','wt')         # Open in write and text mode.
>>> for l in f:
...   print(l.rstrip(), file=o)       # or use o.writelines(l), however print write with proper line endings.
...   print('.', end='', flush=True)  # flush=True flushes output buffer. end='' avoid adding newline at the end.
... 
..>>> o.close()             # close the file to avoid any data loss.
```

Binary file write.

```python
def main():
    i = open('pic-a.jpg', 'rb')
    o = open('pic-b.jpg', 'wb')
    while True:
        buf = i.read(10240)
        if buf:
            o.write(buf)
            print('.', end='', flush=True)
        else: break
    o.close()
    
if __name__ == '__main__': main()
```
## Built-in Functions

### Numeric Functions

```python
>>> x=5
>>> y=-6
>>> z='7'
>>> int(z)          # int contructor to convert to integer.
7
>>> float(x)
5.0
>>> abs(y)          # abs to get absolute value.
6
>>> divmod(x,y)     # divmod return both quotient and remainder.
(-1, -1)
>>> divmod(x,x)
(1, 0)
>>> complex(x, 3)    # complex function is used for complex numbers. j is the imaginary part.
(5+3j)
>>> 

```

### String Functions

Strings are first class objects in python 3.</br>
Strings are immutable.

These are the common methods for a string.

```python
>>> 'hello world!'.upper()
'HELLO WORLD!'
>>> 'hello world!'.capitalize()
'Hello world!'
>>> 'hello world!'.title()
'Hello World!'
>>> 'Hello World!'.swapcase()
'hELLO wORLD!'
>>> 'Hello World!'.lower()
'hello world!'
>>> 'Hello World!'.casefold()    # Similar to lower() but more strong.
'hello world!'
>>> s1 = "hello"
>>> s2 = "world"
>>> s1 + ' ' +  s2            # Concatenation
'hello world'
>>> 'Hello World{}'.format('!')
'Hello World!'
>>> 'Hello {}{}{}{}{}!'.format('W', 'o', 'r', 'l', 'd')
'Hello World!'
>>> 'He{1}{1}{0} W{0}r{1}d!'.format('o', 'l')
'Hello World!'
>>> 'He{y}{y}{x} W{x}r{y}d!'.format(x = 'o', y = 'l')
'Hello World!'
>>> x = 555
>>> '{}'.format(x)
'555'
>>> '{:<5}'.format(x)    # Left adjust with 5 spaces.
'  555'
>>> '{:05}'.format(x)    # Left adjust with 5 spaces zer filled.
'00555'
>>> '{:+05}'.format(x)
'+0555'
>>> x = 555 * 555
>>> '{:,}'.format(x)
'308,025'
>>> '{:,}'.format(x).replace(',','.')       # replace , with .
'308.025'
>>> '{:f}'.format(x)
'308025.000000'
>>> '{:.3f}'.format(x)        # limit to 3 decimal places.
'308025.000'
>>> x = 55
>>> '{:b}'.format(x)       # binary
'110111'
>>> '{:d}'.format(x)       # decimal
'55'
>>> '{:x}'.format(x)       # hexadecimal
'37'
>>> '{:o}'.format(x)       # octal
'67'
>>> f'{x:o}'               # f string formatting started from python version 3.6.x onwards
'67'
>>> f'{x:b}'
'110111'
>>> f'{x:d}'
'55'
>>> f'{x:x}'
'37'
>>> s = 'Hello World'
>>> s.split()             # Splitting a string, by default use space for splitting. It will fold all spaces and newline before splitting.
['Hello', 'World']
>>> s.split('o')          # Splitting string at letter 'o'
['Hell', ' W', 'rld']
>>> l = s.split()
>>> l
['Hello', 'World']
>>> ':'.join(l)           # Joining list with ':'
'Hello:World'
```

```python
>>> s = 'hello world'
>>> print(repr(s))       # repr gives best possible string representation.
'hello world'
>>> print(ascii('🖖'))   # gives the ascii value of a character.
'\U0001f596'
>>> print(chr(128406))   # prints the character represented by the unicode position.
🖖
>>> print(ord('🖖'))     # ord gives you the unicode position of a character.
128406
```

### Container Functions

```python
>>> x = (1,2,3,4,5)
>>> y = ( 0, 0, 0, 0 )
>>> z = ( 0, 0, 1, 0 )
>>> len(x)               # length of 
5
>>> reversed(x)          # gives reversed object.
<reversed object at 0x103a48ba8>
>>> list(reversed(x))
[5, 4, 3, 2, 1]
>>> sum(x)               # gives sum of the numbers.
15
>>> sum(x, 10)
25
>>> max(x)
5
>>> min(x)
1
>>> any(x)              # True is any value is not empty or zero
True
>>> any(y)
False
>>> any(z)
True
>>> all(z)
False
>>> all(x)
True
>>> zip(x, y)
<zip object at 0x103a4f388>
>>> list(zip(x, y))
[(1, 0), (2, 0), (3, 0), (4, 0)]
>>> x = ( 'a', 'b', 'c', 'd', 'e' )
>>> enumerate(x)                     # enumerate gives you index and value.
<enumerate object at 0x103a4de58>
>>> list(enumerate(x))
[(0, 'a'), (1, 'b'), (2, 'c'), (3, 'd'), (4, 'e')]
```

### Object and Class Functions

```python
>>> x = 5
>>> type(x)             # type gives the class of object.
<class 'int'>
>>> isinstance(x, int)  # isinstance check if the object is of a specific class.
True
>>> isinstance(x, float)
False
>>> id(x)               # id gives object id.
4305295872
```

## Reference

* [Python Documentation](https://docs.python.org/3/)


