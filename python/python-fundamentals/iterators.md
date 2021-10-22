# Iterators

Often an important piece of data analysis is repeating a similar calculation, over and over, in an automated fashion.

There’s a lot of cool stuff here we’re skipping, on to the actual functions..

**ENUMERATE**

Often you need to iterate not only the values in an array, but also keep track of the index.

```
L = [2, 4, 6, 8, 10]

for i, val in enumerate(L):
    print(i, val)

0 2
1 4
2 6
3 8
4 10
```

**ZIP**

Other times, you may have multiple lists that you want to iterate over simultaneously.

```
L = [2, 4, 6, 8, 10]
R = [3, 6, 9, 12, 15]

for lval, rval in zip(L, R):
    print(lval, rval)

2 3
4 6
6 9
8 12
10 15
```

**MAP and FILTER**

The map iterator takes a function and applies it to the values in an iterator:

_map(function, iterator)_

```
# find the first 10 square numbers
square = lambda x: x ** 2

for val in map(square, range(10)):
    print(val, end=' ')

0 1 4 9 16 25 36 49 64 81
```

The filter iterator is similar, but only passes through values for which the filter function evaluates to True:

_filter(function, iterator)_

```
# find values up to 10 for which x % 2 is zero
is_even = lambda x: x % 2 == 0

for val in filter(is_even, range(10)):
    print(val, end=' ')

0 2 4 6 8
```

SPECIALIZED ITERATORS

The itertools module contains a whole host of useful iterators, including COUNT, PERMUTATIONS, COMBINATIONS, and PRODUCT.

[https://docs.python.org/3.10/library/itertools.html](https://docs.python.org/3.10/library/itertools.html)
