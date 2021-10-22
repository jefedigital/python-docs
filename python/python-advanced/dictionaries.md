# Dictionaries

**MERGING DICTIONARIES**

Addition notation won’t work .. there are 3 options:

**1. Update()**

The update method for dictionaries appends one after the other.

```
dicta = {'one':1, 'two':2}
dictb = {'three':3, 'four':4}

dicta.update(dictb)

> dicta
{'one': 1, 'two': 2, 'three': 3, 'four': 4}
```

**2. Unpacking Operator (\*\*)**

Create a new dict with the \*\* unpacking operators for each component, separated by commas:

```
dictc = {**dicta, **dictb}

> dictc
{'one': 1, 'two': 2, 'three': 3, 'four': 4}
```

**3. Pipe Operator (|)**

Simplest solution by far.. available in Python 3.9

```
dictc = dicta | dictb

> dictc
{'one': 1, 'two': 2, 'three': 3, 'four': 4}
```

**Duplicate Keys override Values**

In all these cases, if there is a duplicate key in a subsequent dict, it will override the previous value of that key.

```
dicta = {'one':1, 'two':2}
dictb = {'two':20, 'three':3, 'four':4}

dictc = {**dicta, **dictb}

> dictc
{'one': 1, 'two': 20, 'three': 3, 'four': 4}
```
