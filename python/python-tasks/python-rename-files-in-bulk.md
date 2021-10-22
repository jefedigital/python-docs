# Python - rename files in bulk

import os

for f in glob.glob(‘data/\*.csv'):

filename = (f\[9:f.find('\_2020')]) + ".csv” # insert recipe here

os.rename(f,filename)
