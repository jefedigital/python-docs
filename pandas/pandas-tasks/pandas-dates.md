# Pandas - dates

[https://medium.com/jbennetcodes/dealing-with-datetimes-like-a-pro-in-pandas-b80d3d808a7f](https://medium.com/jbennetcodes/dealing-with-datetimes-like-a-pro-in-pandas-b80d3d808a7f)

df\['date'] = pd.to\_datetime(df\['date'], format='%d/%b/%Y:%H:%M:%S +0000', utc=True)

**convert a unix timestamp**

if seconds

pd.to\_datetime(df\['date'], unit='s’)

if milliseconds

pd.to\_datetime(df\['date'], unit=‘ms’)
