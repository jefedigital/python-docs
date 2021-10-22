# Python - split dictionaries

Function splits dictionary into list of sub-dicts

def split\_dict(x, chunks):

i = itertools.cycle(range(chunks))

split = \[dict() for \_ in range(chunks)]

for k, v in x.items():

split\[next(i)]\[k] = v

return split

Example

keywords = split\_dict(cfg\['keywords'],3)
