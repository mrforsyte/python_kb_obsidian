# Content

* Type annotations and type hints;
* Adding static types to code;
* Running a static type checker;
* Enforcing types at runtime;


Python is dynamically typed language, that means that _python checks code only when it runs_. 

```py
if False:
    1+'lol'
else:
    1+1

```
**Result of this will be 3** because the code with error will never run.
However, if we try to run this code
```py
In [23]: 1+'lol'
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-23-2d2bb3a265fc> in <module>
----> 1 1+'lol'

TypeError: unsupported operand type(s) for +: 'int' and 'str'

```
__Static type checking is done before code is run__

## Duck Typing
>It it walks like a duck and quacks like a duck then it must be a duck.

_The idea is that type of an object of a class is less important then methods it implements_.
Instead of checking _type_ of this object we will be checking _methods and attributes_ it has.

## Type Hinting
* A formal solution to indicate the type of a value;
```py
In [28]: def greet(name:str)->str:
    ...:     return "Hello, " + name
    ...: 

In [29]: greet("Ross")
Out[29]: 'Hello, Ross'

    
```
In the given example there is _hint_ in parametrs and hint with what function should return _->_ string


**mypy** package does all the dirty job
```py
pip install mypy

mypy given_python_file

course/days/01-03-datetimes/code$ mypy datetime_date.py 
Success: no issues found in 1 source file

```
## Annotations

```py
n [30]: pi: float = 3.456

In [31]: pi
Out[31]: 3.456

In [32]: type(pi)
Out[32]: float

In [33]: __annotations__
Out[33]: {'pi': float}

```
