# Objects, Attributes, Methods

Python is an object-oriented programming language, and in Python everything is an object.

An object is an entity that contains data along with associated metadata and/or functionality. In Python everything is an object, which means every entity has some **metadata (called \*\***attributes**\*\*)** and associated** functionality (called \*\***methods**\*\*)**. These attributes and methods are accessed via the dot syntax.

**ATTRIBUTES**

metadata about the object

**METHODS**

functionality around the object

For example, before we saw that lists have an `append` method, which adds an item to the list, and is accessed via the dot ("`.`") syntax:

```
L = [1, 2, 3]
L.append(100)
print(L)

[1, 2, 3, 100]
```

What is sometimes unexpected is that in Python even simple types have attached attributes and methods. For example, numerical types have a `real` and `imag` attribute that returns the real and imaginary part of the value, if viewed as a complex number:

```
x = 4.5
print(x.real, "+", x.imag, 'i’)

4.5 + 0.0 i
```

Methods are similar to functions, and can be called with parenthesis: For example, floating point numbers have a method called `is_integer` that checks whether the value is an integer:

```
x = 4.5
x.is_integer()
False

x = 4.0
x.is_integer()
True
```

When we say that everything in Python is an object, we really mean that everything is an object – even the attributes and methods of objects are themselves objects with their own `type` information:

```
type(x.is_integer)
builtin_function_or_method
```
