# Basic IO

## Key Information

Basic information about SHARP's display, there's only space available for 26 characters, If the length of the information displayed exceeds that number the items at the end of the print list will not be seen.

## `PRINT`

It is the main statement to produce output, it has several different variations.

The general format of the `PRINT` statement is the word `PRINT` followed by an item or a list of items to be printed. These
include character strings, expressions, or names of variables whose values will be printed.

### Statement Overview

- **";"**: Inserts a natural cadence, which results in one space between arguments.

- **","**: Creates a tab jump, equivalent to 8 spaces, between arguments. Strings are left-aligned or "left justified", while numbers are right-aligned or "right justified".

- **Argument Calculations**: The `PRINT` statement can perform calculations on arguments and display the result.

- **Comma Limit**: Using a comma `,` in the `PRINT` statement restricts the number of arguments to a maximum of two.

```basic
    10 BS = " BE "
    20 T = 2
    30 PRINT T; BS; " OR NOT"; 12/3 - 2; BS
```

## `PAUSE`

It is a semi-automatic form of the `PRINT` statement, with the difference that the output remains on the display for a fixed and brief period of time. Basically a `PRINT` statement followed by a countdown. When the countdown completes, the program automatically continues to the next statement.

All of the various techniques for the `PRINT` statement are also applicable here. These 2 statements can be mixed at will. It seems like it can only be used in "Programmer mode".

```basic
     10 PAUSE "DO";
     20 PAUSE "RE";
     30 PAUSE "MI";
     40 PAUSE "FA";
     50 PAUSE "SOL";
     60 PAUSE "LA";
     70 PAUSE "SI";
     80 PAUSE "DO"
```

## `INPUT`

The `INPUT` statement in BASIC is used to gather user-provided data during program execution. It allows programmers to prompt users for specific information and store their responses in variables.

### Different Usages:

- **Basic Syntax**: The simplest form of the INPUT statement is

     ```basic
     INPUT variable-name
     ```
     
    When executed, it displays a `?` on the screen, signaling the user to enter data. 

- **Prompting the User**: To make the prompt more informative, the INPUT statement can include a custom message using a character string 

     ```basic
     INPUT "prompt message"; variable-name
     ```
    This form displays the specified prompt followed by a blinking cursor on the same line, where the user can enter their input.

- **Advanced Prompting**: A variation of the prompt uses a **comma** instead of a **semicolon**:  

     ```basic
     INPUT "prompt message", variable-name
     ```

     This version clears the prompt message once the user starts typing their response, replacing it with the input.

### Key Notes

- The expected type of data (numeric or character) must match the variable type.

- The INPUT statement can gather multiple data items at once by specifying a list of variables separated by commas:  

     ```basic
     INPUT var1, var2, var3
     ```  

## `WAIT`

The `WAIT` statement in BASIC allows the programmer to control how long information displayed by the `PRINT` statement stays on the screen. It modifies the operation of the `PRINT` statement, allowing the displayed information to remain visible for a specified period of time.


- The `argument` is optional. If no argument is provided, the default behavior is **"infinite"**, meaning the information will remain on the screen until the user presses the **Enter** key. This is the default mode in many programs.

- If an argument is provided, all subsequent `PRINT` statements will hold their information on the screen for a time period proportional to the specified argument. This is similar to the `PAUSE` statement, but unlike `PAUSE`, the `WAIT` statement's time period is variable.

### Argument Values
- The argument value must be between **0** and **65535**.
  - **WAIT 0** causes the information to be displayed so quickly that it is unreadable.
  - **WAIT 65535** causes the information to stay on the screen for about **17 minutes**.
  - **WAIT 64** results in a display time of about **1 second**.
  - **WAIT 3840** gives a display time of about **1 minute**.

To reset the `PRINT` statement back to its default behavior (waiting for the user to press Enter), simply use `WAIT` with no argument.

```basic
      WAIT argument (64)
```

### Key Notes:

- The `WAIT` statement has no effect on the `PAUSE` statement.

- The time specified by the `WAIT` statement can be adjusted for more precise control over the display duration.

## `READ`

The `READ` statement in BASIC serves as a mechanism to retrieve data from `DATA` statements and assign it to specified variables.
Each variable in the `READ` statement is assigned the next available data item from the list.

The `READ` statement consists of the keyword `READ`, followed by a comma-separated list of variable names. These variables can be either numeric or character types.

### Key Notes:

- **Execution Requirements**: For every execution of a `READ` statement, there must be a corresponding data item within a `DATA` statement. If no data item is available for a variable, the program halts and signals an error.

- **Type Matching**: The data type (numeric or character) of the retrieved item must match the type of the variable to which it is being assigned. A mismatch in type results in an error.

```basic
     120 READ NS, WT , CS, SX$, L
```

## `DATA`

The `DATA` statement allows the programmer to embed data directly within the program. This data can include numbers (in real or scientific notation) and character strings, which are separated by commas.

`DATA` statements may appear anywhere within a program; however, grouping them at the beginning of the program is a widely adopted convention among programmers.

Extra data items not used during the program execution are ignored.

```basic
     10 DATA "MOBY DICK", 20000, " WHITE". " M'', 112
```

## `RESTORE`

The `RESTORE` statement in BASIC is used to reset the data pointer, allowing the program to re-read data items from `DATA` statements.

The `RESTORE` statement enables the re-use of some or all values defined in `DATA` statements. It resets the data pointer to a specified location, allowing subsequent `READ` statements to retrieve previously used data items.

### Different Usages:

- **Default Behavior**: When executed without additional parameters, the RESTORE statement resets the pointer to the first `DATA` statement in the program. Subsequent`READ` statements will then begin reading from the start of the data list.

- **Selective Restoration**: The RESTORE statement can specify a starting point using either a **line number** or a **label**.

```basic
     RESTORE line_number (150)
```
  This causes the program to begin re-reading data items from the `DATA` statement located at the specified line number.  

  Alternatively, a **label** can be assigned to a `DATA` statement, and the RESTORE statement can use this label to target the starting point:  

```basic
     RESTORE label ("X")
```
