# Python 3

## Contents

* [Comment](#comment)
* [Module Import](#module-import)
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
* [Operators](#operators)
  * [Comparison Operators](#comparison-operators)
  * [Logical Operators](#logical-operators)
  * [Identity Operator](#identity-operator)
  * [Membership Operator](#membership-operator)
  * [Arithmetic Operator](#arithmetic-operator)
  * [Bitwise Operator](#bitwise-operator)
* [Reference](#reference)


## Comment

Comment is starting with a #.

```python
# This is a comment
```

## Module Import

```python
import <module>
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

## Reference

* [Python Documentation](https://docs.python.org/3/)


