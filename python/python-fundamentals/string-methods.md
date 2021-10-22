# String Methods

[https://docs.python.org/3/library/stdtypes.html#string-methods](https://docs.python.org/3/library/stdtypes.html#string-methods)

Here are just a few:

`​`​ function description capitalize() capitalize() function returns the capitalized version of the string. center() returns a centered string of specified size. endswith() returns True if the string ends with the given suffix, otherwise it returns False. find() find() method is used to find the index of a substring in a string. format() create a formatted string from the template string and the supplied values. index() returns the lowest index where the specified substring is found. join() returns a new string that is the concatenation of the strings in iterable with string object as a delimiter. lower() creates a new string in lowercase. partition() splits a string based on a separator into a tuple with three strings. replace() create a new string by replacing some parts of another string. rjust(), ljust() create a new string of specified length from the source string with right and left justification. split() split a string into the list of strings based on a delimiter. splitlines() returns the list of lines in the string. startswith() returns True if the string starts with the given prefix, otherwise it returns False. strip() trim whitespaces from the string object. title() returns a title cased version of the string. upper() convert a string to uppercase in Python using str.upper() function. zfill() returns a new string of specified width. The string is filled with 0 on the left side to create the specified width.

**SPLIT()**

_str.split(sep=None, maxsplit=-1)_

Return a list of the words in the string, using sep as the delimiter string. If maxsplit is given, at most maxsplit splits are done (thus, the list will have at most maxsplit+1 elements)

```
a = "this is a string"

> a.split(' ') # space character
['this', 'is', 'a', 'string']

a.split(' ', maxsplit = 1)
['this', 'is a string']
```

**JOIN()**

_str.join(iterable)_

Return a string which is the concatenation of the strings in iterable. (Feels a little backwards, as we begin with the concatenator.)

```
a = "this is a string"
b = a.split(' ')
['this', 'is', 'a', 'string']

'-'.join(b)
'this-is-a-string'
```

**COUNT()**

_str.count(sub\[, start\[, end]])_

Return the number of non-overlapping occurrences of substring **sub** in the range \[start, end]. Optional arguments start and end are interpreted as in slice notation.

```
```

**FIND()**

_str.find(sub\[, start\[, end]])_

Return the lowest (zero-indexed) index in the string where substring sub is found within the slice s\[start:end]. **If not found, returns -1**

```
a = ‘mystring’

> a.find(‘str’)
2
```

The find() method should be used only if you need to know the position of sub. To check if sub is a substring or not, use the **IN **operator!

**STRING VALIDATORS**

I**SALNUM()**

**ISALPHA()**

**ISDIGIT()**

**ISLOWER()**

**ISUPPER()**

These return Booleans.

```
'ab123'.isalnum()
True

'ab123#'.isalnum()
False

'abcD'.isalpha()
True

'abcd1'.isalpha()
False

'1234'.isdigit()
True

'123edsd'.isdigit()
False

'abcd123#'.islower()
True

'abcd123#'.isupper()
False
```
