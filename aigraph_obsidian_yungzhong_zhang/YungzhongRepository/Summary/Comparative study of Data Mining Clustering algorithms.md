[https://ieeexplore.ieee.org/document/7823946](https://ieeexplore.ieee.org/document/7823946)

#list #time_complexity

The article mainly discuss the following four clustering techniques:

- partitioning based(eg, K-means)
    
- hierachincal based(eg, BIRCH)
    
- Density based(eg, DBSCAN)
    
- Grid-based(eg, )
    

and then compare their complexity, advantage, disadvanrages and applications

## Partitioning based(Kmeans)

- objective function of kmeans
    
- algorithm of kmeans
    
- complexity of kmeans: O(n)
    
- Pros and Cons of kmeans
    
    - Pros:
        
        - simple
            
        - Efficient computational complexity
            
    - Cons
        
        - sensitive to noisy and outline
            
        - quality up to #clusters
            
        - Quality up to the distribution of data(spherical)
            
        - **works only on numerical data set**(solved by variant k-modes)
            
- Variants of Kmeas: k-modes - **can cluster categorical data**
    

## hierachincal based(BIRCH)

- introduction of clustering feature tree
    
- introducetion of BIRCH algorithm: bottom-top
    
- complexity of BIRCH: O(N)
    
- Pros and Cons of BIRCH
    
    - Pros:
        
        - Perform faster: With only a single scan BIRCH can perform a good clustering of the datasets. And with additional scans it can further improve the quality
            
        - incremental approach, no need the entire dataset in advance
            
        - less influenced by outlier/noisy: The clustering decisions are not made by considering all the data points and all the clusters
            
    - Cons:
        
        - Quality up to the distribution of data(spherical)
            
        - support only numerical data types.
            
        - **performance up to parameters**
            
- Variant of BIRCH: **suggest multiple threshold values. idea: the size of clusters are always not the same**
    

## Density based(DBSCAN)

- Concepts in DBSCAN: Eps-neigborhood, Direct density reachable, Density reachable, core point, border point
    
- Algorithm of DBSCAN
    
- **Complexity: O(n^2)**
    
- Pros and Cons of DBSCAN
    
    - Pros
        
        - gives good quality whatever shape of data distribution
            
        - robust to outliers
            
    - Cons:
        
        - two input parameters and quality of cluster depends on these parameters.
            
        - works only on numerical data set.
            
        - Suffers from identification of adjacent clusters with different density.
            
- Variants: ISDBSCAN - attempts to solve issues like parameter selection
    

## Grid-based(STING)

- STING: Statistical Information Grid. Constitute to a hierarchical structure: the cells that are present at higher levels are divided to form a number of cells at lower level
    
- TOP-DOWN
    
- algorithm of STING
    
- Complexity:O(K), where K is #cells in the grid
    
- pros and cons of STING
    
    - pros
        
        - The complexity depends on K, the number of grid cells and not n, the number of data points and K is usually less than n.
            
        - update a data then we can do that by incrementally updating rather by re-computing and hence reducing overhead.'
            
        - query independent
            
    - Cons
        
        - The clustering quality depends on the granularity at the bottom-most level
            
        - leaving out the diagonal boundary which may result in poor accuracy.
            
    

## Comparison

![image-20230827223851098](file:///Users/yun/Library/Application%20Support/typora-user-images/image-20230827223851098.png?lastModify=1695557413)

no experiments are provided.

## Summary

The paper mainly introduce four kinds of clustering techniques and provide each example of them, Kmeans, BIRCH, DBSCAN and STING. It provides the time complexity of each algorithm, which benefits for us to choose algorithms when scale of dataset or training speed matters. It also guides the readers to choose clustering models with listing advantage and disadvantages of each models. Regrettably, the paper didnt design experiment to validate the advantages or disadvantages listed.