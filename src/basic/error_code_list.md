# Error code list

In the PC Sharp 1500 system, error codes are essential for identifying and resolving issues during program execution. The system has 80 possible error codes, each with a specific meaning. Below is a detailed explanation of each error, along with suggestions for troubleshooting.

# PROBABLY NOT CORRECT, JUST USED FOR THE STRUCTURE, TODO: FIX THE ERROR EXPLANATIONS!

### Error Code 1
**Description**: End of program reached with GOSUB before encountering a RETURN.  
**Display**: `ERROR 1`

### Error Code 2
**Description**: END statement encountered during program execution.  
**Display**: `ERROR 2`

### Error Code 3
**Description**: RETURN without GOSUB in the program flow.  
**Display**: `ERROR 3`

### Error Code 4
**Description**: NEXT without a corresponding FOR loop.  
**Display**: `ERROR 4`

### Error Code 5
**Description**: FOR statement does not exist for the NEXT statement.  
**Display**: `ERROR 5`

### Error Code 6
**Description**: FOR statement references a variable incorrectly.  
**Example**: `FOR A = 1 TO 10 STEP 0`  
**Display**: `ERROR 6`

### Error Code 7
**Description**: Branching error when a line number does not exist in GOTO or GOSUB statements.  
**Display**: `ERROR 7`

### Error Code 8
**Description**: GOTO or GOSUB instruction references a line number that is outside of program range.  
**Display**: `ERROR 8`

### Error Code 9
**Description**: Program terminates because an undefined line number is encountered.  
**Display**: `ERROR 9`

### Error Code 10
**Description**: DIM or array index is out of bounds.  
**Example**: `A(11)` when the array `A` was declared with only 10 elements.  
**Display**: `ERROR 10`

### Error Code 11
**Description**: String variable overflow.  
**Display**: `ERROR 11`

### Error Code 12
**Description**: REDIM command attempted on an array that has already been defined.  
**Display**: `ERROR 12`

### Error Code 13
**Description**: Unmatched parentheses in an expression.  
**Example**: `PRINT (A + B`  
**Display**: `ERROR 13`

### Error Code 14
**Description**: Quotation marks in string expression are unmatched.  
**Example**: `PRINT "Hello`  
**Display**: `ERROR 14`

### Error Code 15
**Description**: Arithmetic overflow or underflow in numeric calculations.  
**Display**: `ERROR 15`

### Error Code 16
**Description**: Expression does not match the required data type (for example, trying to perform arithmetic on a string).  
**Example**: `PRINT A + "HELLO"`  
**Display**: `ERROR 16`

### Error Code 17
**Description**: Data type (numerals, character strings) is inappropriate for the calculation expression.  
**Example**: `1 + "A"`  
**Display**: `ERROR 17`

### Error Code 18
**Description**: Number of arguments inappropriate for expression.  
**Example**: `LEFT$("ABC")`, `SIN(30, 60)`  
**Display**: `ERROR 18`

### Error Code 19
**Description**: Specified numeric value is outside the permitted range.  
**Example**: `DIM A(256)`  
**Display**: `ERROR 19 IN 10`

### Error Code 20
**Description**: No '@' following when fixed memory array variables are specified.  
**Example**: `@$ = "A"`  
**Display**: `ERROR 20 IN 100`

### Error Code 21
**Description**: A variable is required in the expression.  
**Example**: `FOR 1 = 0 TO 10`  
**Display**: `ERROR 21 IN 10`

### Error Code 22
**Description**: No memory space available for loading the program.  
**Display**: `ERROR 22`

### Error Code 23
**Description**: Time is set incorrectly.  
**Example**: `TIME = 131005.10`  
**Display**: `ERROR 23`

### Error Code 26
**Description**: Command cannot be executed in the current mode.  
**Example**: `<RUN MODE> NEW`  
**Display**: `ERROR 26`

### Error Code 27
**Description**: Optional printer is not connected and there is no program that corresponds to the given label.  
**Display**: `ERROR 27`

### Error Code 28
**Description**: Command or function code has been inserted inside quotes or when INPUT or READ commands are used incorrectly.  
**Example**: `INPUT A$`  
**Display**: `ERROR 28`

### Error Code 30
**Description**: Line number exceeds 65539.  
**Example**: `A = 10`  
**Display**: `ERROR 30`

### Error Code 32
**Description**: Graphic cursor between columns 152-155 during execution of input commands (input code cannot be displayed).  
**Display**: `ERROR 32`

### Error Code 36
**Description**: Data or characters cannot be displayed in accordance with the format specified by USING commands.  
**Example**: `USING "::: ; ; : "`  
**Display**: `ERROR 36`

### Error Code 37
**Description**: Numeric calculations result in overflow beyond the range `9.999999999 E99`.  
**Display**: `ERROR 37`

### Error Code 38
**Description**: Division by zero.  
**Example**: `PRINT 5/0`  
**Display**: `ERROR 38`

### Error Code 39
**Description**: Illogical calculation has been made. This includes:
- Negative number logarithmic calculation
- ASN or ACS where `X = 1`
- Square root of a negative number  
**Display**: `ERROR 39`

## Cassette Related Errors

### Error Code 40
**Description**: Inappropriate specification for the expression.  
**Display**: `ERROR 40`

### Error Code 41
**Description**: SAVE and LOAD have been specified for the ROM area.  
**Display**: `ERROR 41`

### Error Code 42
**Description**: The cassette file data is too large to load.  
**Display**: `ERROR 42`

### Error Code 43
**Description**: CLOAD? command detects mismatch between file format and the one on tape.  
**Display**: `ERROR 43`

### Error Code 44
**Description**: Checksum error during cassette data verification.  
**Display**: `ERROR 44`

## Printer Related Errors

### Error Code 70
**Description**: Pen has exceeded coordinate range `-2048 <= X, Y <= 2047`.  
**Display**: `ERROR 70`

### Error Code 71
**Description**: Paper has backed up more than 10.24 cm in TEXT mode or will do so if commands are continued.  
**Display**: `ERROR 71`

### Error Code 72
**Description**: Inappropriate value specified for TAB command.  
**Display**: `ERROR 72`

### Error Code 73
**Description**: Command used in the wrong printer mode (GRAPH/TEXT).  
**Display**: `ERROR 73`

### Error Code 74
**Description**: Too many commas in LINE or RUNE command (over seven commas).  
**Display**: `ERROR 74`

### Error Code 76
**Description**: For LPRINT, when the printing of calculation results cannot be done on one line (in TEXT mode).  
**Display**: `ERROR 76`

### Error Code 78
**Description**: Two possible reasons:
1. Pens are in the process of being changed.
2. The LOW BATTERY state has not been corrected.  
**Display**: `ERROR 78`

### Error Code 79
**Description**: The color signal has not been activated.  
**Display**: `ERROR 79`

### Error Code 80
**Description**: Low Battery condition.  
**Display**: `ERROR 80`

## Conclusion

These 80 error codes are designed to help developers identify problems in their code and understand what went wrong during execution. By following the troubleshooting tips provided for each error, you can efficiently debug and resolve issues in your programs for the PC Sharp 1500 system.
