[10.17485/ijst/2016/v9i3/75971](http://dx.doi.org/10.17485/ijst/2016/v9i3/75971)

# A Survey on Clustering Techniques for Big Data Mining

### 1. Summary of the paper:

The paper discusses the introduction and architecture of big data, describes various clustering algorithms, and compares them in terms of 4 V's of big data characteristics, namely Volume, Variety, Velocity, and Value. There are several specific clustering algorithms in each categories but only one provided in the category of partitioned based algorithm. The paper provides detailed steps for each algorithm mentioned, so this paper is important for researchers and students who want to understand how the algorithms work instead of just know the basic idea. However, the paper contains some errors of text editing, such as placing the explanation of one concept on another concept and vice versa, which may cause confusion during reading.

### 2.  4 V’s of Big Data characteristics:

- **Volume**: it refers to the ability of an algorithm to deal with large amounts of a data. 
	Criteria: 
	- Size of the data set
	- High dimensionality
	- Handing outliers
- **Variety**: This refers to the different types of data that can be present in a data set, such as numerical, categorical, continuous, ordinal, and ratio.
	Criteria: 
	- Type of the data set
	- Cluster shape
- **Velocity**: mainly refers Time complexity.
- **Value**: numbers of input parameters.

### 3. Comparison results:

- All grid based clustering algorithm mentioned in this paper can work for large size of dataset, and their cluster shape is arbitrary.
- The paper suggests that use BIRCH, CLIQUE and ORCLUS to identify the outliers in large datesets.
- If the data's type is categorical, CURE and ROCK will be better choices.
- STING, OPTIGRID, PROCLUS and ORCLUS can be applied for spatial data.
