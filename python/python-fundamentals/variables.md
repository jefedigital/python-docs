# Variables

Assigning variables in Python is as easy as putting a variable name to the left of the equals (`=`) sign.

```
# assign 4 to the variable x
x = 4
```

In Python, variables are best thought of not as containers but as pointers. In the above statement, you are essentially defining a pointer named `x` that points to some other bucket containing the value `4`.

Because Python variables just point to various objects, there is no need to "declare" the variable, or even require the variable to always point to information of the same type! This is the sense in which people say Python is dynamically-typed: variable names can point to objects of any type.

```
x = 1         # x is an integer
x = 'hello'   # now x is a string
x = [1, 2, 3] # now x is a list
```

While users of statically-typed languages might miss the type-safety that comes with declarations like those found in C, this dynamic typing is one of the pieces that makes Python so quick to write and easy to read.

If we have two variable names pointing to the same mutable object, then changing one will change the other as well!

```
x = [1, 2, 3]  # a list
y = x
```

We've created two variables `x` and `y` which both point to the same object. Because of this, if we modify the list via one of its names, we'll see that the "other" list will be modified as well:

```
print(y)
[1, 2, 3]

x.append(4) # append 4 to the list pointed to by x

print(y)
[1, 2, 3, 4]
```

Note also that if we use "`=`" to assign another value to `x`, this will not affect the value of `y` – assignment is simply a change of what object the variable points to:

```
x = 'something else'

print(y)
[1, 2, 3, 4]
```

Numbers, strings, and other simple types are immutable: you can't change their value – you can only change what values the variables point to.

```
x = 10
y = x
x += 5  # add 5 to x's value, and assign it to x

print(x,y)
(15, 10)
```

When we call `x += 5`, we are not modifying the value of the `10` object pointed to by `x`; we are rather changing the variable `x` so that it points to a new integer object with value `15`. For this reason, the value of `y` is not affected by the operation.
