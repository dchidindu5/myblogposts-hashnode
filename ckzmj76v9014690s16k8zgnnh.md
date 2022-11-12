# 3 Programming errors every programmer should know!

Beginners in programming make a lot of mistakes while writing programs because of inexperience in programming or because of unfamiliarity with the programming language. Well seasoned programmers make mistakes due to carelessness or because the proposed solution to a problem is faulty and the correct implementation of an incorrect solution will not produce a correct program.

 Regardless of the reason, programming error falls under one of three categories:
> Note: Dev C++ will be used as IDE.

**Compile-time error**

**Run-time error**

**Logic error.**

 

## Compile-time Errors

A compile-time error occurs as a result of   programmer’s misuse of the language and does not produce a machine-language translation. A syntax error is a common compile-time error.
 For example, in English one can say

*"The boy runs every day"*.

This sentence uses correct syntax. However, the sentence

*"The boy ran every day"*.

It's not correct syntactically: the subject (singular form) disagrees with the verb used because the verb is in past tense and the adverb used contradicts the statement. 
It contains a syntax error. It violates a grammatical rule of the English language.

Similarly, the C++ statement 

`x = y + 4;` 
is syntactically correct because it obeys the rules for the structure of an assignment statement.
However, consider replacing this assignment statement with a slightly modified version: 
`y + 4 = x;`

If a statement like this one appears in a program and the variables x and y have been properly declared, the compiler will issue an error message; for example, the Dev C++ compiler reports (among other things):

 *error C2106: ’=’ : left operand must be l-value*

The syntax of C++ does not allow an expression like `y + 4` to appear on the left side of the assignment operator.
(The term l-value in the error message refers to the left side of the assignment operator; *the l is an “elle,” not a “one.”*)
The compiler may generate an error for a syntactically correct statement like 

`x = y + 4;`

If either of the variables x or y has not been declared; for example, if y has not been declared, Dev C++ reports:

*error C2065: ’y’ : undeclared identifier*

Other common compile-time errors include missing semicolons at the end of statements, mismatched curly brackets and parentheses, and simple typographical errors.
 
Compile-time errors usually are the easiest to repair. The compiler pinpoints the exact location of the problem, and the error does not depend on the circumstances under which the program executes.
Compilers have the reputation for generating cryptic error messages. They seem to provide little help as far as novice programmers are concerned. Sometimes a combination of errors can lead to messages that indicate errors on lines that follow the line that contains the actual error.

## Run-time Errors

The compiler ensures that the structural rules of the C++ language are not violated. It can detect, for example, the malformed statement and the use of a variable before its declaration. Some violations of the language cannot be detected at compile time, however. A program may not run to completion but instead terminate with an error.
Consider the expression 

`dividend/divisor` as used in the program.

Image of the code snippet

![codesnippetforRuntimeError.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1644832634677/hJZK87RGJ.png)


For example If a user enters, `15 and 5`, as the dividend and divisor respectively the program works nicely.


![OutputForRuntime.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1644832672941/3g6O_XoK8.png)
 
and displays the answer of `3`. If the user instead types the numbers 15 and 0, the program reports an error and terminates. Division by zero is undefined in mathematics, and integer division by zero in C++ is illegal.
When the program attempts the division at run time, the system detects the attempt and terminates the program.
This particular program can fail in other ways as well; for example, outside of the C++ world, `15.0` looks like a respectable integer but if the user types in `15.0` and `5`, the program crashes because `15.0` is not a valid way to represent an integer in C++. When the compiler compiles the source line

`std::cin >> dividend >> divisor;`

Given that **dividend** has been declared to be an `int`, it generates slightly different machine language code than it would have if `dividend` has been declared to be a `double` instead. 
The compiled code expects the text entered by the user to be digits with no extra decoration. Any deviation from this expectation results in a run-time error. 
Similar results occur if the user enters text that does not represent an integer, like "Dennis".
Observe that in either case—entry of a valid but inappropriate integer (zero) or entry of a non-integer
(15.0 or Dennis)—it is impossible for the compiler to check for these problems at compile time. The compiler cannot predict what the user will enter when the program is running. This entails that it is up to the programmer to write code that can handle bad input by the users.

## Logic Errors

Consider the effects of interchanging the expression
`dividend / divisor;`

With this `divisor / dividend;`

![logicSnippet.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1644832735758/bQwhu3-mTZ.png)

 
The program compiles with no errors. It runs, unless a value of zero is entered for the dividend, no run-time errors arises. However, the answer it calculates will not be correct. The only time the correct answer is printed is when `dividend = divisor`.

![LogicErrorOutput.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1644832783166/Pol53qdQf.png)

The program contains an error, but neither the compiler nor the run-time system is able detect the problem.
An error of this type is known as a **logic error**.

As the programmer becomes more professional in writing programs, the number of compile-time errors decreases or are trivially fixed and the number of logic errors increases.
Unfortunately, Logical errors tend to be the most difficult to find and repair, but there's always a way out.

The bad news is that since software development in an inherently human intellectual pursuit, logic errors are inevitable. Accidentally introducing and later finding and eliminating logic errors is an integral part of the programming process.

