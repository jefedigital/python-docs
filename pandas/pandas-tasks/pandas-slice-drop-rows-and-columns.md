# Pandas - slice drop rows & columns

Drop rows where columns 10+ are all NA. (and convert 0’s to NA)

import numpy as np

df = df.replace(0, np.nan)

df = df.dropna(subset=df.columns\[10:], how='all')

Drop rows with value conditions

df\[df.name != 'Tina’]

df\[\~df\['campaign\_name'].str.contains('shopping')] ## \~ negates the condition

Drop Columns

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop.html)

df.drop(\['B', 'C'], axis=1, inplace=True)

Drop Columns where labels are duplicated

df = df.loc\[: , \~df.columns.duplicated()]

Explanation: [https://stackoverflow.com/questions/33585928/how-to-delete-columns-from-a-dataframe-with-columns-with-the-same-label](https://stackoverflow.com/questions/33585928/how-to-delete-columns-from-a-dataframe-with-columns-with-the-same-label)

df.loc(rows, columns)

Multiple Conditionals

df1 = df\[(df.a != -1) & (df.b != -1)]

**Use slices with .iloc**

df.iloc\[1:3, 0:3]
