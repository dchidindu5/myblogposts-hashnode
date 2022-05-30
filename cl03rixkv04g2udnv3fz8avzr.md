## The Anatomy of a C++ Program


I could remember vividly some years ago when I started learning programming I really found it difficult to understand the structure and precedence behind programs but as time went by, I solidly gained my ground through thorough practice and mentorships.

This article is aimed at helping newbies who want to make C++ or any other programming language their career path.
The following paradigm helps all to see and understand the structural behavior of any C++ program.

## Preprocessor

Each time you run your compiler, the preprocessor `#include <iostream>` runs first. It reads through your source code and includes the files you’ve asked for, and performs other housekeeping chores. The compiler then runs to convert your preprocessed source code to object code.

## Functions
Main function - `main()` is special because it is called automatically each time your program is executed. It might not be called by any other function and it must exist in every program.

## Defining Variables

In C++, a variable is a location in your computer’s memory in which you can store a value and from which you can later retrieve that value. example `int sum = 20 , double B = 10.5`
Notice that variables are used for temporary storage. When you exit a program or turn
the computer off, the information in variables is lost. Permanent storage is a different matter. Typically, the values from variables are permanently stored either to a database or to a file on disk.
Some words are reserved by C++, and you cannot use them as variable names. These
keywords have special meaning to the C++ compiler. Keywords include if, while, for,
and main.

## Comments
C++-style, single-line comments are started with two slashes (//) and they comment out any text until the end of the line. Multiline, or C-style, comments are
identified with marker pairs (/* */), and everything between the matching pairs is
commented out. You must be careful to ensure that you have matched pairs.

 C++-style, single-line comments can be nested within multiline, C-style comments:
/* This marker starts a comment. Everything including
// this single line comment,
is ignored as a comment until the end marker */
You can, in fact, nest slash-star style comments within double-slash, C++-style
comments as long as you remember that the C++-style comments end at the end of
the line.

Multiline, C-style comments can be longer than one line. If you want to extend
C++-style, single-line comments to a second line, you must put another set of double slashes (//).

## Body
The body of a function in the C++ program, refers to the operations that are performed in the functions. It can be anything like manipulations, searching, sorting, printing, etc. It also comprises of all mentioned above.

As you venture into C++, consistency and patience is key in developing your career.
