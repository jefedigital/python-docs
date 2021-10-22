# Function Annotations

[https://www.geeksforgeeks.org/function-annotations-python/](https://www.geeksforgeeks.org/function-annotations-python/)

Function annotations are arbitrary python expressions that are associated with various part of functions. These expressions are evaluated at compile time and have no life in python’s runtime environment. Python does not attach any meaning to these annotations. They take life when interpreted by third party libraries, for example, mypy.

**Syntax of function annotations**

They are like the optional parameters that follow the parameter name.

**Note:**

**Annotations for simple parameters :** The argument name is followed by ‘:’ which is then followed by the expression. Annotation syntax is shown below.

```
def foobar(a: expression, b: expression = 5):
```

**Annotations for excess parameters :** Excess parameters for e.g. \*args and \*\*kwargs, allow arbitrary number of arguments to be passed in a function call. Annotation syntax of such parameters is shown below.

```
def foobar(*args: expression, *kwargs: expression):
```

**Annotations for nested parameters : **Nested parameters are useful feature of python 2x where a tuple is passed in a function call and automatic unpacking takes place. This feature is removed in python 3x and manual unpacking should be done. Annotation is done after the variable and not after the tuple as shown below.

```
def foobar((a: expression, b: expression), (c: expression, d: expression)):
```

**Annotations for return type :** Annotating return type is slightly different from annotating function arguments. The ‘->’ is followed by expression which is further followed by ‘:’. Annotation syntax of return type is shown below.

```
def foobar(a: expression)->expression
```
