# Datetime - functions

**Converting datetime to strings (with formatting)**

**from datetime import date**

date.today().strftime('%Y-%m-%d')

**from datetime import datetime**

date.today().strftime('%m/%d/%Y, %H:%M:%S')

**Converting strings to datetimes**

my\_date = datetime.strptime('2019-06-01','%Y-%m-%d')

**Calculating with datetimes and returning values**

start\_date = datetime.strptime('2019-06-15','%Y-%m-%d')

end\_date = datetime.strptime('2019-06-27','%Y-%m-%d’)

num\_days = (end\_date - start\_date)**.days**
