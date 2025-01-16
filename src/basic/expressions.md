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

We'll focus on the first for now. In the `RUN` mode the computer is in a REPL, each expression introduced is immediately evaluated and the result is displayed on the screen. In `PRO` mode, this is not the case, all expression must be used alongside a statement, such as an assignment or a print statement.

```basic
10 A = 10 + (2 * 8)
20 PRINT A + 25
```

## Variable types

In SHARP, there are mainly two types of variables, which correspond to the possible content that can be stored in them: a numeric value or a string of characters. The type of variable can be easily distinguished because character variables need to have their name end with a dollar sign '$', while numeric variables do not. The '$' alerts SHARP to the fact that the variable holds character information. Beyond this distinction, both types function in an analogous manner. 

In the specific case of arrays, as in any other programming language, their behavior is entirely predictable, and they are simply a set of variables of one of the two previously mentioned types. As a clarification, it is important to know that an array-variable X and a variable X are separate and distinct to SHARP

```basic
10 A = 10 + (2 * 8)
20 B$ = "HELLO WORLD"
```

## Uninitialized variables

It is important to know that each possible variable name that is not reserved by SHARP is initialized automatically to 0 if it is numeric and to an empty string if it is a character type variable.

Once initialized information within variables is retained until:
1) A CLEAR or NEW commad is given.
2) A program is run using the RUN command.
3) Another Assignment statement is executed for the same variable.
4) The computer's batteries are changed.
Turning the computer off does not affect values stored in variables.

## Reserved variable names

Due to conflicts with abbreviations which have other meanings in the BASIC language, SHARP does not allow the use of some variable names such as: LF, IF, LN, PI, TD, LFS, IFS, LNS, PIS, TO$.

## Operators

There are four arithmetic operators: `+`, `-`, `*`, `/`. The precedence of the operators is the usual. 

The `+` and `-` can also be used in their unary form with a high precedence. 

There are also the usual comparison operators `<`, `<=`, `=`, `>=`, `>`, `<>`, which seem to have all the same precedence, that being the second lowest.

There are also boolean bitwise functions `AND`, `OR` and `NOT`, which seem to have all the same precedence, that is the lowest.

## Precedence

Calculations are performed in accordance with the following hierarchy; expressions in parentheses having the highest priority and logical operations having the lowest. If two or more
operations of the same priority are found in the same expression or sub-expression, they are
evaluated from left to right.

- 1. Expressions in Parenthesis
- 2. Retrieval or values from variables
- 3. Functions 
- 4. Exponentiation
- 5. Arithmetic Sign (+ , -)
- 6. Multiplication, Division (* , /)
- 7. Addition, Subtraction (+ , -)
- 8. Comparison Operators (<, <=, =, >= , >, <>)
- 9. Logical Operators (AND, OR, NOT)