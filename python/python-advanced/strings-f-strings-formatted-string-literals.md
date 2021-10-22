# Strings  F-Strings (Formatted String Literals)

[https://docs.python.org/3/reference/lexical\_analysis.html#formatted-string-literals](https://docs.python.org/3/reference/lexical\_analysis.html#formatted-string-literals)

F-strings provide a concise and convenient way to embed python expressions inside string literals for formatting.

To create an f-string, prefix the string with the letter “ f ”. The string itself can be formatted in much the same way that you would with str.format().

```
name = 'Tushar'
age = 23

> print(f"Hello, My name is {name} and I'm {age} years old.") 
# Hello, My name is Tushar and I'm 23 years old.


round(result,2) = 28.0   # let's say we want two decimal places.

> print(f'{result:.2f}')
28.00
```
