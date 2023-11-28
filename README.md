# Analysing the Performance of Two Data Clustering Algorithms

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](dataset)
- [Explanation and Preparation of Dataset](#explanation-and-preparation-of-dataset)
- [Implementation in Python](#implementation-in-python)
- [Evaluation of Algorithms](#evaluation-of-algorithms)
- [Results and Discussion](#results-and-discussion)
- [Conclusion](#conclusion)



### Project Overview

A data collection is segmented into subgroups by clustering so that each subset's data has specific characteristics. This study examines and contrasts two clustering methodologies. The algorithms under consideration are k-means and the hierarchical clustering algorithm. 

### Dataset
The Travel Reviews dataset from UCI was used for this study. UCI is a group of databases, domain theories, and data generators that the machine learning community employs to empirically analyse machine learning algorithms. This data set is populated by TripAdvisor.com. The dataset has 980 rows and 11 features.
Link: https://archive.ics.uci.edu/ml/datasets/Travel+Reviews

### Programming Language
- Python

### Explanation and Preparation of Datasets
Importing Libraries: The relevant Python libraries were imported, including NumPy, Pandas for data manipulation, Mat-plotlib, and Seaborn for visualisation.

Importing the Dataset: The tripadvisor_review.csv was imported into python using the read_csv () in pandas’ library.

Missing Values: Checking for missing values is an important step in data pre-processing, it readjusts the dataset by replacing the missing values, if missing values are present. The dataset did not contain missing values.

Normalisation: After performing pre-processing, normalization is performed to balance our datasets and to remove redundancy. The numerical columns in the dataset were chosen using the iloc() function. Because K-means uses a distance metric, K-means clustering requires all variables to be continuous. Scaling was then applied to the data. Scaling significantly affects the outcomes.

### Implementation in Python
- K – means Algorithm
- Hierarchical Clustering

#### Implementation of K – means Algorithm to Pre-processed Datasets
- Finding the Ideal Number of Clusters Using the Elbow Method: 
The choice of clustering variables is also of particular importance. Using K-means and the elbow approach, the ideal number of clusters was established.The elbow here appears to be at k = 2. 

![Finding the Ideal Number of Clusters Using the Elbow Method](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/dfc219a1-21a7-46a0-9d3f-b38c8166390e)


- Fitting K-Means to the Dataset: In the dataset, two (2) clusters were shown to be the optimal number of clusters. The fit_predict() method was then used to train a KMeans() estimator on the dataset. 
- Visualising the Clusters:The obtained data were represented in a scatterplot in relation to the clusters and centroids that were assigned to them. It uses various colours to distinguish each cluster.

  ![Visualising the Clusters for K-means](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/45690e83-1db6-41b2-bc96-80a2d0db3a18)

- Dimensionality Reduction: The clusters didn't seem to be distinct. To apply dimensionality reduction to the data, the PCA function was applied. The fitted data were then returned after performing PCA using the fit_transform() method.

  ![Visualising the Clusters after dimensionality reduction for K-means](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/31a1e6b4-c8b8-44e7-a055-1b4a44007a7b)

#### Implementation of Hierarchical Clustering Algorithm to Pre-processed Datasets
- Using the Dendrogram to Ascertain the Ideal Number of Clusters: To execute hierarchical clustering, the necessary function was imported, and then the resulting dendrogram was plotted. This dendrogram demonstrates how row data points are hierarchically clustered based on Euclidean distance. In the dendrogram, it displays the recommended number of clusters in several colour schemes. The dendrogram's horizontal lines, however, was used to determine the number of clusters to use, which is optimally 2.

  ![Finding the Ideal Number of Clusters Using the Dendrogram](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/290d9336-8f86-49e8-8cd4-40b87b2f6977)

- Fitting Hierarchical Clustering to the Dataset: An Agglomerative Clustering object was instantiated using the predetermined number of clusters and then the fit_predict() method was used on this to generate an array of cluster assignments.
  
- Visualising the Clusters: The data points were represented in a scatterplot to visualise the clusters. The cluster assignments match those from K-means clustering quite closely.

  ![Visualising the Clusters for HC](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/2e0767ac-c607-428e-82d6-144a0f5da4bd)


### Evaluation of Algorithms
#### Silhouette Analysis and Davies Bouldin Index were used to evaluate the algorithms. 

- Silhouette Analysis for K-means Clustering on Sample Data
  
![Silhouette Analysis for K-means Clustering on Sample Data](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/147f308d-47dc-48c2-805c-6b10473639ed)

- Silhouette Analysis for Hierarchical Clustering on Sample Data

  ![Silhouette Analysis for Hierarchical Clustering on Sample Data](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/4fe5b34c-6a4f-4195-af2c-fa29790848a8)

#### Evaluation of Algorithms Using Davies Bouldin Index

![Evaluation of Algorithms Using Davies Bouldin Index](https://github.com/Daviducheori/Analysing-the-Performance-of-Two-Data-Clustering-Algorithms/assets/76125377/2cb56810-29ed-4f3e-97e1-42e1ff800a9e)


### Results and Discussion
The two strategies produce distinct results in terms of performance. The comparison results show performance of hierarchical clustering technique is somewhat reduced compared to than that of the K-means, based on the results of the evaluations between the two algorithms.
The two algorithms generated distinct clusters although there was a slight overlap in both results. In comparison to hierarchical clustering, k-means clustering performed better. The Silhouette Score and Davies Bouldin index were used as metrics to evaluate the two clustering algorithms. Silhouettes score is calculated by taking the mean distance from intra-cluster and nearest cluster samples. K-means had a silhouette score of 0.26 while hierarchical clustering algorithm had 0.22. Both scores are acceptable and indicate that the clusters are not overlapping, but the closer the value of the silhouette score to 1 the better-separated the clusters. Hence, k-means had better separated clusters. 

Comparing the output of the two algorithms using the graphical representation of the cluster labels against the silhouette coefficient values. There is presence of negative values in the group 0 of algorithm and negative values are present in both groups using the hierarchical technique.

The output from the evaluation using Davies Bouldin index yielded a value of approximately 1.57 for K-means clustering and 1.76 for hierarchical clustering. The ratio of within-cluster to inter-cluster distances, which determines similarity, determines the Davies Bouldin Index, which is the average similarity measure between each cluster and its most similar cluster. The smaller the index, the better the clusters. K-means had a lower value compared to hierarchical clustering. The quality of the clusters was evaluated by observing the size of each cluster.


### Conclusion
Clustering is the technique of finding relationships among any group of data. Its application areas are pattern recognition, information retrieval and so on. There are several steps in this procedure, starting with pre-processing, algorithm creation, and result validity and evaluation. This project's major finding compares and contrasts the performance of the hierarchical clustering technique with K-means. When clustering some (noisy) data, all algorithms contain some degree of ambiguity. K-means produce clusters quickly and efficiently while hierarchical clustering is more sensitive to noisy data and exhibits significant change with time complexity. These algorithms, which originate from several academic circles and seek to solve various issues, each with their own advantages and disadvantages. Algorithms typically are constructed using specific suppositions that favour some type of biases. K-means performed better in comparison to hierarchical clustering based on the properties of the dataset, under certain conditions, the results may become quite different if the conditions change.











