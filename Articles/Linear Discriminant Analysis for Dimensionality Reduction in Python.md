
https://machinelearningmastery.com/linear-discriminant-analysis-for-dimensionality-reduction-in-python/

Dimensionality reduction is the process of reducing the number of input variables(features) for a predictive model. Fewer input variables can result in a simpler predictive model that may have better performance when making predictions on new data.

Curse of dimensionality - Considering data is represented using rows and columns, input variables are the columns, representing dimensions on an n-dimensional feature space and rows of data are points in that space.  Having a large number of dimensions in the feature space can mean that the volume of that space is very large, and in turn, the points that are in that space often represent a small and non-representative sample which can dramatically impact the performance of machine learning algorithms fit on data.

**Projection methods** - seek to reduce the number of dimensions in the feature space whilst also preserving the most important structure or relationships between the variables observed in the data. The original features no longer exist and new features are constructed from the available data that are not directly comparable to the original data.

Linear Discriminant Analysis or LDA (which is different from the topic modelling method Latent Dirichlet Allocation) is a multi-class classification method that can also be used as a dimensionality reduction technique. It seeks to find a linear combination of input variables that achieves the maximum separation for samples between classes (class centroids or means) and the minimum separation of samples within each class.