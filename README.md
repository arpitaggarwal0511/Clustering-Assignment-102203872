# 🍷 Wine Quality Clustering Analysis (Red Wine)

This project performs a comparative study of clustering techniques on the **Red Wine Quality** dataset from the UCI Machine Learning Repository. We evaluate multiple preprocessing techniques and clustering algorithms using standard performance metrics.

---

## 📦 Dataset

- **Source**: [Wine Quality - UCI Repository](https://archive.ics.uci.edu/dataset/186/wine+quality)
- **File used**: `winequality-red.csv`
- **Attributes**: 11 physicochemical properties (e.g., acidity, sugar, pH)

---

## 🧪 Preprocessing Techniques

We tested the following combinations:
- No Processing
- Normalization (StandardScaler)
- Transform (PowerTransformer)
- PCA (Principal Component Analysis)
- Transform + Normalize (T+N)
- Transform + Normalize + PCA (T+N+PCA)

---

## 🤖 Clustering Algorithms

- **K-Means Clustering**
- **Hierarchical (Agglomerative) Clustering**
- **Mean Shift Clustering**

---

## 📈 Evaluation Metrics

- **Silhouette Score** (higher = better)
- **Calinski-Harabasz Index** (higher = better)
- **Davies-Bouldin Score** (lower = better)

---

## 📊 Sample Results

| Algorithm     | Preprocessing | Clusters | Silhouette | Calinski-Harabasz | Davies-Bouldin |
|---------------|---------------|----------|------------|--------------------|----------------|
| KMeans        | Normalization | 5        | 0.77       | 7999               | 0.77           |
| Agglomerative | T+N+PCA       | 5        | 0.48       | 3677               | 0.77           |
| MeanShift     | T+N+PCA       | 6        | 0.56       | 4087               | 0.71           |
| KMeans        | PCA           | 3        | 1.00       | 5294               | 0.41           |
| Agglomerative | PCA           | 3        | 1.00       | 2766               | 0.09           |

> Full results can be found in `clustering_results.csv`.

---

## 📎 Files

- `wine_clustering.ipynb`: The Colab notebook with complete clustering analysis
- `clustering_results.csv`: Table of all evaluation results
- `README.md`: This file with method and result summary
- `results_table.png`: (Optional) Screenshot of table output

---

## 🧠 Conclusion

- **Normalization + KMeans** gave strong performance in high dimensions.
- **PCA** helped when visualizing clusters in 2
