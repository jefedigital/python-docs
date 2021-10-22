# Errors and Exceptions

Mistakes come in three basic flavors:

* **Syntax errors: **Errors where the code is not valid Python (generally easy to fix)
* **Runtime errors:** Errors where syntactically valid code fails to execute, perhaps due to invalid user input (sometimes easy to fix)
* **Semantic errors**: Errors in logic: code executes without a problem, but the result is not what you expect (often very difficult to track-down and fix)

**Exception Handling** helps us deal with Runtime Errors.

**CATCHING EXCEPTIONS** (Try and Except)

Runtime Errors can happen in a lot of ways, including:

* if you try to reference an undefined variable
* if you try an operation that's not defined
* trying to compute a mathematically ill-defined result
* trying to access a sequence element that doesn't exist

In each case, Python is kind enough to not simply indicate that an error happened, but to spit out a meaningful exception that includes information about what exactly went wrong, along with the exact line of code where the error happened.

The main tool Python gives you for handling runtime exceptions is the try...except clause. Its basic structure is:

```
try:
    print("this gets executed first")
except:
    print("this gets executed only if there is an error")

this gets executed first
```

Let's put a problematic statement in the try block and see what happens:

```
try:
    print("let's try something:")
    x = 1 / 0 # ZeroDivisionError
except:
    print("something bad happened!")

let's try something:
something bad happened!
```

It's nearly always a better idea to catch exceptions **explicitly:**

```
def safe_divide(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return 1E100

> safe_divide(1, 0)
1e+100

> safe_divide(1, '2')
TypeError: unsupported operand type(s) for /: 'int' and 'str'
```

In the above example, a ZeroDivisionError error returns a “safe value” we assign, while other types of errors pass through unmodified.

**RAISING EXCEPTIONS** (Raise)

It's equally valuable to make use of informative exceptions within the code you write, so that users of your code (foremost yourself!) can figure out what caused their errors.

The way you raise your own exceptions is with the raise statement:

```
raise RuntimeError("my error message")
```

As an example of where this might be useful, let's return to our fibonacci function that we defined previously, creeating a ValueError to handle cases where the user enters a negative number as the argument.

```
def fibonacci(N):
    if N < 0:
        raise ValueError("N must be non-negative")
    L = []
    a, b = 0, 1
    while len(L) < N:
        a, b = b, a + b
        L.append(a)
    return L

> fibonacci(-10)
..
ValueError: N must be non-negative
```

**ACCESSING THE ERROR MESSAGE **

Sometimes in a try...except statement, you would like to be able to work with the error message itself. This can be done with the as keyword:

```
try:
    x = 1 / 0
except ZeroDivisionError as err:
    print("Error class is:  ", type(err))
    print("Error message is:", err)

Error class is:   <class 'ZeroDivisionError'>
Error message is: division by zero
```

CLEANING UP

In addition to try and except, you can use the else and finally keywords to further tune your code's handling of exceptions. The basic structure is this:

```
try:
    print("try something here")
except:
    print("this happens only if it fails")
else:
    print("this happens only if it succeeds")
finally:
    print("this happens no matter what")
```
