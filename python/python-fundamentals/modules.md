# Modules

A module is a file containing Python definitions and statements.

The file name is the module name with the suffix .py appended.

Within a module, the module’s name is available as the global variable \_\_name\_\_ .

A sample module we’ll call **fibo ** — saved as fibo.py

```sql
# Fibonacci numbers module

def fib(n):    # write Fibonacci series up to n
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()
```

Import the module:

```sql
import fibo
```

Now you can access the functions in **fibo**

```sql
> fibo.fib(1000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
```

For simplicity you can assign a module’s functions to a local name:

```sql
> myfibby = fibo.fib
> myfibby(1000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
```

Even better, you can import individual functions (or all functions) from one module into another:

```sql
from fibo import fib, fib2

(or ..)

from fibo import fib as myfibby  # custom name

(or..)

from fibo import *
```

Now you can access these functions directly instead of having to call to **fibo** every time.

```sql
> fib(1000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
```

_Note: Using the \\_ wildcard imports all names except those beginning with an underscore (\_). In most cases Python programmers do not use this facility since it introduces an unknown set of names into the interpreter.\*

Modules can be executed as scripts. When you run a module from the command line with:

```sql
python fibo.py <arguments>
```

the code in the module executes just as if you had imported it, but with the \_\_name\_\_ global variable set to “\_\_main\_\_”.
