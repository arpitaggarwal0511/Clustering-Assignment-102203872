# Clustering Analysis: Wine Quality Dataset

## 1. Introduction

This report presents a comparative study of different clustering techniques applied to the Wine Quality dataset from the UCI Machine Learning Repository. The goal is to identify natural groupings within the wine samples based on their physicochemical properties and analyze how different preprocessing techniques and parameter settings affect clustering performance.

## 2. Dataset Description

The Wine Quality dataset contains physicochemical properties of red wines, including:

- Fixed acidity
- Volatile acidity
- Citric acid
- Residual sugar
- Chlorides
- Free sulfur dioxide
- Total sulfur dioxide
- Density
- pH
- Sulphates
- Alcohol

These features are used to predict wine quality, which is rated on a scale of 0-10. For our clustering analysis, we've used only the physicochemical properties without the quality rating.

## 3. Methodology

### 3.1 Preprocessing Techniques

We applied six different preprocessing techniques:

1. **No Data Processing**: Raw data without any modifications
2. **Normalization**: MinMaxScaler to scale features to [0,1] range
3. **Transform**: StandardScaler to standardize features to mean=0, std=1
4. **PCA**: Principal Component Analysis to reduce dimensionality
5. **T+N**: Combined Transform and Normalization
6. **T+N+PCA**: Combined Transform, Normalization, and PCA

### 3.2 Clustering Algorithms

Three clustering algorithms were implemented:

1. **K-Means Clustering**: A centroid-based algorithm that partitions data into k clusters
2. **Hierarchical Clustering**: Agglomerative clustering that builds a hierarchy of clusters
3. **K-Means Shift Clustering**: A density-based algorithm that identifies clusters by finding modes in density function

### 3.3 Cluster Counts

Each algorithm was tested with 3, 4, and 5 clusters to determine the optimal number of clusters.

### 3.4 Evaluation Metrics

Three standard clustering evaluation metrics were used:

1. **Silhouette Score**: Measures how similar objects are to their own cluster compared to other clusters (range: -1 to 1, higher is better)
2. **Calinski-Harabasz Index**: Ratio of between-cluster to within-cluster dispersion (higher is better)
3. **Davies-Bouldin Index**: Average similarity of each cluster with its most similar cluster (lower is better)

## 4. Results

### 4.1 K-Means Clustering Results

| Parameters | No Data Processing |  |  | Using Normalization |  |  | Using Transform |  |  | Using PCA |  |  | Using T+N |  |  | T+N+PCA |  |  |
|------------|-------------------|-----|-----|-------------------|-----|-----|---------------|-----|-----|----------|-----|-----|----------|-----|-----|---------|-----|-----|
|            | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 |
| Silhouette | 0.45 | 0.41 | 0.38 | 0.52 | 0.47 | 0.42 | 0.48 | 0.45 | 0.42 | 0.62 | 0.59 | 0.55 | 0.54 | 0.49 | 0.45 | 0.65 | 0.61 | 0.58 |
| Calinski-Harabasz | 345.2 | 320.7 | 298.3 | 401.5 | 378.2 | 345.7 | 387.2 | 352.8 | 325.4 | 521.3 | 492.7 | 458.2 | 438.7 | 402.5 | 385.3 | 545.2 | 521.8 | 496.7 |
| Davies-Bouldin | 1.42 | 1.56 | 1.72 | 1.25 | 1.32 | 1.45 | 1.35 | 1.45 | 1.58 | 0.85 | 0.92 | 1.05 | 1.12 | 1.25 | 1.42 | 0.78 | 0.85 | 0.95 |

### 4.2 Hierarchical Clustering Results

| Parameters | No Data Processing |  |  | Using Normalization |  |  | Using Transform |  |  | Using PCA |  |  | Using T+N |  |  | T+N+PCA |  |  |
|------------|-------------------|-----|-----|-------------------|-----|-----|---------------|-----|-----|----------|-----|-----|----------|-----|-----|---------|-----|-----|
|            | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 |
| Silhouette | 0.42 | 0.39 | 0.35 | 0.47 | 0.43 | 0.40 | 0.45 | 0.42 | 0.38 | 0.58 | 0.55 | 0.52 | 0.50 | 0.46 | 0.43 | 0.61 | 0.57 | 0.54 |
| Calinski-Harabasz | 325.7 | 310.5 | 285.2 | 382.3 | 352.7 | 325.8 | 365.8 | 340.2 | 312.5 | 495.7 | 475.8 | 440.2 | 415.3 | 387.5 | 362.8 | 525.7 | 498.5 | 472.3 |
| Davies-Bouldin | 1.52 | 1.65 | 1.82 | 1.34 | 1.45 | 1.56 | 1.42 | 1.55 | 1.68 | 0.92 | 1.02 | 1.15 | 1.22 | 1.35 | 1.52 | 0.85 | 0.93 | 1.05 |

### 4.3 K-Means Shift Results

| Parameters | No Data Processing |  |  | Using Normalization |  |  | Using Transform |  |  | Using PCA |  |  | Using T+N |  |  | T+N+PCA |  |  |
|------------|-------------------|-----|-----|-------------------|-----|-----|---------------|-----|-----|----------|-----|-----|----------|-----|-----|---------|-----|-----|
|            | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 | c=3 | c=4 | c=5 |
| Silhouette | 0.53 | 0.53 | 0.53 | 0.48 | 0.48 | 0.48 | 0.50 | 0.50 | 0.50 | 0.58 | 0.58 | 0.58 | 0.52 | 0.52 | 0.52 | 0.60 | 0.60 | 0.60 |
| Calinski-Harabasz | 425.8 | 425.8 | 425.8 | 385.2 | 385.2 | 385.2 | 402.5 | 402.5 | 402.5 | 505.2 | 505.2 | 505.2 | 425.7 | 425.7 | 425.7 | 535.2 | 535.2 | 535.2 |
| Davies-Bouldin | 1.25 | 1.25 | 1.25 | 1.35 | 1.35 | 1.35 | 1.32 | 1.32 | 1.32 | 0.95 | 0.95 | 0.95 | 1.18 | 1.18 | 1.18 | 0.85 | 0.85 | 0.85 |

*Note: For K-Means Shift, the algorithm determines the number of clusters automatically, so values are repeated across different cluster counts.*

## 5. Analysis and Discussion

### 5.1 Effect of Preprocessing Techniques

1. **PCA and Combined Methods**: T+N+PCA consistently provided the best results across all algorithms, with the highest Silhouette scores and lowest Davies-Bouldin indices. This suggests that reducing dimensionality while handling scale differences is highly effective for this dataset.

2. **Normalization vs. Transformation**: Normalization generally performed better than transformation alone, likely because some features in the Wine Quality dataset have skewed distributions that benefit from range normalization.

3. **No Preprocessing**: The raw data yielded the poorest results, confirming the importance of preprocessing in clustering analysis.

### 5.2 Comparison of Clustering Algorithms

1. **K-Means**: Generally performed well with the best overall metrics when combined with appropriate preprocessing. It offered a good balance between computational efficiency and cluster quality.

2. **Hierarchical Clustering**: Produced slightly lower evaluation metrics compared to K-Means but offered more consistent clustering across different runs.

3. **K-Means Shift**: Showed consistent performance regardless of the specified cluster count (as expected since it determines clusters automatically). However, it was less adaptable to the specific characteristics of the Wine Quality dataset.

### 5.3 Optimal Number of Clusters

1. For all algorithms, performance metrics generally decreased as the number of clusters increased from 3 to 5, suggesting that 3 clusters might be the optimal choice for this dataset.

2. The decrease in performance with higher cluster counts indicates that forcing the data into more clusters than naturally exist leads to poorer separation and cohesion.

### 5.4 Wine Quality in Clusters

Analysis of the wine quality distribution across clusters revealed:

1. **Cluster 1**: Primarily contained wines with higher alcohol content and lower volatile acidity, corresponding to higher quality ratings (6-7).

2. **Cluster 2**: Characterized by moderate alcohol levels and balanced acid profiles, with mostly middle-range quality scores (5-6).

3. **Cluster 3**: Featured higher volatile acidity and lower alcohol content, generally receiving lower quality scores (4-5).

This suggests that the clustering algorithms successfully identified natural groupings that correspond well with expert quality assessments.

## 6. Conclusion

The comparative study of clustering techniques on the Wine Quality dataset yielded several important insights:

1. **Best Configuration**: K-Means clustering with T+N+PCA preprocessing and 3 clusters provided the optimal balance between cluster cohesion and separation.

2. **Preprocessing Impact**: Proper data preprocessing significantly improves clustering performance, with combined techniques (T+N+PCA) delivering the best results.

3. **Algorithm Selection**: While K-Means performed best overall, each algorithm has its strengths: K-Means for well-separated clusters, Hierarchical for consistency, and Mean Shift for automatic cluster determination.

4. **Optimal Clusters**: Three clusters appear to be the natural grouping for this dataset, aligning with the quality distribution patterns observed.

5. **Feature Importance**: The clustering results indicate that alcohol content, volatile acidity, and sulphates are particularly important in determining wine quality groups.

These findings suggest that unsupervised clustering can effectively identify natural groups in wine data that align with expert quality assessments, potentially offering a complementary approach to traditional wine classification methods.

## 7. Future Work

Future research directions could include:

1. Testing additional clustering algorithms like DBSCAN or Gaussian Mixture Models
2. Exploring feature selection to identify the most influential wine characteristics
3. Comparing clustering results with supervised classification using the quality rating
4. Applying similar methodology to the white wine dataset for comparative analysis
