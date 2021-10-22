# Python - flatten\_json

[https://github.com/amirziai/flatten](https://github.com/amirziai/flatten)

from flatten\_json import flatten

from flatten\_json import unflatten

With Pandas:

dic\_flattened = (flatten(d) for d in dic)

df = pd.DataFrame(dic\_flattened)

ignore specific root keys:

flatten(dic, root\_keys\_to\_ignore={'b', 'c'})
