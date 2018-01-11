#  Learning Python(5th edition)

## 1. Preface
Python is a multi-paradigm language

## A Python Q&A Session
### Why Do People Use Python?
*  Software quality: readable, reuseable
*  Developer productivity: no need to compile, 1/3 or 1/4 size of C++ or Java code
*  Program portability: Windows/Linux/Mac OS
*  Support libraries: so much libraries
*  Component integration: can call C libraries, Java or .Net compoenets
*  Enjoyment

##  2. How Python Runs Programs
### Python Interpreter
read program and carries out the instructions. between python code and hardware, an interpreter can be a native program(C program) or java set
### byte code
"textcode.py" --(compile)-> "bytecode.pyc"(lower-level, platform-independent ) ->
In 3.2 and later, bytecode saved in "\__pycache__" subdirectory.
Only imported files save to bytecode file
### The Python Virtual Machine(PVM)
used to run byte code