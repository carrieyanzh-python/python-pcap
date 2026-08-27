# python-pcap
Python vs Java import


python:Module/package names, classes, functions, variables	
java:Mainly classes/interfaces/enums

Package structure	Package → modules → objects	
Package → classes/interfaces

import package is allowed, but does not import all its contents	
import package.* imports all accessible types in that package

Import specific item	from math import sqrt	
import java.lang.Math

Static members	from math import pi	import static java.lang.Math.PI

*	from math import *	import java.util.*

mypackage/
    __init__.py
    calculator.py

def add(a, b):
    return a + b

✅ Option 1
from mypackage.calculator import add
print(add(2, 3))

import mypackage.calculator

from mypackage import calculator

A              → package
A.B            → module
A.B.Class      → class

Inside B.py:

class Class:
    def hello(self):
        print("Hello")

__pycache__ = directory for cached .pyc bytecode files. ✅

A docstring is a string literal placed as the first statement of a module, function, class, or method.

Also, ''' ... ''' and """ ... """ can both be used for docstrings:

In Python, sum(), abs(), and range() are built-in functions, so you can use them without importing a module.
1. Common Python built-in functions
Function	Purpose	Example
sum()	Add items	sum([1, 2, 3]) → 6
abs()	Absolute value	abs(-5) → 5
range()	Generate a sequence of numbers	range(1, 5)
min()	Smallest value	min(3, 1, 2) → 1
max()	Largest value	max(3, 1, 2) → 3
len()	Number of items	len("hello") → 5
round()	Round a number	round(3.14) → 3
pow()	Power	pow(2, 3) → 8
divmod()	Quotient + remainder	divmod(10, 3) → (3, 1)
sorted()	Return sorted list	sorted([3,1,2]) → [1,2,3]
reversed()	Reverse iterator	list(reversed([1,2,3]))
enumerate()	Index + value	enumerate(["a","b"])
zip()	Combine iterables	zip([1,2], ["a","b"])
all()	Are all values true?	all([True, True])
any()	Is any value true?	any([False, True])
type()	Get type	type(10) → <class 'int'>
isinstance()	Check object type	isinstance(10, int) → True
int()	Convert to integer	int("10")
float()	Convert to float	float("3.2")
str()	Convert to string	str(100)
list()	Create list	list("abc")
tuple()	Create tuple	tuple([1,2])
set()	Create set	set([1,2,2])
dict()	Create dictionary	dict(a=1)

Important: All of these are built-in. No import is required.

2. Similar functions from the math module
Function	Purpose	Example
math.sqrt()	Square root	math.sqrt(16) → 4.0
math.pow()	Power	math.pow(2, 3) → 8.0
math.fabs()	Absolute value as float	math.fabs(-5) → 5.0
math.ceil()	Round upward	math.ceil(3.2) → 4
math.floor()	Round downward	math.floor(3.8) → 3
math.factorial()	Factorial	math.factorial(5) → 120
math.gcd()	Greatest common divisor	math.gcd(12, 8) → 4
math.lcm()	Least common multiple	math.lcm(4, 6) → 12
math.log()	Logarithm	math.log(10)
math.exp()	e raised to power	math.exp(1)
math.sin()	Sine	math.sin(0) → 0.0
math.cos()	Cosine	math.cos(0) → 1.0
math.tan()	Tangent	math.tan(0) → 0.0

3. Functions from the random module
Function	Purpose
random.random()	Random float from 0.0 to < 1.0
random.randint()	Random integer within range
random.randrange()	Random value from a range
random.choice()	Random item
random.shuffle()	Shuffle a list
random.sample()	Random sample
random.seed()	Set random generator seed

4. Functions from other important PCAP modules
Module	Important functions
math	sqrt(), ceil(), floor(), factorial(), gcd(), pow()
random	random(), randint(), randrange(), choice(), shuffle(), seed()
statistics	mean(), median(), mode(), stdev(), variance()
os	getcwd(), listdir(), mkdir(), remove(), rename()
sys	exit(), getsizeof(), path
datetime	date(), datetime(), timedelta(), strptime()
re	match(), search(), findall(), sub(), split()

PCAP exam point ⭐

print() has several parameters, including: print(*objects, sep=' ', end='\n', file=None, flush=False)
For example:
print("A", "B", "C", sep="-") : Output: A-B-C


*args → tuple
**kwargs → dictionary

Syntax	Inside function	Type
*args	positional arguments	tuple
**kwargs	keyword arguments	dictionary

Why use one versus the other?
Code	How you call sqrt()
import math	math.sqrt(25)
from math import sqrt	sqrt(25)

Multiple inheritance = one child class inherits from two or more parent classes.

Encapsulation ensures data hiding and protection.
Abstraction simplifies the interaction with complex systems by exposing only what is necessary.

o __init__: Initializes an object. __init__ is usually defined inside a class. ✅
o __str__: Defines how an object is represented as a string.
o __add__: Defines behavior for the + operator.
o __eq__: Defines behavior for equality comparison (==).

Method	Purpose	Parameter
__new__()	Creates the object	cls
__init__()	Initializes the object	self

Try, Except, Else, and Finally Blocks
 Try Block: This is where the code that might raise an exception is placed. Python will
monitor this block for any exceptions.
 Except Block: If an exception occurs in the try block, control moves to the except
block. This is where the exception is caught and handled. You can specify what type
of exception to catch, or leave it open to catch all exceptions.
 Else Block: This block is executed if no exception was raised in the try block. It’s
useful for code that should run only when everything goes smoothly.
 Finally Block: The finally block is executed no matter what – whether an exception
was raised or not. It’s often used for cleanup actions like closing files or releasing
resources. Even if there is an unhandled exception, the finally block will still execute
before the program stops.

Common built-in exceptions
Exception	When it happens	Example
ValueError	Correct type, but invalid value	int("abc")
TypeError	Wrong/incompatible data type	"5" + 3
ZeroDivisionError	Division by zero	10 / 0
IndexError	Invalid list/tuple index	[1, 2][5]
KeyError	Dictionary key doesn't exist	{"a": 1}["b"]
NameError	Variable/name doesn't exist	print(x)
AttributeError	Object doesn't have the attribute	"hello".append(1)
ImportError	Import cannot be performed	from math import xyz
ModuleNotFoundError	Module cannot be found	import abcxyz
FileNotFoundError	File doesn't exist	open("abc.txt")
PermissionError	Insufficient permission	Opening a protected file
OSError	Operating-system-related error	File/system operation fails
RuntimeError	General runtime error	Operation cannot be completed
NotImplementedError	Operation is intentionally not implemented	raise NotImplementedError
OverflowError	Numeric result too large	Some numeric operations
RecursionError	Recursion goes too deep	Infinite recursion
MemoryError	Program runs out of memory	Huge memory allocation
AssertionError	assert condition is false	assert 1 == 2
StopIteration	Iterator has no more values	next(iterator)
KeyboardInterrupt	User interrupts program	Ctrl+C
EOFError	input() reaches end-of-file	Input stream ends unexpectedly


BaseException
│
├── Exception
│   │
│   ├── ValueError
│   │   ├── UnicodeError
│   │   └── ...
│   │
│   ├── TypeError
│   ├── ZeroDivisionError
│   ├── IndexError
│   ├── KeyError
│   ├── NameError
│   ├── AttributeError
│   ├── ImportError
│   │   └── ModuleNotFoundError
│   ├── OSError
│   │   ├── FileNotFoundError
│   │   └── PermissionError
│   └── ...
│
├── KeyboardInterrupt
├── SystemExit
└── GeneratorExit

Know ValueError, TypeError, IndexError, KeyError, NameError, AttributeError, ZeroDivisionError, ImportError, ModuleNotFoundError, and FileNotFoundError especially well.

Pandas                  ← library
  └── pandas.core       ← package/subpackage
       └── frame.py     ← module
            └── DataFrame()  ← class

pandas : dataframe
head() → first 5 rows by default.

iloc means integer-location based indexing.
dropna() → remove missing-data rows
inplace=True → make the change directly to the original DataFrame


Python   -> NumPy -> Pandas -> Matplotlib -> scikit-learn -> PyTorch -> Hugging Face -> LangChain -> FastAPI -> AI application / REST API

NumPy       → numerical calculations
Pandas      → data processing
scikit-learn→ machine learning
PyTorch     → deep learning
Hugging Face→ pretrained AI/LLM models
LangChain   → LLM applications/agents
FastAPI     → expose your Python/AI code as an API


python -c "import numpy; print(numpy.__version__)"

NumPy:
>>> a = np.array([1,2,3])
>>> b = np.array([(1.5,2,3), (4,5,6)], dtype = float)
>>> c = np.array([[(1.5,2,3), (4,5,6)],[(3,2,1), (4,5,6)]], dtype = float)

np.zeros((3,4))
np.ones((2,3,4),dtype=np.int16)
np.arange(10,50,5) output : [10 15 20 25 30 35 40 45]
np.linspace(0,2,9)  [0.   0.25 0.5  0.75 1.   1.25 1.5  1.75 2.  ]
np.full((2,2),7)   [[7 7]  [7 7]]
np.eye(2) [[1. 0.]  [0. 1.]]
np.random.random((2,2)), output: [[0.06659435 0.5264786 ] [0.7767073  0.11546391]]
np.empty((3,2))


 
