# Flexible Arbitrary Arguments  Unpacking

Good Guide: [https://realpython.com/python-kwargs-and-args/](https://realpython.com/python-kwargs-and-args/)

Doc: [https://docs.python.org/3/tutorial/controlflow.html#arbitrary-argument-lists](https://docs.python.org/3/tutorial/controlflow.html#arbitrary-argument-lists)

**\*args **and **\*\*kwargs **allow you to pass multiple arguments or keyword arguments to a function.

Instead of passing a list in this example, you’re passing three different positional arguments. my\_sum() takes all the parameters that are provided in the input and packs them all into a single iterable object named args:

```
def my_sum(*args):
    result = 0
    for x in args:
        result += x
    return result

print(my_sum(1, 2, 3))
```

All that matters here is that you use the unpacking operators (\* or \*\*). The names args and kwargs can be anything.

\*\*kwargs works just like \*args, but instead of accepting positional arguments it accepts keyword (or named) arguments

```
def concatenate(**kwargs):
    result = ""
    for arg in kwargs.values():
        result += arg
    return result

print(concatenate(a="Real", b="Python", c="Is", d="Great", e="!"))

RealPythonIsGreat!
```

**Ordering Arguments in a Function**

If you’re passing a combination of standard arguments, \*args and \*\*kwards, the order matters:

1. Standard
2. \*args
3. \*\*kwargs

**Unpacking Operators \* and \*\***

Unpacking operators are operators that unpack the values from iterable objects in Python. The single asterisk operator \* can be used on any iterable that Python provides, while the double asterisk operator \*\* can only be used on dictionaries.

**Cool Stuff**

print() is a function, so you can unpack arguments to it.

```
mylist = [1,2,3,4,5]

print(*mylist) # unpacks and prints in sequence
1 2 3 4 5

print(*mylist, sep='-') # fun stuff
1-2-3-4-5
```

You can unpack a string into a list, this has to be the easiest way possible! NOTE the square brackets being used:

```
[*'mystring']
['m', 'y', 's', 't', 'r', 'i', 'n', 'g']

'-'.join([*'mystring'])
'm-y-s-t-r-i-n-g'

mystr = 'abracadabra'
[*mystr]  # even simpler than a list comprehension!
['a', 'b', 'r', 'a', 'c', 'a', 'd', 'a', 'b', 'r', 'a']
```

**Parsing Input**
