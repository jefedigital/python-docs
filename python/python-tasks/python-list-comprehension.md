# Python - list comprehension

[https://djangostars.com/blog/list-comprehensions-and-generator-expressions/](https://djangostars.com/blog/list-comprehensions-and-generator-expressions/)

List Comprehension

\[j for j in range(5)]

Nested List Comprehension

matrix = \[\[j for j in range(5)] for i in range(5)]

\[\[a\[f] for f in fields] for a in report\['data’]]

**Logic**

ads\_df\['creative\_id'] = \['dc' if 'dc\_trk\_cid' in a else 'utm' for a in ads\_df\['click\_url']]
