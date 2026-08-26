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
