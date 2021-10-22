# Pandas - import data to df

read\_csv

[http://lira.no-ip.org:8080/doc/python-pandas-doc/html/generated/pandas.read\_csv.html](http://lira.no-ip.org:8080/doc/python-pandas-doc/html/generated/pandas.read\_csv.html)

read\_excel

import multiple csv to a df

import pandas as pd

import glob

df = pd.concat(\[pd.read\_csv(f) for f in glob.glob('data\*.csv')], ignore\_index = True)

[https://medium.com/@kadek/elegantly-reading-multiple-csvs-into-pandas-e1a76843b688](mailto:https://medium.com/@kadek/elegantly-reading-multiple-csvs-into-pandas-e1a76843b688)

[https://stackoverflow.com/questions/20906474/import-multiple-csv-files-into-pandas-and-concatenate-into-one-dataframe](https://stackoverflow.com/questions/20906474/import-multiple-csv-files-into-pandas-and-concatenate-into-one-dataframe)

Almost all of the answers here are either unnecessarily complex (glob pattern matching) or rely on additional 3rd party libraries. You can do this in 2 lines using everything Pandas and python (all versions) already have built in.

For a few files - 1 liner:

df = pd.concat(map(pd.read\_csv, \['data/d1.csv', 'data/d2.csv','data/d3.csv']))

For many files:

from os import listdir

filepaths = \[f for f in listdir("./data") if f.endswith('.csv')]

df = pd.concat(map(pd.read\_csv, filepaths))

How I did it .. multiple .csv in directory “infolder” with skiprows of 0 .. axis=1 for a horizontal concat.

df = pd.concat(\[pd.read\_csv(infolder + f, skiprows=0) for f in listdir(infolder) if f.endswith('.csv')], sort=False, axis=0)
