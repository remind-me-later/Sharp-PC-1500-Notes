# Grammar

The grammar has been extracted from sources as much as possible, but a big chunk
of it has been reverse engineered from the calculator's behavior. Checked with
[BNF Visualizer](https://bnfplayground.pauliankline.com/).

```ebnf
/* --- Tokens --- */
<digit> ::= [0-9]
<number> ::= <digit>+
<letter> ::= [A-Z]
<identifier> ::= <letter> (<letter> | <digit>)*
<comparison_op> ::= "=" | "<>" | "<" | ">" | "<=" | ">="
<add_sub_op> ::= "+" | "-"
<mul_div_op> ::= "*" | "/"
<char> ::= [A-Z] | [a-z] | [0-9]
    | " " | "!" | "\"" | "#" | "$" | "%" | "&" | "'" | "(" | ")"
    | "*" | "+" | "," | "-" | "." | "/" | ":" | ";" | "<" | "="
    | ">" | "?" | "@" | "[" | "\\" | "]" | "^" | "_" | "`"
    | "{" | "|" | "}" | "~"
<string> ::= "\"" <char>* "\"" | "\"" <char>*
<newline> ::= "\n"

/* functions */
<and> ::= "AND"
<or> ::= "OR"
<not> ::= "NOT"

/* --- Grammar --- */
<program> ::= <line>+
<line> ::= <number> <stmt> <newline>

/* stmts */
<stmt> ::= <atomic_stmt> (":" <atomic_stmt>)*
<atomic_stmt> ::= <assignment>
    | <print>
    | <pause>
    | <input>
    | <wait>
    | <cursor>
    | <gcursor>
    | <gprint>
    | <if>
    | <for>
    | <next>
    | <goto>
    | <gosub>
    | <return>
    | <end>
    | <comment>
    | <data>
    | <read>
    | <restore>
    | <poke>
    | <call>
    | <dim>

/* Comments */
<comment> ::= "REM" <char>*

/* Variables */
<variable> ::= <identifier> "$"?
<array_subscript> ::= <variable> "(" <expr> ("," <expr> )? ")"
<lvalue> ::= <variable> | <array_subscript>
<assignment> ::= "LET"? <lvalue> "=" <expr>

/* I/O */
<print> ::= "PRINT" <expr> (";" <expr>)*
<pause> ::= "PAUSE" <expr> (";" <expr>)*
<input> ::= "INPUT" (<expr> ";")? <lvalue>
<wait> ::= "WAIT" <expr>?
<cursor> ::= "CURSOR" <expr>
<gcursor> ::= "GCURSOR" <expr>
<gprint> ::= "GPRINT" <expr> (";" <expr>)* | "GPRINT" <string>

/* Data */
<data_item> ::= <number> | <string>
<data> ::= "DATA" <data_item> ("," <data_item>)*
<read> ::= "READ" <lvalue> ("," <lvalue>)*
<restore> ::= "RESTORE" (<number>)?

/* Control flow */
<if> ::= "IF" <expr> "THEN" <stmt> ("ELSE" <stmt>)?
<for> ::= "FOR" <variable> "=" <expr> "TO" <expr> ("STEP" <expr>)?
<next> ::= "NEXT" <variable>
<goto> ::= "GOTO" <number>
<gosub> ::= "GOSUB" <number>
<return> ::= "RETURN"
<end> ::= "END"

/* Assembly */
<poke> ::= "POKE" <number>, (<number>)+
<call> ::= "CALL" <number>

/* Arrays */
<dim> ::= "DIM" <variable> "(" <number> ("," <expr> )? ")" ("*" <number>)?

/* exprs */
<expr> ::= <comparison>
<comparison> ::= <add_sub> (<comparison_op> <add_sub>)*
<add_sub> ::= <mul_div> (<add_sub_op> <mul_div>)*
<mul_div> ::= <factor> (<mul_div_op> <factor>)*
<factor> ::= "-" <factor> | "+" <factor> | <term>
<term> ::= <number> | <lvalue> | <string> | "(" <expr> ")"
```
