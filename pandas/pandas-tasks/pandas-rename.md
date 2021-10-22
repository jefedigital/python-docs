# Pandas - rename

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html)

replace using list of new column names

df.rename(columns={"A": "a", "C": "c”}, inplace=True)

str.replace method

df.columns = df.columns.str.replace('$','')
