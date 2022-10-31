# Creating Python library/Packaging Python projects in Visual Studio 2022

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
      - **anomaly_devosmita/**
        - **\_\_init\_\_.py**
        - **example.py**
    - **tests/**

## Content of the project

### example.py

```
def add_one(number):
  return(number + 1)
```
    
### pyproject.toml  
```
[build-system]
requires = ["setuptools>=61.0"]
build-backend = "setuptools.build_meta"

[project]
name = "example_package_devosmita"
version = "0.0.1"
authors = [
  { name="Devosmita Chatterjee", email="chatterjeedevosmita267@gmail.com" },
]
description = "A small example package"
readme = "README.md"
requires-python = ">=3.7"
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]

[project.urls]
"Homepage" = "https://github.com/pypa/sampleproject"
"Bug Tracker" = "https://github.com/pypa/sampleproject/issues"
```

### README.md
This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.

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
- Create an account with username and password via  https://test.pypi.org/account/register/.
- Run in Developer PowerShell.
```python3 -m pip install --upgrade twine```
```python3 -m twine upload --repository testpypi dist/*``` or ```python3 -m twine upload dist/*```
- Enter username and password in Developer PowerShell.
- View the uploaded package on TestPyPI: https://test.pypi.org/manage/projects/example_package_devosmita.

## Installing the package
- Run in Developer PowerShell.
```python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-package-devosmita```
- Or, Go to View -> Other windows -> Python Environments -> Add Environments -> Anaconda 2020.11 -> Packages(PyPI) -> example-package-devosmita (0.01) -> pip install exa

## Running the package
```from example_package_YOUR_USERNAME_HERE import example```
```example.add_one(2)```
