# Pandas Fundamentals

{% file src="../.gitbook/assets/Pandas_Cheat_Sheet.pdf" %}
Pandas Cheat Sheet
{% endfile %}

Get count of rows in dataframe

```python
len(df)
```

Get count of distinct values in dataframe columns

```python
df.nunique()
df['col'].nunique()
```

Get count of rows per distinct value in dataframe

```python
df.value_counts()
df['col'].value_counts()
```

Get descriptive statistics for each column

```python
df.describe()
```

Group Data

[https://towardsdatascience.com/pandas-groupby-aggregate-transform-filter-c95ba3444bbb](https://towardsdatascience.com/pandas-groupby-aggregate-transform-filter-c95ba3444bbb)

```python
df.groupby([‘col’]) # groupby object, can accept column label (or list)
```

Summary functions

```python
df.groupby('title').mean()  # summary functions can be chained to groupby objects

count() # count of non-NAN rows per groupby level
size() # count of rows per groupby level

sum()
median()
quantile([dec]) # takes one or more decimals
min(), max()
mean()
var()
std()
apply(numpy_function)
```

Additional group functions

```python
rank(method=average|dense|first|min, pct=bool) # method = how to handle ties, default is 'average'

shift(n) # rolling window, retrieve value from n rows prior or after. 

# SPECIAL NOTE: the integer n for shift() is opposite of what you'd expect.
# shift(1) retrieves 1 row prior, shift(-1) retrieves 1 row following!
```

apply() vs agg()

```python
# apply 
df.groupby('Sales Rep').apply(np.sqrt)

# agg
df.groupby('Sales Rep').agg({ 
    'Order Id':'size',
    'Val':['sum','mean'],
    'Sale':['sum','mean']
})

# We pass a dictionary to the aggregation function, where the keys  are the columns and the values are the functions to be applied to the respective columns.
```

Sort dataframe by values

```python
df.sort_values([cols], acsending=[bool])
```

Sort dataframe by indexes (labels)

```python
df.sort_index(ascending=) # rows
df.sort_index(axis=1,ascending=) # columns
```

Move row indexes to column

```python
df.reset_index(drop)
# drop=True to remove indexes instead
```

Rename columns or row indexes

```python
df.rename(index={‘old’:’new’}) # rows
df.rename(columns={‘old’:’new’}) # columns
```

Remove columns or rows by label

```python
df.drop(index=['row1']) # list of row labels
df.drop(columns=['col1']) # list of column labels
```

Drop duplicate rows

```python
df.drop_duplicates()
```

Melt dataframe (columns -> rows)

```python
pd.melt(df, id_vars=[])  # this is a pandas method
```

Pivot dataframe

```python
df.pivot(index, columns, values)
```

Concat dataframes

```python
pd.concat([df1,df2]) # rows
pd.concat([df1,df2], axis=1) # columns
```

Filter rows with conditionals

```python
# conditional creates a Series, use to filter the larger dataframe:
df.col1 < 10  

df[df.col1 < 10]

# multiple conditionals require parentheses.  == for equality
df[(df.col1 < 10) & (df.col2 == 2)]
```

Filter rows and columns with regex

```python
df_cols.filter(regex='a', axis=0) # rows

df_cols.filter(regex='a', axis=1) # columns
```

Get random sample of rows from dataframe

```python
# frac for a fraction of the total df rows
df.sample(frac=0.3)

# n for a specific number of rows
df.sample(7)
```

Get rows with N largest and smallest values from dataframe

```python
df.nsmallest(N,['col']) # can take single col or list of multiple cols

df.nlargest(N,['col'])
```

Select rows and columns by label with loc and slice notation

```python
df.loc[row:row, col:col]

df.loc[‘row’]  # single element returns a series

df.loc['row1':'row2'] # return range of rows

df.loc['row1':'row2', 'col1':'col2'] # range of rows and cols

df.loc[:,'col1':'col2'] # all rows, range of cols

df.loc[df.col1 > 2, 'col2':'col3'] # ok to combine conditionals and slice
```

Select rows and columns by index with iloc and slice notation

```python
# zero-indexed
df_cols.iloc[1:,1:]
```

Joining Dataframes

```python
pd.merge(df1, df2, how='left|right|inner|outer|cross', on = ['col'])

# the 'on' parameter can take a single label or a list of labels.   If the columns have diffrent labels between the two dataframes, rename first.
```

Setlike Operations

```python
pd.merge(df1, df2) # INTERSECTION of rows that appear in both df's

pd.merge(df1, df2, how='outer') # UNION of rows that appear in either or both.
```

Window Calculations

```python
df.rolling(n).func
```
