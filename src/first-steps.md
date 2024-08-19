# First steps

When you first start the calculator, which can be done by pressing the `ON` button, you will be greeted by a prompt.
Notice also that above the screen a `RUN` prompt is displayed. This means that the calculator is in `RUN` mode, what this means will be explained later, but for now we will always want to be in `RUN` mode. If you are not in `RUN` mode, you can switch to it by pressing the `MODE` key until the `RUN` prompt is displayed.

Introducing something like

```basic
2+2
```

and pressing enter will give you the expected result:

```basic
4
```

To discard the result simply press the red `CL`, shorthand for `clear`, button at the right of the calculator.
Now, with a fresh screen, you could even write something like:

```basic
2+2*2
```

obtaining

```basic
6
```

And any other expression you could expect of a calculator. But the real power of the PC-1500 is that it
can run any `BASIC` program. Introducing, for example:

```basic
PRINT "Hello, World!"
```

<div class="note">
The spaces are optional, they make the program more readable, but could slow you down when typing.
</div>

will produce the expected output:

```basic
Hello, World!
```

We can also assign values to variables and print them:

```basic
A=20
PRINT A
```

will output

```basic
20
```

In this fashion we can only execute one line of program at a time, in the following chapters we will see how to write multi-line programs.
