# Input and Output

FunctionDescription`format()`Converts a value to a formatted representation`input()`Reads input from the console`open()`Opens a file and returns a file object`print()`Prints to a text stream or the console

`print`(_\\_objects_, _sep=' '_, _end='\n'_, _file=sys.stdout_, _flush=False\*)

Print _objects_ to the text stream _file_, separated by _sep_ and followed by _end_. _sep_, _end_, _file_ and _flush_, if present, must be given as keyword arguments.

```
> print(*range(10), sep='')

0123456789
```
