---
layout: default
title: Python Styleguide - BID SCL
parent: code
nav_order: 1
---

# Python Style Guide – BID SCL

## Basic guidelines for .py files writers
Are our .py files readable and comprehensible – not only today, but also in several months? To assure this, we might apply some general rules to our codes. In this case the main ones would be:

### Presentation
Always include a comment containing the version number of your program, your name or initials, and the date the program was last modified above the program line. Be consistent with the information you provide in your py files.

### 2. Structure
2.1. Include a pip requirements.txt file specifying the dependencies required in your project.

2.2. Create multiple python modules that separates code into parts while maintaining the relation and functionality. For instance, if your program objective is to transform information and create indicators, separate your models into data gathering, data procession, feature creation, indicators creation and finally a master .py file that integrates the program functionality in one file. 
	* Keep module names short 
	* Avoid dot notation; `module.py` instead of `my.module.py`

2.3. To import functions from modules, always specify the function you want to import. Use `from module import function1` or `import module` and use the function as `module.function1`. Avoid `from module import *`, this makes the code harder and it is harder to read the dependencies from the module. 

### 3. Expressions
3.1. Limit all lines to a maximum of 79 characters. For long statements use backslashes to continue and indentation to clearly distinguish  the continuation line.
```
with open(‘{path}’) as file1, \
         open(‘{path}’) as file2:
         file2.write()
```

3.2. For mathematical expressions, always break expressions before binary operation for a better readability of the code. 
```
# OK
variable = (var1 
                    + var2
	     + var3)
# NOT OK
variable = (var1 +
                    var2 +
	     var3)
```

3.3. Always surround binary operators (=, +=, -=, ==, <, >, !=, <>, <=, >=, in, not in, is, is not, and, or, not) with a single space on both sides.

3.4. Avoid multiple statements on the same line. 
```
# OK
if variable == ‘value’:
	do

# NOT OK
If variable == ‘value’: do
```

### 4. Further information 
> Python, Structuring your project. Retrieved from https://docs.python-guide.org/writing/structure/
> Rosuum, Guido van, Warsaw, Barry, and Coghlan, Nick (2001). PEP 8 – Style Guide for Python Code. Python. Retrieved from http://greentv.mobiloitte.com/FTP-LOCATION/CoodingGuidence/images/Style%20Guide%20for%20Python%20Code%20_%20Python.org.pdf