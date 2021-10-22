# Lists  Sorting

[https://docs.python.org/3/howto/sorting.html](https://docs.python.org/3/howto/sorting.html)

## **.SORT() and SORTED()**

Python lists have a built-in list.sort() method that modifies the list in-place. There is also a sorted() built-in function that builds a new sorted list from an iterable.

```
mylist = [3,6,1,2,7]

s = sorted(mylist) # creates a new list
print(s)
[1, 2, 3, 6, 7]


mylist.sort() # sorts the list in-place
print(mylist)
[1, 2, 3, 6, 7]
```

## REVERSE Parameter

Both list.sort() and sorted() accept a reverse parameter with a boolean value.

```
sorted(mylist, reverse=True)
[7, 6, 3, 2, 1]
```

## **KEY Parameter**

The **KEY** parameter defines a function to be used on each list element.

The most common pattern is to sort complex objects, using some of the incides as keys.

```
mylist = [['sue', 50.0], ['bob', 20.0], ['aaron', 20.0]]

sorted(mylist, key = lambda x:x[1])
[['bob', 20.0], ['aaron', 20.0], ['sue', 50.0]]
```

In fact this usage is so common that the OPERATORS module can be imported to use itemgetter(), attrgetter() and methodcaller() functions.

```
from operator import itemgetter

sorted(mylist, key = itemgetter(1))
[['bob', 20.0], ['aaron', 20.0], ['sue', 50.0]]

sorted(mylist, key = itemgetter(1,0))  # and you can sort by multiple indices
[['aaron', 20.0], ['bob', 20.0], ['sue', 50.0]]
```
