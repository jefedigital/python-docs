# Functions

Functions are groups of code that have a name, and can be called using parentheses.

For example, _print_ is a built-in Python function:

```
> print('abc’)
abc
```

Here print is the function name, and 'abc' is the function's argument.

In addition to arguments, there are _keyword arguments_ that are specified by name.

One available keyword argument for the print() function is _sep_, which tells what character or characters should be used to separate multiple items:

```
> print(1, 2, 3, sep='-‘)
1-2-3
```

When non-keyword arguments are used together with keyword arguments, the keyword arguments must come at the end.

**DEFINING FUNCTIONS**

In Python, functions are defined with the** def **statement.

For example, we can encapsulate a version of our Fibonacci sequence code from the previous section as follows:

```
def fibonacci(N):
    L = []
    a, b = 0, 1
    while len(L) < N:
        a, b = b, a + b
        L.append(a)
    return L


> fibonacci(10) # run the fibonacci function with argument 10
[1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
```

Functions can return any Python object, simple or compound.

For example, multiple return values are simply put in a tuple, which is indicated by commas:

```
def real_imag_conj(val):
    return val.real, val.imag, val.conjugate()

> r, i, c = real_imag_conj(3 + 4j)
> print(r, i, c)

3.0 4.0 (3-4j)
```

**DEFAULT ARGUMENT VALUES**

When defining a function, there are certain values that we want the function to use most of the time, but we'd also like to give the user some flexibility. In this case, we can use default values for arguments.

```
def fibonacci(N, a=0, b=1):
    L = []
    while len(L) < N:
        a, b = b, a + b
        L.append(a)
    return L

> fibonacci(10) # use default values for a and b
[1, 1, 2, 3, 5, 8, 13, 21, 34, 55]

> fibonacci(10, 0, 2) # define values for a and b (order matters)
> fibonacci(10, b=2, a=0) # can also be named (order doesn't matter)
[2, 2, 4, 6, 10, 16, 26, 42, 68, 110]
```

**FLEXIBLE ARGUMENTS**

Sometimes you don't know how many arguments the user will pass. In this case, you can use the special form \*args and \*\*kwargs to catch all arguments.

The words ARGS and KWARGS are simply conventions, they can be any string. The important piece is the \* or \*\* preceeding them:

\* (single asterisk) means **arguments **in the form of a sequence (in the order the function is expecting to receive them)

\*\* (double asterisk) means **keyword arguments** in the form of a dictionary (in which case order does not matter)

```
def print_my_arguments(*ordered_args, **keyword_args):
    print(‘ordered args: ‘, ordered_args)
    print(‘keyword_args: ‘, keyword_args)

> print_my_arguments(1, 2, 3, a=4, b=5)

ordered_args: (1,2,3)
keyword_args: ('a':4, 'b':5)
```

Again, a single \* before a variable means "expand this as a sequence", while a double \*\* before a variable means "expand this as a dictionary".

In fact, this syntax can be used not only with the function definition, but with the function call as well:

```
inputs = (1, 2, 3)
keywords = {'a':4, 'b':5}

> print_my_arguments(*inputs, **keywords)

ordered_args: (1,2,3)
keyword_args: ('a':4, 'b':5)
```

**ANONYMOUS FUNCTIONS** (Lambda Functions)

Instead of using the **def** statement, we can use **lambda **to define short, one-time functions:

```
add = lambda x, y: x + y

>add(1,2)
3
```

Remember that everything is an object in Python, even functions themselves. This means functions can be passed as arguments to other functions.

More on this laters ..
