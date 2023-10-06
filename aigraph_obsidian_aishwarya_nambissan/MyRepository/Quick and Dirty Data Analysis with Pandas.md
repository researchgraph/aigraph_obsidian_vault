
https://machinelearningmastery.com/quick-and-dirty-data-analysis-with-pandas/

Pandas python library is built for fast data analysis and manipulation.

Printing the data frame directly shows the first 60 rows.
**print(data)**

To get distribution of each attribute by reviewing summary statistics, specifically: the count, mean, standard deviation, min, max, and 25th, 50th (median), 75th percentiles.:
**print(data.describe())**

To review the spread of each attribute use box and whisker plots:  

**import matplotlib.pyplot as plt
data.boxplot()**

To look at the distribution of each attribute by discretization of the values into buckets and reviewing the frequency in each bucket as histograms:
**data.hist()**

To explore the relationship of each attribute to the class attribute:
**data.groupby('class').hist()**

For better contrast of the attribute values for each class on the same plot
**data.groupby('class').plas.hist(alpha=0.4)**

To explore the relationships between the attributes by looking at the distribution of the interactions of each pair of attributes:
**from pandas.plotting import scatter_matrix
scatter_matrix(data, alpha=0.2, figsize=(6, 6), diagonal='kde')**
This uses a built function to create a matrix of scatter plots of all attributes versus all attributes. The diagonal where each attribute would be plotted against itself shows the Kernel Density Estimation of the attribute instead.
