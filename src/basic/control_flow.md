# Control flow

## `IF` and ## `THEN`

The `IF` statement in BASIC provides conditional execution of code based on the result of a logical test. It enables decision-making within a program by evaluating conditions and determining which actions to perform.

The `THEN` keyword in BASIC is a component of the `IF` statement, used to specify the action or instruction to execute when a condition evaluates to **True**. It defines the response to the logical test performed by the `IF` statement.

```basic
     IF condition THEN statement
```

### Logical Flow

- If the **condition** evaluates to **True**, the statement following the `THEN` keyword is executed.

- If the **condition** evaluates to **False**, the statement is skipped, and program execution continues with the next line.

### Types of Statements

The statement after `THEN` can be any valid BASIC command, including:

- A `PRINT` statement to display information.

- An **assignment** using `LET` (**required** for assignments in this context).

- A `GOTO` statement for branching to another line (using a **number-line** also works).

### Key Notes

-  In BASIC, any expression evaluating to a **non-zero** value is considered **True**. A **zero** value is considered **False**.

-  If the statement following `THEN` is an assignment, the `LET` keyword must be included.

## `ELSE`

## `GOTO`

The `GOTO` statement in BASIC alters the normal sequential flow of a program by jumping to a specified line. It allows for flexible execution paths, skipping or repeating sections of code as necessary.

The `GOTO` instruction is a **command** as well as a **statement**. 

Issued as a **statement**, `GOTO` tells SHARP to "go to" a line other than the next one and begin executing statements sequentially from there.

```basic
    GOTO expression
```
where:

**expression** evaluates to a number which is a valid program line-number (**1 through 65279**).

Issued as a **command**, in the RUN mode, `GOTO` begins program execution in a manner similar to the `RUN` command. However,  unlike the `RUN` command the `GOTO` command will **not clear values** from any variables before it begins execution of lhe program.

To begin program execution with the `GOTO` command `ENTER`:

```basic
    GOTO line_number
```
where:

**line_number** is the number of the first line of the program to be executed.

**NOTE**: Specifying a line number which does not exist will result in an `ERROR 11`.

### Possible usages

- As a jump instruction inside of an `IF` statement

- To create **loops** manually

- As a command `RUN` substitute to start a program in `RUN` mode

## `GOSUB`

The `GOSUB` statement is a special type of `GOTO` statement used to call a subroutine, which is a reusable block of code within a program. Subroutines help avoid duplication of code and allow for modular program design.

It has the same syntax as the `GOTO` statement with the only difference being that before jumping, the program "remembers" the location of the `GOSUB` statement so it can return to it after reaching the `RETURN` statement.

When the `RETURN` statement is encountered in the subroutine, the program resumes execution at the line following the original `GOSUB` statement.

## `FOR` and `NEXT`

The `FOR` and `NEXT` statements in BASIC provide a structured mechanism for repeating a sequence of instructions, forming a loop. They are particularly useful for iterative tasks, where a counter variable controls the number of repetitions.

Utilizes a counter variable with defined start, end, and step values to determine the loop's behavior.

```basic
FOR counter-variable = initial-value TO final-value [STEP increment-value]
    [statements to repeat]
NEXT counter-variable
```


## `RETURN`

The `RETURN` statement is used to indicate the end of a subroutine in BASIC. It ensures the program resumes execution at the point immediately following the corresponding `GOSUB` statement.

Every `GOSUB` needs to have its own `RETURN` statement.

## `REPEAT`