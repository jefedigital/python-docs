# Definitions

**ASSERT**

The assert statement exists in almost every programming language. When you do...

assert condition

... you're telling the program to test that condition, and trigger an error if the condition is false.

In Python, it's roughly equivalent to this:

if not condition:

raise AssertionError()

Try it in the Python shell:

\>>> assert True # nothing happens

\>>> assert False

Traceback (most recent call last):

File "\\", line 1, in \\

AssertionError
