# Creating Python library or package in Visual Studio 2022

## Installing the latest version of pip
- Run in Developer PowerShell.

```python3 -m pip install --upgrade pip```

## Creating a simple project
- The structure of the project should be as follows.
  - **packaging_tutorial/**
    - **LICENSE**
    - **pyproject.toml**
    - **README.md**
    - **src/**
      - **squareroot_no/**
        - **\_\_init\_\_.py**
        - **libs.py**
        - **example.py**
    - **tests/**

## Content of the project

### \_\_init\_\_.py
Intra-Package Module Dependencies:
```
from . import libs as l
```

### libs.py
```
import math
```

### example.py
```
from . import libs as l

def squareroot(number):
  return(l.math.sqrt(number))
```
    
### pyproject.toml  
```
[build-system]
requires = ["setuptools>=61.0"]
build-backend = "setuptools.build_meta"

[project]
name = "squareroot_no"
version = "0.0.1"
authors = [
  { name="Devosmita Chatterjee", email="chatterjeedevosmita267@gmail.com" },
]
description = "An example package"
readme = "README.md"
requires-python = ">=3.7"
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]

[project.urls]
"Homepage" = "https://github.com/pypa/squareroot_no"
"Bug Tracker" = "https://github.com/pypa/squareroot_no/issues"
```

### README.md
This is an example package.

### LICENSE
- A license can be chosen from https://choosealicense.com/.
- The MIT license.

```
Copyright (c) 2018 The Python Packaging Authority

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Generating distribution packages
- Run in Developer PowerShell.

```python3 -m pip install --upgrade build```

```python3 -m build```

## Uploading the package to the Python Package Index
- Create an account with username and password via  https://test.pypi.org/account/register/ or https://pypi.org/account/register.
- Run in Developer PowerShell.

```python3 -m pip install --upgrade twine```

```python3 -m twine upload --repository testpypi dist/*``` or ```python3 -m twine upload dist/*```
- Enter username and password in Developer PowerShell.
- View the uploaded package on TestPyPI or PyPI: https://test.pypi.org/manage/projects/squareroot_no or https://pypi.org/manage/projects/squareroot_no.

## Installing the package
- Run in Developer PowerShell.

```python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps squareroot_no```

or

```python3 -m pip install squareroot_no```

- Or, Go to View -> Other windows -> Python Environments -> Anaconda 2020.11 -> Packages(PyPI) -> anomaly-devosmita (0.0.1) -> Run command: pip install anomaly-devosmita

## Running the package

```from squareroot_no import example```

```example.squareroot(2)```
