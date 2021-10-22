# Syntax

Comments are marked by #, any characters to the right will be ignored

```
x += 2 # this is a comment
```

End-of-Line terminates a statement (no semicolon needed)

```
midpoint = 5
endpoint = 9
```

Semicolon can separate statements on a single line

```
midpoint = 5; endpoint = 9
```

Backslash links multiple lines if needed

```
x = 1 + 2 + 3 + 4 +\
    5 + 6 + 7 + 8
```

Indentation and Whitespace **before** lines matters. Code blocks are denoted by indentation, and are preceded by a colon (:)

```
for i in range(10):
    if i < midpoint:
        lower.append(i)
    else:
        upper.append(i)
```

Whitespace **within** lines does not matter.

```
x=1+2
x = 1 + 2
# these are identical
```
