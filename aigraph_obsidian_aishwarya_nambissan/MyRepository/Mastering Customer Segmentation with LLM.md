
https://towardsdatascience.com/mastering-customer-segmentation-with-llm-3d9008235f41

**Python Outlier Detection Library** - This library is focused on detecting outliers for different cases

**ECOD** method (**empirical cumulative distribution functions for outlier detection**) -This method seeks to obtain the distribution of the data and thus know which are the values ​​where the probability density is lower (outliers)

**Prince library** - This library is focused on exploratory analysis and dimensionality reduction

**MCA** (Multiple Correspondence Analysis) - method is contained inside Prince library and is great for visualizations since it accepts as mixed dataset

**Evaluation Metrics**

1. Davies Bouldin index
The Davies Bouldin index is defined as the average similarity measure of each cluster with its most similar cluster, where similarity is the ratio of within-cluster distances to between-cluster distances.    
The minimum value of the DB Index is 0, whereas a smaller  
value (closer to 0) represents a better model that produces better clusters.

2. Calinski Harabaz Index (Variance Ratio Criterion)
Calinski Harabaz Index is defined as the ratio of the  
sum of between-cluster dispersion and of within-cluster dispersion.    
The higher the index the more separable the clusters.

3. Silhouette score
The silhouette score is a metric used to calculate the goodness of fit of a clustering algorithm, but can also be used as  
a method for determining an optimal value of k (see here for more).  Its value ranges from -1 to 1.  
A value of 0 indicates clusters are overlapping and either  
the data or the value of k is incorrect.    
1 is the ideal value and indicates that clusters are very  
dense and nicely separated.

When we apply the PCA method, since it is a linear algorithm, it is not capable of capturing more complex relationships.  **t-SNE**  is capable of capturing  complex polynomial relationships, but it has higher computational cost.

To find out which features are the most important and what are the main characteristics of the clusters, the importance of each variable is assessed by creating a classification model where the “X” is the inputs of the clustering model, and the “y” is the clusters predicted by the clustering model.

_LGBMClassifier_ is a good classification model. This model is quite powerful and works well having categorical and numerical variables. Having the new model trained, using the _SHAP_ library, the importance of each of the features in the prediction can be obtained.

**LLMs** cannot understand written text directly, so the input of this type of models have to be transformed. For this, **Sentence** **Embedding** is carried out. Thanks to the large dimension of the vector created by embedding, small variations in the data can be seen with greater precision.
