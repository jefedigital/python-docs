# Iterables and Iterators

An **ITERATOR** is an object that represents a stream of data, from which items can be returned one at a time.

Most built-in containers in Python (such as Lists, Tuples, Strings, Dicts) can produce Iterator objects, so we call them ITERABLES.

However these containers themselves are not ITERATORS. One needs to create an ITERATOR object separately:

```python
# define a list
my_list = [4,7,0,3]

# create an iterator object using iter()
my_iterator = iter(my_list)

# now we can apply iterable functions to it...

# print all the elements using next()
```

Guide: [https://www.programiz.com/python-programming/iterator](https://www.programiz.com/python-programming/iterator)

FunctionDescription`all()`Returns `True` if all elements of an iterable are true[`any()`](https://realpython.com/any-python/)Returns `True` if any elements of an iterable are true[`enumerate()`](https://realpython.com/python-enumerate/)Returns a list of tuples containing indices and values from an iterable`filter()`Filters elements from an iterable`iter()`Returns an iterator object`len()`Returns the length of an object`map()`Applies a function to every item of an iterable`next()`Retrieves the next item from an iterator`range()`Generates a range of integer values`reversed()`Returns a reverse iterator`slice()`Returns a `slice` object[`sorted()`](https://realpython.com/python-sort/)Returns a sorted list from an iterable[`zip()`](https://realpython.com/python-zip-function/)Creates an iterator that aggregates elements from iterables

**RANGE()**

_**range(start, end, step)**_** **

The Range function generates arithmetic progressions

```
range(0, 10, 3)
0, 3, 6, 9
```
