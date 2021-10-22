# Pandas - dataframe column names .. flatten MultiIndex DFs

flatten the multiindex columns for writing to df

df.columns = \[b.lower() if b != '' else a.lower() for a,b in df.columns]

find and replace a string in (some) dataframe columns

str = ‘boop\_'

df\_pivot.columns = \[c.split(str)\[1] if str in c else c for c in df\_pivot.columns]

**rename()**

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html)

df.rename(index={0: "x", 1: "y", 2: "z”})

df.rename(columns={"A": "a", "B": "b", "C": "c"}, errors="raise")
