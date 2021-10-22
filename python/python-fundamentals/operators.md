# Operators

**ARITHMETIC OPERATORS** OperatorNameDescription`a + b`AdditionSum of `a` and `b``a - b`SubtractionDifference of `a` and `b``a * b`MultiplicationProduct of `a` and `b``a / b`True divisionQuotient of `a` and `b``a // b`Floor divisionQuotient of `a` and `b`, removing fractional parts`a % b`ModulusInteger remainder after division of `a` by `b``a ** b`Exponentiation`a` raised to the power of `b``-a`NegationThe negative of `a``+a`Unary plus`a` unchanged (rarely used)

The floor division operator was added in Python 3; you should be aware if working in Python 2 that the standard division operator (`/`) acts like floor division for integers and like true division for floating-point numbers.

**ASSIGNMENT OPERATORS**

`a += b``a -= b``a *= b``a /= b``a //= b``a %= b``a **= b``a &= b``a |= b``a ^= b``a <<= b``a >>= b`

**COMPARISON OPERATORS**

OperationDescriptionOperationDescription`a == b``a` equal to `b``a != b``a` not equal to `b``a < b``a` less than `b``a > b``a` greater than `b``a <= b``a` less than or equal to `b``a >= b``a` greater than or equal to `b`

Note the "double equals" for Comparison (a == b). The “single equals" is reserved for variable assignment.

BOOLEAN OPERATORS

* And
* Or
* Not

With parenthesis:

```
x = 4
(x < 6) and (x > 2)
True

(x > 10) or (x % 2 == 0)
True

not (x < 6)
False
```

**IDENTITY & MEMBERSHIP OPERATORS**

OperatorDescription`a is b`True if `a` and `b` are identical objects`a is not b`True if `a` and `b` are not identical objects`a in b`True if `a` is a member of `b``a not in b`True if `a` is not a member of `b`

```
a = [1, 2, 3]
b = [1, 2, 3]

a == b
True

a is b
False

a is not b
True
```

The difference between the two cases here is that in the first, `a` and `b` point to different objects, while in the second they point to the same object.

As we saw in the previous section, Python variables are pointers. The "`is`" operator checks whether the two variables are pointing to the same container (object), rather than referring to what the container contains.

With this in mind, in most cases that a beginner is tempted to use "`is`" what they really mean is `==`.

```
1 in [1, 2, 3]
True

2 not in [1, 2, 3]
False
```
