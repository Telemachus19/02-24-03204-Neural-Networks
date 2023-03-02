---
title: Explanation of the Steps taken in the assignment
author: Ahmed Ashraf Mohamed
---

# Loading The data

Import the numpy library and load the sales data into a variable `data` using function `numpy.load()`
```python
import numpy as np
data = np.load("sales_data.npy")
```
Check the sales data, its dimensions and shape of the numpy array.
assign the number of rows of the data into a variable `rows` and the number of columns into a variable `cols`
```py
print(data,data.ndim,data.shape,sep="\n")
rows = data.shape[0]
cols = data.shape[1]
```

# Slice the array to extract the sales data for the year 2022.

Since the data is arranged, we can slice the numpy array easily. Knowing that the data contains five months of each year.

```py
data2022 = data[10:15,3]
print(data2022)
```

# Calculate the total sales amount for each country for the year 2022.
Since the the total sales amount is the fourth column, we can loop through the 2022 slice or through the whole data, and extract the total sales amount for the year 2022 of each country, and calculate the total sales amount for all the countries in 2022
```py
totalCountries = 0 # used to hold the total sales for all countries
# looping through the whole data using the rows variable
for i in range(rows): 
    # checking the for year 2022
    if "2022" in data[i,0]:
        print("Country:", data[i,1], "Total Sales:", data[i,4],sep = "\t", end="\n")
        totalCountries += int(data[i,4])
print("Total Sales for all Countries in the year 2022:",totalCountries)
```
