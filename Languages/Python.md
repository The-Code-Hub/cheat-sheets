# Python Cheatsheet

##### Table of Contents

- [Variables](#variables)  
- [Types](#types)
- [Operators](#operators)
- [If, elif, else](#if-elif-else)
- [Data Structures](#data-structures)
- [Loops](#loops)
- [Functions](#functions)
- [Classes](#classes)
- [Indentation](#indentation)
- [Naming Conventions](#naming-conventions)
- [Comments](#comments)
- [Error handling](#error-handling)
- [Definition skipping](#definition-skipping)
- [Type casting](#type-casting)

## Variables

```python
name = "Your Name"
number = 0

# Static typing
name: str = "Your Name"
number: int = 0
```

### Constants

Constants work the same as normal variables and are only syntactical sugar.
UPPER_CASE IS ALWAYS USED.

```python
NAME = "Duck"
LONG_NAME = "Quack Duck"
```

## Types

| Name | Static typing | Example |
| --- | --- | --- |
| String | str | "alex" |
| Int | int | 10 |
| Float | float | 10.0 |
| Boolean | bool | True, False |
| Tuple | tuple[] | ("hello", 10) |
| List | list[] | [1, 2, 3, 4] |
| Dictionary | dict[] | {name: "alex", hobby: "programming"} |

### Strings

```python
# Strings can be declared with '', or ""
name = "alex"
name = 'alex'
```

#### String concat

```python
first_name = "alex "
last_name = "parra"

full_name = first_name + last_name
```

#### f string

```python
guest = "alex"
print(f"Hello {guest}!")
```

## Operators

### Comparison

| Symbol | Reading |
| --- | --- |
| ==  | equals |
| > | greater then |
| < | lesser then |
| >= | greater or equal then |
| <= | lesser or equal then |

### Logical

| and | or |
| --- | --- |

## If, elif, else

```python
number = 5

if number == 0:
    print("zero")
elif number > 0 and number <= 10:
    print("between 1 and 10")
else:
    print("bigger than 10")
```

## Data structures

### Tuple

Tuples are fixed size and can have multiple-types.

```python
my_tuple = (1, "name")

# Static typing
my_tuple: tuple[int, str] = (1, "name")
```

### Array

Array’s are a list of values from the same type.

```python
empty_array = []
int_array = [1, 2, 3, 4]

# Access by index
# Array always start at index 0
int_array[0] # 1

# Access by index range
int_array[0:2] # 1, 2, 3

# Access the last element
int_array[-1] # 4

# Static typing
int_array: list[int] = [1, 2, 3, 4]
```

### Dictionary

Dictionaries are a `key: value` pair data type.

```python
person = {1: "one", 2: "two"} 

# Access value by key
person[1] # "one"

# Static typing
person: dict[int, str]
```

## Loops

### For

```python
name_list = ["jean", "alice", "herbert"]

for name in name_list:
    print(f"hello {name}!")

# "jean"
# "alice"
# "herbert"
```

### While

```python
flag = True

while flag {
    flag = False
}
```

### List comprehension

```python
# Multiply every number in a given range
lc = [x * 2 for x in range(10)]
```

## Functions

```python
def add(n1, n2):
    return n1 + n2

# Static typing
def add(n1: int, n2: int) -> int:
    return n1 + n2
```

## Classes

```python
class Person:
    def __init__(self) -> None:
        # The self keyword denotes that the variable 
        # can be accessed by the entire class methods.
        self.global_value = 10

	# Methods always need to receive self
    def method(self, value: int) -> None:
        print("i'm a method")

me = Person()
me.method()

# Output: i'm a method
				
```

### Class parameters

```python
class Dog:
    # Receive parameters after self
    def __init__(self, age: int, name: str) -> None:
		 self.age = age
		 self.name = name

    def bark(self) -> None:
        print(f"{self.name} is barking")

my_dog = Dog(10, "doug")
my_dog.bark()

# Output: doug is barking
```
## Indentation
Python uses levels of indentation to differ statements, as seen above, the level of indentation is denoted by a `:`
Always indent using 4 spaces.
```python
# Not putting the correct indentation can leave messy problems
def no_indentation:
print("fail")

# Or

for i in 1..10:
print(i) # i is not present in this scope because is not in the correct indentation
```

## Naming conventions

```python
# Variables are always snake_case
name = "alex"
middle_name = "parra"
int_list = [1, 2, 3, 4]

# Constants are always UPPER_SNAKE_CASE
FIRST_NAME = "alex"

# Functions follow the same principal for varibles
def slice_name(name: str) -> str:
    ...

# Classes follow the UpperCamelCase
class Person
class TallPerson
```

## Comments

```python
# Comments start with # and are not stopped if # appears
# Multiple lines always require #
```

### Docstring

```python
# Docstrings are explanations of what classes and functions do
def say_hi(name: str) -> None:
    """Receive a string and greet it!"""
    print(f"hello {name}!")

class Person:
    """Describes a real person"""
    # They are often used by IDE's to provide fast feedback on their usage
```

## Error handling

```python
# When you try to do something that might fail on run-time
try:
    crash = 10 / 0

except ZeroDivisionError:
    # handle the error here
    print("You can't devide by 0")

finally:
    # Only executed after the try/except
    # finally is totally optional
```

### Chain except

```python
try:
    crash = 10 / 0

except ZeroDivisionError:
    # handle the error here
    print("You can't devide by 0")

except TypeError:
		...
except ValueError:
		...
```

### raise

```python
# if for some reason you want to throw an exception yourself:
if number > 10:
    raise Exception("Number cannot be bigger than 10")
```

## Definition skipping

```python
# Sometimes it can be useful to skip a method or function definition

def to_implement(n1: int, name: str) -> bool:
    ...

class Skip:
    ...
```

## Type casting

```python
# Transform a value to another, be careful, it may lead to runtime exceptions.
# Just wrap the value you want with the name of the type, float(), int(), str()
integer = 10
string_int = str(integer)

calculation = int(10.0 + 5.5 / 15)
```
