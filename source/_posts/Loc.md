title: Loc
author: Arden Rasmussen
tags:
  - Python
categories:
  - CS
thumbnail: /gallery/thumbnails/loc.png
date: 2018-06-21 10:56:00
---
**Loc** is a simple python program used for counting the number of lines of code in a project. It prints a table distribution of the lines/bytes for each recognized language in the project.

[![GitHub Link](https://img.shields.io/badge/Github-LOC-blue.svg?style=for-the-badge)](https://github.com/Nedra1998/loc) ![](https://img.shields.io/github/repo-size/Nedra1998/loc.svg?style=for-the-badge)

<!-- more -->

The program quickly scans all the files in a directory, and if the flag ``-r`` is set then it does so recursively. If the ``--git`` flag is set, then all files that are in the ``.gitignore`` file will be removed from the count. Then every file type is determined. This is done primarily through file extension, then it attempts at read a shebang to determine the file type.

Using the files types it reads through each file, keeping track of the lines of code, and the lines of comments, and it ignores the blank lines. Finally it displays a table of the acquired data, and a bar graph representing the percentages that each language represents in the project.

Currently there is support for 42 different languages.

|           |              |             |        |                  |
| ---       | ---          | ---         | ---    | ---              |
| Ada       | CoffeeScript | J           | Perl   | Text             |
| AsciiDoc  | Common Lisp  | JSON        | Python | TypeScript       |
| Assembly  | Cuda         | Java        | R      | VimScript        |
| Bash      | D            | JavaScript  | Ruby   | Web Assembly     |
| Brainfuck | Diff         | LLVM        | Rust   | YAML             |
| C         | E            | Less        | SQL    | Zsh              |
| C#        | Emacs Lisp   | Lex         | SVG    | reStructuredText |
| C++       | F#           | Lua         | Sage   |                  |
| CMake     | Fish         | M           | Sass   |                  |
| COBOL     | Fortran      | Makefile    | Scala  |                  |
| CSS       | GLSL         | Markdown    | Shell  |                  |
| CSV       | Go           | Objective-C | Swift  |                  |
| Clojure   | HTML         | OpenCL      | TeX    |                  |
