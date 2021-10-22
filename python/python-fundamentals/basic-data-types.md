# Basic Data Types

**INTEGER**

Any number without a decimal point is an integer:** **

```
x = 1

type(x)
int
```

Although Python 2.x had both an `int` and `long` type, Python 3 combines the behavior of these two into a single `int` type.

**FLOAT**

The float type in Python designates a floating-point number. float values are specified with a decimal point. Optionally, the character e or E followed by a positive or negative integer may be appended to specify scientific notation.

```
>>> 4.2
4.2

>>> .4e7
4000000.0

>>> type(.4e7)
<class 'float'>

>>> 4.2e-4
0.00042
```

In Python 3, integers will up-cast to Floats in division:

```
>>> 5 / 2
2.5
```

**COMPLEX**

Complex numbers are specified as \\+\j

```
>>> 2+3j
(2+3j)
>>> type(2+3j)
<class 'complex'>
```

**STR**

String literals may be delimited using either single or double quotes. All the characters between the opening delimiter and matching closing delimiter are part of the string. It can also be empty.

```
>>> print("I am a string.")
I am a string.

>>> type("I am a string.")
<class 'str'>
```

If you want to include either type of quote character within the string, the simplest way is to delimit the string with the other type. If a string is to contain a single quote, delimit it with double quotes and vice versa. Or use the backslash to suppress the special character. Other special characters include:

\n linefeed

\t tab

\uxxxx Unicode character with 16-bit hex value

**Raw String** literals are preceded by an r or R, specifiying that escape sequences in the string will not be translated.

```
>>> print('foo\\bar')
foo\bar

>>> print(R'foo\\bar')
foo\\bar
```

**Triple Quoted** Strings allow for multiline srings, and escape sequences will also work:

```
>>> print("""This is a
string that spans
across several lines""")
This is a
string that spans
across several lines
```

**BOOLEAN**

Objects of Boolean type may have one of two values, True or False:

```
>>> type(True)
<class 'bool’>

>>> type(False)
<class 'bool'>
```
