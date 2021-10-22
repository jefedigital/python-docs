# Python - date and time

datetime and timedelta

[https://docs.python.org/3.7/library/datetime.html](https://docs.python.org/3.7/library/datetime.html)

from datetime import datetime, timedelta

**strptime:** parse datetime from string

my\_datetime\_object = datetime.strptime(my\_date\_string,'%Y-%m-%d')

**strftime: **parse string from datetime

my\_date\_string = datetime.strftime(my\_datetime\_object,'%Y-%m-%d')

dateutil.relativedelta

[https://dateutil.readthedocs.io/en/stable/relativedelta.html](https://dateutil.readthedocs.io/en/stable/relativedelta.html)

timedelta doesn’t handle months so well .. use this instead.

from datetime import date

from dateutil.relativedelta import relativedelta as rd

six\_months = date.today() + rd.relativedelta(months=+6)

get a series of months with start and end dates

from dateutil import relativedelta as rd

start\_date = datetime.strptime('2018-09-01','%Y-%m-%d')

end\_date = datetime.strptime('2019-06-01','%Y-%m-%d')

months = rd.relativedelta(end\_date, start\_date).months

for m in range(months):

sd = start\_date + rd.relativedelta(months=+m)

ed = start\_date + rd.relativedelta(months=+m+1) - timedelta(1)
