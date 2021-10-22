# Pandas - join tables

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.join.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.join.html)

DataFrame.join(other, on=None, how='left', lsuffix='', rsuffix='', sort=False)

Another option to join using the key columns is to use the on parameter. DataFrame.join always uses other’s index but we can use any column in df. This method preserves the original DataFrame’s index in the result.

df.join(other.set\_index('key'), on='key')
