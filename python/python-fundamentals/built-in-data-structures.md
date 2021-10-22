# Built-In Data Structures

**LIST**

Lists are the basic ordered and mutable data collection type in Python. They can be defined with comma-separated values between square brackets.

```
L = [2, 3, 5, 7]
```

Lists can contain objects of any type, or even a mix of types.

```
L = [1, 'two', 3.14, [0, 3, 5]]
```

Some useful properties and methods:

```
> len(L)
4

> L.append(11)
[2, 3, 5, 7, 11]

> L + [13, 17]
[2, 3, 5, 7, 11, 13, 17]

> M = [2, 5, 1, 6, 3, 4]
M.sort()
[1, 2, 3, 4, 5, 6]
```

**List Indexing and Slicing**

Python uses zero-based indexing, and accepts negative values to index from the end of the list.** **

```
> L[0]
2

> L[1]
3

> L[-1]
19
```

Slicing uses a colon to indicate the start point **(inclusive**) and end point (**non-inclusive**). A third integer can specify **step** size.

```
> L[0:3]
[2, 3, 5]

> L[:3]
[2, 3, 5]

> L[-3:]
[11, 13, 17]

> L[::2]
[2, 5, 11, 17]

> L[::-1]  # clever way to get a reverse sort
[17, 13, 11, 7, 5, 3, 2]
```

Indexing and Slicing can be used to **set** elements as well as access them:

```
L[0] = 'a'
['a', 3, 5, 7, 11, 13, 17]

L[1:3] = ['b','c']
['a', 'b', 'c', 7, 11, 13, 17]
```

**TUPLE**

Tuples are in many ways similar to lists, but they are defined with parentheses rather than square brackets (or no brackets at all)

```
> t = (1, 2, 3)
(1, 2, 3)

>t = 1, 2, 3
(1, 2, 3)

> len(t)
3

> t[1] # slicing and indexing work for looking up values
2
```

The main distinguishing feature of tuples is that they are immutable: this means that once they are created, their size and contents cannot be changed.

```
> t[1] = 5
TypeError: 'tuple' object does not support item assignment

> t.append(4)
AttributeError: 'tuple' object has no attribute 'append'
```

A common use for tuples is for functions that have multiple return values.

For example, the `as_integer_ratio()` method of floating-point objects returns a numerator and a denominator; this dual return value comes in the form of a tuple:

```
> x = 0.125
> x.as_integer_ratio()
(1, 8)
```

These multiple return values can be individually assigned as follows:

```
> numerator, denominator = x.as_integer_ratio()
> print(numerator / denominator)
0.125
```

**DICT**

Dictionaries are extremely flexible mappings of keys to values; format is a comma-separated list of `key:value` pairs within curly braces.

```
> numbers = {'one':1, 'two':2, 'three':3}
```

Item values may be indexed using the name of the key:

```
> numbers['two’]
2
```

New items can be added

```
> numbers[‘four'] = 4
{'one':1, 'two':2, 'three’:3, ‘four’:4}
```

Dictionaries do not maintain any sense of order (by design), allowing them implemented very efficiently, so that random element access is very fast, regardless of the dictionary size.

**Some Dictionary Operations:**

* **list(d) ** Return a list of all the keys used in the dictionary d.
* **len(d)** Return the number of items in the dictionary d.
* **d\[key] ** Return the item of dictionary _d_ with key _key_.
* **d\[key] = value** Set key to value
* **clear(**_**d**_**)**
* **del **_**d**_**\[key] **
* **get(key\[, default]) ** Return the value for key if key is in the dictionary, else default.
* **items() **Return a new view of the dictionary’s items
* **iter(d) **Return an iterator over the keys of the dictionary. This is a shortcut for iter(d.keys()).
* **key in | not in **_**d**_
* **keys()**
* **pop(key\[, default])** If key is in the dictionary, remove it and return its value, else return default
* **popitem() **Remove and return a (key, value) pair from the dictionary in LIFO order
*   \*\*values()

    \*\*

**SET**

Sets contain unordered collections of unique items. They are defined much like lists and tuples, except they use the curly brackets of dictionaries.

```
primes = {2, 3, 5, 7}
odds = {1, 3, 5, 7, 9}
```

Sets have built-in operations such as union, intersection, difference, etc.

```
# union: items appearing in either set
> primes | odds   
{1, 2, 3, 5, 7, 9}  

# intersection: items appearing in both sets
> primes & odds
{3, 5, 7}

# difference: items in the first set but not the second set
> primes - odds
{2}

# symmetric difference: items appearing in only one set
> primes ^ odds
{1, 2, 9}
```

**COLLECTIONS**

More specialized data structures .. specialized container datatypes providing alternatives to Python’s general purpose built-in containers

[https://docs.python.org/3/library/collections.html](https://docs.python.org/3/library/collections.html)
