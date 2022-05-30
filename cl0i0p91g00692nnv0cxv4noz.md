## Understanding the concept of short-circuit evaluation in C++

Exploring Short-circuiting in C++ makes your code clean and beautiful.
Two situations show why it is important, consider the following:

In the expression `e1 && e2` both subexpressions `e1` and `e2` must be true for the overall expression to be true. Since the && operator evaluates left to right, this means that if `e1` is false, there is no need to evaluate `e2`. 

If `e1` is false, no value of `e2` can make the expression `e1 && e2` true. The logical and operator first tests the expression to its left. If it finds the expression to be false, it does not bother to check the right expression. This approach is called **short-circuit evaluation**.

 In a similar fashion, in the expression `e1 || e2`, if `e1` is true, then it does not matter what value `e2` has—a logical expression is true unless both subexpressions are false.
The `||` operator uses short-circuit evaluation also.

1. The order of the subexpressions can affect performance. When a program is running, complex expressions require more time for the computer to evaluate than simpler expressions. We classify an expression that takes a relatively long time to evaluate as an expensive expression. If a compound Boolean expression is made up of an expensive Boolean subexpression and a less expensive Boolean subexpression, and the order of evaluation of the two expressions does not affect the behavior of the program, then place the more expensive Boolean expression second. If the first subexpression is false and `&&` is being used, then the expensive second subexpression is not evaluated; if the first subexpression is true and `||` is being used, then, again, the expensive second subexpression is avoided.

2. Subexpressions can be ordered to prevent run-time errors. This is especially true when one of the subexpressions depends on the other in some way. Consider the following expression: `(x != 0) && (z/x > 1)`.

Here, if `x` is zero, the division by zero is avoided. If the subexpressions were switched, a run-time error would result if `x` is zero.
>Note: `&&` has precedence over `||`, this means that parentheses are placed to evaluate what would be evaluated together.


