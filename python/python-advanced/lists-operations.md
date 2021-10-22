# Lists  Operations

[https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)

* Lists and Byte Arrays are **Mutable** sequence types.
* Tuples, Sets and Ranges are **Unmutable** sequence types.

## **Common Sequence Operations ** (Mutable and Unmutable)

Operation

Result

Notes

`x in s`

`True` if an item of _s_ is equal to _x_, else `False`

(1)

`x not in s`

`False` if an item of _s_ is equal to _x_, else `True`

(1)

`s + t`

the concatenation of _s_ and _t_

(6)(7)

`s \* n` or `n \* s`

equivalent to adding _s_ to itself _n_ times

(2)(7)

`s[i]`

_i_th item of _s_, origin 0

(3)

`s[i:j]`

slice of _s_ from _i_ to _j_

(3)(4)

`s[i:j:k]`

slice of _s_ from _i_ to _j_ with step _k_

(3)(5)

`len(s)`

length of _s_

`min(s)`

smallest item of _s_

`max(s)`

largest item of _s_

`s.index(x[, i[, j]])`

index of the first occurrence of _x_ in _s_ (at or after index _i_ and before index _j_)

(8)

`s.count(x)`

total number of occurrences of _x_ in _s_

## **Mutable Sequence Operations**

Operation

Result

Notes

`s[i] = x`

item _i_ of _s_ is replaced by _x_

`s[i:j] = t`

slice of _s_ from _i_ to _j_ is replaced by the contents of the iterable _t_

`del s[i:j]`

same as `s[i:j] = []`

`s[i:j:k] = t`

the elements of `s[i:j:k]` are replaced by those of _t_

(1)

`del s[i:j:k]`

removes the elements of `s[i:j:k]` from the list

`s.append(x)`

appends _x_ to the end of the sequence (same as`s[len(s):len(s)] = [x]`)

`s.clear()`

removes all items from _s_ (same as `del s[:]`)

(5)

`s.copy()`

creates a shallow copy of _s_ (same as `s[:]`)

(5)

`s.extend(t)` or `s += t`

extends _s_ with the contents of _t_ (for the most part the same as `s[len(s):len(s)] = t`)

`s \*= n`

updates _s_ with its contents repeated _n_ times

(6)

`s.insert(i, x)`

inserts _x_ into _s_ at the index given by _i_ (same as `s[i:i] = [x]`)

`s.pop([i])`

retrieves the item at _i_ and also removes it from _s_

(2)

`s.remove(x)`

remove the first item from _s_ where `s[i]` is equal to _x_

(3)

`s.reverse()`

reverses the items of _s_ in place

(4)
