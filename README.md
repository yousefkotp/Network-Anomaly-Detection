# Network Anomaly Detection

The exponential growth of network traffic has led to an increase in network anomalies, such as cyber attacks, network failures, and hardware malfunctions. Network anomaly detection is a critical task for maintaining the security and stability of computer networks. The objective of this project is to implement clustering algorithms from scratch such as K-mean, Spectral Clustering, Hierarchical Clustering and DBSCAN. All of those clustering algorithms can be used for network anomaly detection.

## Table of Contents
- [Newtork Anomaly Detection](#network-anomaly-detection)
  - [Dataset](#dataset)
    - [Data Preprocessing](#data-preprocessing)
  - [Algorithms](#algorithms)
    - [K-mean](#k-mean)
    - [Spectral Clustering](#spectral-clustering)
    - [Hierarchical Clustering](#hierarchical-clustering)
        - [Pseudocode](#pseudocode)
    - [DBSCAN](#dbscan)
        - [Pseudocode](#pseudocode-1)
  - [Results](#results)
  - [Contributors](#contributors)


## Dataset
For this project, we will use the ["KDD Cup 1999" dataset](https://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html?fbclid=IwAR2W62F9o8T5fllzvL-7mkA6amNjo8shdGi3QNfqCak86BEtBdLZUh-h8UI), which is a widely used benchmark dataset for network anomaly detection. This dataset contains network traffic data collected from a simulated environment, including features such as protocol type, service, source and destination IP addresses, source and destination ports, and attack types.

### Data Preprocessing



## Algorithms



### K-mean



### Spectral Clustering



### Hierarchical Clustering
- Hierarchical clustering is a type of unsupervised machine learning algorithm that groups similar data points together based on a distance or similarity measure. It creates a hierarchy of clusters, which can be visualized using a dendrogram. There are two main types of hierarchical clustering: agglomerative and divisive.

- Agglomerative hierarchical clustering starts by assigning each data point to its own cluster and then iteratively merges the two closest clusters until all the data points are in a single cluster. Divisive hierarchical clustering, on the other hand, starts with all data points in a single cluster and recursively splits it into smaller clusters until each data point is in its own cluster. This project only implements Agglomerative hierarchical clustering.

- Hierarchical clustering is extremely useful when we don't know the number of clusters beforehand, unlike some other clustering algorithms. Additionally, the dendrogram can help visualize the clustering structure and can be used to identify the optimal number of clusters.

- There are some potential drawbacks to hierarchical clustering. Firstly, it can be computationally expensive for large datasets, as the algorithm needs to compute a distance matrix between all pairs of data points. Secondly, the clustering results can be sensitive to the choice of distance metric and linkage method, which can significantly affect the resulting clusters. Finally, hierarchical clustering can be susceptible to the so-called chaining effect, where nearby clusters are merged into a single cluster even if they do not belong together, leading to suboptimal clustering results.

#### Pseudocode
```python
AGNES(D, k)
  C = {c1, c2, ..., cN} where ci = {xi}
  while |C| > k
    find a pair of clusters {ci, cj} that minimizes d(ci, cj)
    merge {ci, cj} into a new cluster {ci, cj}
    remove ci and cj from C
    add {ci, cj} to C
  return C
```

### DBSCAN
- DBSCAN is a density-based clustering algorithm where given a set of points in some space, it groups together points that are closely packed together (points with many nearby neighbors), marking as outliers points that lie alone in low-density regions (whose nearest neighbors are too far away). It is one of the most common clustering algorithms and also one of the most versatile, able to find clusters of any shape, as long as they are dense enough. It is also one of the most used clustering algorithms in real-world applications.

- One of the advantages of DBSCAN is that it does not require the number of clusters to be specified beforehand, unlike some other clustering algorithms. Additionally, DBSCAN can handle non-linearly separable data and is robust to outliers.

- However, there are some potential drawbacks to DBSCAN. Firstly, the choice of parameters, such as the neighborhood radius(eps) and minimum density threshold(n_neighbors), can significantly affect the resulting clusters, and determining the optimal parameters for a given dataset can be challenging. Secondly, the algorithm can struggle with datasets that have varying densities or irregular shapes, as the density threshold may not capture all the relevant structures in the data. Finally, DBSCAN can be computationally expensive for large datasets, as it requires a distance matrix computation and multiple passes through the data.

#### Pseudocode
```python
DBSCAN(D, eps, MinPts)
  C = 0
  for each unvisited point P in dataset D
    mark P as visited
    NeighborPts = regionQuery(P, eps)
    if sizeof(NeighborPts) < MinPts
      mark P as NOISE
    else
      C = next cluster
      expandCluster(P, NeighborPts, C, eps, MinPts)
```

## Results


 
## Contributors

- [Yousef Kotp](https://github.com/yousefkotp)

- [Mohamed Farid](https://github.com/MohamedFarid612)

- [Adham Mohamed](https://github.com/adhammohamed1)

