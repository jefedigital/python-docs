# List Comprehension

GREAT GUIDE: [https://data-flair.training/blogs/python-list-comprehension/](https://data-flair.training/blogs/python-list-comprehension/)

**BASIC LIST COMPREHENSIONS**

List comprehensions are simply a way to compress a list-building for-loop into a single short, readable line.

For example, here is a loop that constructs a list of the first 12 square integers:

```
[n ** 2 for n in range(12)]

[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121]
```

This basic syntax is

## \[_expr_ for _var_ in _iterable_]

where expr is any valid expression, var is a variable name, and iterable is any iterable Python object.

**MULTIPLE ITERATION**

To build a list from two values, add another **for** expression in the comprehension:

```
[(i, j) for i in range(2) for j in range(3)]

[(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)]
```

**CONDITIONALS ON THE ITERATOR**

You can further control the iteration by adding a conditional to the end of the expression:

```
[val for val in range(1,31) if val % 3 == 0] # note 31, as end of range() is non-inclusive

[3, 6, 9, 12, 15, 18, 21, 24, 27, 30]  # multiples of 3 from 0 to 30
```

**SET COMPREHENSION**

With curly braces you can create a set with a **set comprehension**:

```
{n**2 for n in range(12)}

{0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121}
```

Recall that a set is a collection that contains no duplicates. The set comprehension respects this rule, and eliminates any duplicate entries:

```
{a % 3 for a in range(1000)}

{0, 1, 2}
```

**DICT COMPREHENSION**

Use curly braces and add a colon (:) to create a dict comprehension:

```
{n:n*2 for n in range(4)}

{0: 0, 1: 2, 2: 4, 3: 6}
```

**GENERATOR EXPRESSION**

Use parentheses instead of square or curly brackets to create a **generator expression**:

```
(n*2 for n in range(4))

<generator object <genexpr> at 0x7fbdf9835200>
```

A generator expression is essentially a list comprehension in which elements are generated as-needed rather than all at-once. It’s a recipe for generating a list comprehension at a later time, which means memory and computational efficiency.

Notice that printing the generator expression does not print the contents; one way to print the contents of a generator expression is to pass it to the list constructor:

```
G = (n*2 for n in range(4))

> list(G)
[0, 2, 4, 6]
```

Generators are single-use!

```
G = (n*2 for n in range(4))

> list(G)
[0, 2, 4, 6]

> list(G)
[]
```

And they can be stopped and re-started. There are uses for this (working with collections of files on disk?)

```
G = (n**2 for n in range(12))
for n in G:
    print(n, end=' ')
    if n > 30: break

print("\ndoing something in between")

for n in G:
    print(n, end=' ')

0 1 4 9 16 25 36 
doing something in between
49 64 81 100 121
```

**GENERATOR FUNCTIONS** (Yield)

We can make more complicated generators using generator functions, which make use of the **yield** statement.

Here are identical generators; one using comprehension, the other a function with a yield statement:

```
G1 = (n ** 2 for n in range(12))

def gen():
    for n in range(12):
        yield n ** 2

G2 = gen()
print(*G1)
print(*G2)

0 1 4 9 16 25 36 49 64 81 100 121
0 1 4 9 16 25 36 49 64 81 100 121
```

A generator function is a function that, rather than using **return** to return a value once, uses **yield **to yield a (potentially infinite) sequence of values.

Just as in generator expressions, the state of the generator is preserved between partial iterations,

**NESTED CONDITIONALS**

For integers 0 to 7, it first filters out the elements that aren’t perfectly divisible by 2. For the remaining elements, it keeps only those that are divisible by 3. Finally, it stores these elements in a list, and prints it out

```
[i for i in range(8) if i%2==0 if i%3==0]
```

**IF/ELSE with LIST COMPREHENSIONS**

The order is going to be different.

Since the first thing we specify in a comprehension is the value to put in a list, this is where we put the TRUE result of the our if-else.

\[TrueValue IF eval ELSE FalseValue FOR element IN list]

```
["Even" if i%2==0 else "Odd" for i in range(8)]
```

**NESTED LIST COMPREHENSIONS**

Used these a lot for traversing JSON documents from API calls.

This is one approach with FOR loops:

```
for i in range(7,9):
  for j in range(1,11):
    print(f"{i}*{j}={i*j}")
```

However using nested List Comprehensions:

```
[ [i*j for j in range(1,11)] for i in range(7,9)]
```

Note how the FOR loop for J was the inner loop in the first code; that relationship is preserved here.
