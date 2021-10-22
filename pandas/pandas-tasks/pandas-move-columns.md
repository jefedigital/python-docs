# Pandas - move columns

[https://stackoverflow.com/questions/35321812/move-column-in-pandas-dataframe/35321983](https://stackoverflow.com/questions/35321812/move-column-in-pandas-dataframe/35321983)

cols = list(df.columns.values) #Make a list of all of the columns in the df

cols.pop(cols.index('b')) #Remove b from list

cols.pop(cols.index('x')) #Remove x from list

df = df\[cols+\['b','x']] #Create new dataframe with columns in the order you want

**move date to front**

df = df\[ \['date'] + \[col for col in df.columns if col != 'date']]
