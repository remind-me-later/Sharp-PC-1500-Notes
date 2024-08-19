# The BASIC programming language

Writing single line programs is kind of limited, so let's see how to write
programs with multiple lines.

To write our program we first need to enter the `programming` mode, to do this
simply press the `mode` key until the `PRO` indicator is displayed above the
screen. This modes gives us a "text editor" like interface that will make
writing long programs easier.

TODO: add graphics

Now the computer is ready to accept our program, lets start with the classical
`Hello, World!` program. The program is introduced line by line, so first we
introduce the following input.

```basic
10 PRINT "HELLO, WORLD!"
```

When you are done introducing the line, press the `enter` key to accept it. The
first number in the line is the line number, it is used to reference the line in
the program, and is mandatory. After the line number we have the statement, in
this case `PRINT`, which prints the string that follows it, in this case
`"HELLO, WORLD!"`.

Now we can run the program, to do this, press the `MODE` key until the `RUN`
prompt is displayed above the screen. Then press enter the following command.

```basic
RUN
```

The program will run and display the `HELLO, WORLD!` message on the screen.

Let's add a second line to our program, to do this return to the `PRO` mode and
write:

```basic
20 PRINT "GOODBYE, WORLD!"
```

Running the program again will show the two lines, one after another. Let's say
we want to output something between the two lines, we can simply add a new line
in `PRO` mode, between the two existing lines.

```basic
15 PRINT "I'M A COMPUTOR!"
```

Running wil yield the expected output, but oops we made a typo, to fix it we can
go again into `PRO` mode and use the list command

```basic
LIST 15
```

This will let us edit the line, and fix the typo, to do this point the cursor to
the incorrect character by using the `left` and `right` keys, then simply press
the character you want to replace it with, in this case `E`.

```basic
15 PRINT "I'M A COMPUTER!"
```
