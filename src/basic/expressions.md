# Expressions

Let's dive deeper into the syntax of BASIC. As we've seen before a program in
BASIC consists of a list of lines, each line begins with a **line number**,
followed by a **statement**.

The line number uniquely identifies each line, the lines of the program are
executed in order according to the line number. And are also used as labels for
branch statements, which we'll see later.

The statement after the line number tells the computer what to do, we've seen
some examples, like the assignment statement:

```basic
10 LET A = 10
```

or simply

```basic
10 A = 10
```

And the print statement:

```basic
20 PRINT A
```

We'll focus on the first for now. In the `RUN` mode the computer is in a REPL,
each expression introduced is immediately evaluated and the result is displayed
on the screen. In `PRO` mode, this is not the case, all expression must be used
alongside a statement, such as an assignment or a print statement.

```basic
10 A = 10 + (2 * 8)
20 PRINT A + 25
```

## Operators

There are four arithmetic operators: `+`, `-`, `*`, `/`. The precedence of the
operators is the usual. The `+` and `-` can also be used in their unary form,
There are also boolean bitwise functions `AND`, `OR` and `NOT`, which seem to
have all the same precedence, that is the lowest.
