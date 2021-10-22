# Pandas - isin()

`DataFrame.``isin`(_self_, _values_)Whether each element in the DataFrame is contained in values.

[https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.isin.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.isin.html)

Example

[https://stackoverflow.com/questions/50449088/check-if-value-from-one-dataframe-exists-in-another-dataframe](https://stackoverflow.com/questions/50449088/check-if-value-from-one-dataframe-exists-in-another-dataframe)

Df1 = pd.DataFrame({'name': \['Marc', 'Jake', 'Sam', 'Brad']

Df2 = pd.DataFrame({'IDs': \['Jake', 'John', 'Marc', 'Tony', 'Bob’]

Df1.name.isin(Df2.IDs).astype(int)

0 1

1 1

2 0

3 0
