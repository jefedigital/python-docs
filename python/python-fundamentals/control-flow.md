# Control Flow

**CONDITIONAL STATEMENTS **( IF, ELIF, ELSE )

Conditional statements, often referred to as if-then statements, allow the programmer to execute certain pieces of code depending on some Boolean condition.

```
if x == 0:
    print(x, "is zero")
elif x > 0:
    print(x, "is positive")
elif x < 0:
    print(x, "is negative")
else:
    print(x, "is unlike anything I've ever seen...")
```

Note the use of colons and indented code blocks.

ELIF is short for “ELSE IF”. Both ELIF and ELSE are optional.

**LOOPS** (For)

Loops in Python are a way to repeatedly execute some code statement.

```
for N in [2, 3, 5, 7]:
    print(N, end=' ') # print all on same line

2 3 5 7
```

We specify the variable we want to use, the sequence we want to loop over, and use the "in" operator to link them together in an intuitive and readable way.

More precisely, the object to the right of the "in" can be any Python iterator.

One of the most commonly-used iterators in Python is the** range** object, which generates a sequence of numbers:

```
for i in range(10):
    print(i, end=' ')

0 1 2 3 4 5 6 7 8 9
```

Note that in Python 2, range() produces a list, while in Python 3, range() produces an iterable object.

**LOOPS** (While)

The other type of loop in Python is a while loop, which iterates until some condition is met:

```
i = 0
while i < 10:
    print(i, end=' ')
    i += 1

0 1 2 3 4 5 6 7 8 9
```

The argument of the while loop is evaluated as a boolean statement, and the loop is executed until the statement evaluates to False.

**BREAKING LOOPS **(Break and Continue)

* The **break** statement breaks-out of the loop entirely
* The **continue** statement skips the remainder of the current loop, and goes to the next iteration

```
for n in range(20):
    # if the remainder of n / 2 is 0, skip the rest of the loop
    if n % 2 == 0:
        continue
    print(n, end=' ')

1 3 5 7 9 11 13 15 17 19
```

This loop will fill a list with all Fibonacci numbers up to a certain value.

Notice that we use a **while True** loop, which will loop forever unless we have a **break** statement!

```
a, b = 0, 1
amax = 100
L = []

while True:
    (a, b) = (b, a + b)
    if a > amax:
        break
    L.append(a)

print(L)

[1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
```

One rarely used pattern available in Python is the else statement as part of a for or while loop.

Think of the** loop-else** as a _nobreak_ statement: that is, the** else** block is executed only if the loop ends naturally, without encountering a break statement.

```
L = []
nmax = 30

for n in range(2, nmax):
    for factor in L:
        if n % factor == 0:
            break
    else: # no break
        L.append(n)

[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

(Above is the Sieve of Eratosthenes, a well-known algorithm for finding prime numbers)
