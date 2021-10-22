# Decorators

A decorator is a function that extends the behavior of another function without explicitly modifying it.

{% embed url="https://realpython.com/primer-on-python-decorators/" %}

```
def do_twice(func):
    def wrapper_do_twice():
        func()
        func()
    return wrapper_do_twice
    
@do_twice
def say_whee():
    print("Whee!")
    
>>> say_whee()
Whee!
Whee!
```

### Decorating Functions With Arguments

Use [`*args` and `**kwargs`](https://realpython.com/python-kwargs-and-args/) in the inner wrapper function. Then it will accept an arbitrary number of positional and keyword arguments...

```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        func(*args, **kwargs)
    return wrapper_do_twice
    
@do_twice
def say_whee():
    print("Whee!")
    
@do_twice
def greet(name):
    print(f"Hello {name}")
    
>>> say_whee()
Whee!
Whee!

>>> greet("World")
Hello World
Hello World
```

### Returning Values From Decorated Functions

You need to **make sure the wrapper function returns the return value of the decorated function**.&#x20;

```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs)
    return wrapper_do_twice
    
# The return value from the last execution of the function is returned:

>>> return_greeting("Adam")
Creating greeting
Creating greeting
'Hi Adam'
```
