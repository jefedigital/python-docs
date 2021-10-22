# Regular Expressions

## PYTHONIC APPROACH

[https://jakevdp.github.io/WhirlwindTourOfPython/14-strings-and-regular-expressions.html](https://jakevdp.github.io/WhirlwindTourOfPython/14-strings-and-regular-expressions.html)

The Python interface to regular expressions is contained in the built-in **re** module.

```
import re
```

## Match Objects

Match objects are returned by the various **re **methods, and always have a boolean value of True. Since match() and search() return None when there is no match, you can test whether there was a match with a simple if statement:

```
match = re.search(pattern, string)
if match:
    process(match)
```

You can query the match object for information about the matching string. Match object instances also have several methods and attributes; the most important ones are

Method/Attribute

Purpose

`group()`

Return the string matched by the RE

`start()`

Return the starting position of the match

`end()`

Return the ending position of the match

`span()`

Return a tuple containing the (start, end) positions of the match

Note that you don’t have to create a pattern object and call its methods; the re module also provides top-level functions called match(), search(), findall(), sub(), and so forth. These functions take the same arguments as the corresponding pattern method with the RE string added as the first argument, and still return either None or a match object instance.

```
print(re.match(pattern, string))
```

## RE METHODS

## re.compile(pattern, flags=0)

This will be the foundation of using regex with Python. This compile a regular expression pattern into a regular expression object, which can be used for matching using its match(), search() and other methods, described below.

```
prog = re.compile(pattern) # produces a regex object
result = prog.match(string) # produces a match object

# the above is equivalent to

result = re.match(pattern, string)
```

It seems overly complex at first, but using **re.compile() **and saving the resulting regular expression object for reuse is more efficient when the expression will be used several times in a single program.

Some available flags include re.ignorecase

```
re.compile('ab*', re.IGNORECASE)
```

Flag

Meaning

`ASCII`, `A`

Makes several escapes like `\\w`, `\\b`, `\\s` and `\\d` match only on ASCII characters with the respective property.

`DOTALL`, `S`

Make `.` match any character, including newlines.

`IGNORECASE`, `I`

Do case-insensitive matches.

`LOCALE`, `L`

Do a locale-aware match.

`MULTILINE`, `M`

Multi-line matching, affecting `^` and `$`.

`VERBOSE`, `X` (for ‘extended’)

Enable verbose REs, which can be organized more cleanly and understandably.

## re.match(pattern, string, flags=0)

Checks if the RE matches at the **beginning** of the string. If the match wouldn’t start at zero, match() will not report it.

Returns None if no match can be found. If successful, a **match object **instance is returned, containing information about the match: where it starts and ends, the substring it matched, and more.

## re.search(pattern, string, flags=0)

Scans forward through the string, reporting the first match it finds.

Sometimes you’ll be tempted to keep using re.match(), and just add .\* to the front of your RE. Resist this temptation and use re.search() instead, it’s faster.

Returns None if no match can be found. If successful, a match object instance is returned, containing information about the match: where it starts and ends, the substring it matched, and more.

## re.split(pattern, string, maxsplit=0, flags=0)

Split string by the occurrences of pattern.

## re.sub(pattern, repl, string, count=0, flags=0)

Return the string obtained by replacing the leftmost non-overlapping occurrences of pattern in string by the replacement repl.

## re.findall(pattern, string, flags=0)

Return all non-overlapping matches of pattern in string, as a list of strings. The string is scanned left-to-right, and matches are returned in the order found. If one or more groups are present in the pattern, return a list of groups.

## re.finditer(patterns, string, flags=0)

Find all substrings where the RE matches, and returns them as an iterator.

## REGEX PATTERNS

**Metacharacters**

* \[] Character Set
* &#x20;Anti-Character Set
* \[a-z] Character Range (A-Z, a-z, 0-9 …)
* () Character Sequence or Group
* ^ at beginning of string (except in anti-character set, above)
* $ at end of string
* . Any character (except newline)

**Some Special Sequences**

* **\d ** Matches any decimal digit; this is equivalent to the class \[0-9].
* **\D ** Matches any non-digit character; this is equivalent to the class .
* **\s ** Matches any whitespace character; this is equivalent to the class \[ \t\n\r\f\v].
* **\S ** Matches any non-whitespace character; this is equivalent to the class .
* **\w** Matches any alphanumeric character; this is equivalent to the class \[a-zA-Z0-9\_].
* **\W ** Matches any non-alphanumeric character; this is equivalent to the class .
* **\t ** Tab
* **\n ** Newline
* **\b** Word boundary
* **\B ** Not a word boundary

**Repetition**

* \* Sequence of zero or more (aka ‘any’)
* ? Sequence of zero or one (aka ’no more than one’)
*
  * Sequence of one or more (aka ‘not zero’)
* {m,n} there must be at least m repetitions, and at most n.

```
re.compile('ca*t') # matches ct, cat, caat, caaaaaaat...

re.compile('ca?t') # matches ct or cat

re.compile('ca+t') # matches cat, caat, caaaaaat...

re.compile('ab{1,3}c') # matches abc, abbc, abbbc (but not ac or abbbbc...)
```

**Grouping**

Groups are marked by the '(', ')' metacharacters and you can repeat the contents of a group with a repeating qualifier, such as \*, +, ?, or {m,n}.

For example, (ab)\* will match zero or more repetitions of ab.

```
p = re.compile('(ab)*')

> print(p.match('ababababab').span())
(0, 10)
```

Groups are numbered starting with 0. Group 0 is always present; it’s the whole RE, so match object methods all have group 0 as their default argument.

Subgroups are numbered from left to right, from 1 upward. Groups can be nested; to determine the number, just count the opening parenthesis characters, going from left to right.

```
p = re.compile('(a(b)c)d')
m = p.match('abcd')

> m.group(0)
'abcd'

> m.group(1)
'abc'

> m.group(2)
'b'
```

group() can be passed multiple group numbers at a time, in which case it will return a tuple containing the corresponding values for those groups.

```
> m.group(2,1,2)
('b', 'abc', 'b')
```

The groups() method returns a tuple containing the strings for all the subgroups

```
> m.groups()
('abc', 'b')
```

**Backreferencing**

Matches the results of a capture group. For example \1 matches the results of the first capture group and \3 matches the third.

Use the **raw string** format when incorporating backreferences, because, you know, problems.

```
re.compile(r'(\w)a\1')  # match repeated alphanumeric character with an 'a' in the middle.

dad # match
dab # no match

gag # match
gig # no match
```

**Named Groups**

Keeping track of multiple groups can get confusing. You can name groups using the **?P\\** format (and remember to enclose it all using the **raw string** format.)

```
re.compile(r'(?P<firstword>\b\w+\b)')
line = 'bird is the word'

result = reg.search(line)

> result.group('firstword')
'bird'
```

**Lookarounds**

Examines the string preceding or following the regex pattern, and returns a result if a desired value is found (or not found!). The lookaround string is not included in the result.

(?=string) positive lookahead for ‘string’

(?!string) negative lookahead for ‘string’

```
re.compile('\d(?=px)'  # find any numeric followed by the string 'px'

1px # match, returns '1'
1em # no match, returns NoneType
```

**Greedy vs Non-Greedy**

When repeating a regular expression, as in a\*, the resulting action is to consume as much of the pattern as possible. This can result in unexpected errors, for example:

```
line = '<html><head><title>Title</title>'

> re.match('<.*>', line).group()
<html><head><title>Title</title>
```

The RE matches the '\\<' in '\\', and the .\* consumes the rest of the string. There’s still more left in the RE, though, and the > can’t match at the end of the string, so the regular expression engine has to backtrack character by character until it finds a match for the >. The final match extends from the '\\<' in '\\' to the '>' in '\\\</title>', which isn’t what you want.

the solution is to use the non-greedy qualifiers \*?, +?, ??, or {m,n}?, which match as little text as possible.

```
> re.match('<.*?>', line).group()
<html>
```

In the above example, the '>' is tried immediately after the first '\\<' matches, and when it fails, the engine advances a character at a time, retrying the '>' at every step.
