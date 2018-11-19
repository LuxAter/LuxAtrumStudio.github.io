title: Estl
author: Arden Rasmussen
tags:
  - Cpp
  - ''
categories:
  - CS
thumbnail: /gallery/thumbnails/estl.png
date: 2018-09-12 10:03:00
---
**ESTL** is a set of header files that can be used to add advanced utilities to C++ code. The header files each implement a new utility that can be included into any project.

[![GitHub Link](https://img.shields.io/badge/Github-Estl-blue.svg?style=for-the-badge)](https://github.com/LuxAtrumStudio/estl) ![](https://img.shields.io/github/repo-size/LuxAtrumStudio/estl.svg?style=for-the-badge)


<!-- more -->

There are several available implemented header files that are described below

## ArgParse ##

```cpp
#include<estl/argparse.hpp>
```

This file is an implementation of a highly extendable argument parsing system.  The implemented syntax is similar to that of Pythons argparse module. The base class will generate help displays that list all possible arguments. There is currently support for arguments that set flags, or assigning variables of most base types (``bool``, ``char``, ``int``, ``double``, ``string``, or a list of any of those).

## Basic ##

```cpp
#include<estl/basic/basic.hpp>
```

The *basic* sub folder implements a minimized alternatives to some of the larger classes. Including ``Matrix``, ``Vector``, and ``Format``. Since each of these are fairly complex, this *basic* implementation removes much of the extend ability, but provides a much larger boost in speed, and simplicity.

## Format ##

```cpp
#include<estl/format.hpp>
```

This file implements a python like string formatting engine, allowing for the use of printf like utility without requiring character buffers. This also extends that utility, by allowing  the use of overloaded operators. By passing a custom ``class`` or ``struct`` the format of that object will first be attempted by calling a member function of that object called ``format``, if that fills, then it will attempt to use ``printf`` type formatting, and finally that system will resort to using ``ostream`` formatting. Through this method, any object or type can be cleanly formatted, and provide a string containing the formatted text.

## Fuzz ##

```cpp
#include<estl/fuzz.hpp>
```

The *fuzz* file implements an efficient string based fuzzy finder. Utilizing either Manhattan distance or Levenshtein distance calculations, the system determines the closest ``n`` matches to the input string in a vector of strings. It then returns that array sorted in order of closeness distance.

## Json ##

```cpp
#include<estl/json.hpp>
```

The *json* file implements reading/writing of ``.json`` files from C++, as well as easy manipulation of the json objects, and pretty printing. **Note** A major rewrite of this module is in development.

## Logger ##

```cpp
#include<estl/logger.hpp>
```

The logging system implemented allows for extreme control over a easy to use logging system. The general format for a logger can be specified, then each call to a logger uses ``printf`` formatting. The collection of call functions utilize macros to determine the source file, function name, and line number that the log message was called from, allowing significantly improved diagnoses of logged messages. There are five different logger bases, then the default logger can consist of any collection of these.

* ConsoleLogger
* FileLogger
* DailyLogger
* CounterLogger
* StreamLogger

More detail can be found in the documentation.

## Matrix ##

```cpp
#include<estl/matrix.hpp>
```

The *matrix* file is primarily to provide a mathematical matrix object. Using templated arguments, the matrix class provides all common mathematical matrix operations, utilizing the templated types commands. **Note** that sparse matrix optimizations have not been implemented.

## Stream ##

```cpp
#include<estl/stream.hpp>
```

The *stream* file is to provide an extended implementation of ``printf`` that utilizes C++ streams. This is a smaller version of the *format* file. This again implements the use of stream operators, but does not utilize the more advanced features that are available in the *format* file.

## Tree ##

```cpp
#include<estl/tree.hpp>
```

The *tree* class implements an arbitrary tree data structure. It provides easy ways to add or remove children. There are three different iterators that can be used for traversing the tree:

* depth_iterator
* sibling_iterator
* leaf_iterator

The class also provides methods for printing the tree.

## Variable ##

```cpp
#include<estl/variable.hpp>
```

This file provides a general variable which is represented as a union of most fundamental C++ types, as well as vectors of those types, including

* ``bool``
* ``char``
* ``signed char``
* ``unsigned char``
* ``signed short int``
* ``unsigned short int``
* ``signed int``
* ``unsigned int``
* ``signed long int``
* ``unsigned long int``
* ``signed long long int``
* ``unsigned long long int``
* ``float``
* ``double``
* ``long double``
* ``std::string``
* ``const char*``

## Variadic ##

```cpp
#include<estl/variadic.hpp>
```

The *variadic* files implements utility functions for handling variadic packed template arguments. It provides methods for unpacking arguments into ``vector``, ``tuple``, and ``vector<any>``, allowing simple access of packed arguments.

## Vector ##

```cpp
#include<estl/vector.hpp>
```

The *vector* file is a mathematical vector object. Using templated arguments, the vector class provides most common mathematical vector operations, utilizing the templated types commands.
