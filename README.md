# Day 13 - DBSCAN Clustering

This project is part of my Machine Learning journey, where I implemented 
**DBSCAN (Density-Based Spatial Clustering of Applications with Noise)** and 
compared it with **K-Means** and **Hierarchical (Agglomerative) Clustering** on
a synthetic dataset.

## Project Overview

DBSCAN is a density-based clustering algorithm that groups together points that are 
closely packed and marks points in low-density regions as noise. Unlike K-Means, it does
not require specifying the number of clusters and can detect clusters of arbitrary shape.

In this notebook, I:
- Created a synthetic 2D dataset of **concentric circles plus noise**
- Applied **K-Means** clustering
- Applied **Agglomerative Hierarchical** clustering
- Applied **DBSCAN** clustering
- Visualized and compared the clustering results

## Key Concepts

- **Density-based clustering**: Forms clusters where data points are densely packed and
- treats sparse areas as noise.
- **DBSCAN parameters**:
  - `eps` (Epsilon): Neighborhood radius around a point.
  - `min_samples`: Minimum number of points required in the `eps`-neighborhood to be
  -  considered a core point.
- **Core points, border points, and noise**:
  - Core points: Have at least `min_samples` points within `eps`.
  - Border points: Fewer than `min_samples` neighbors but reachable from a core point.
  - Noise: Neither core nor border points for any cluster.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Google Colab / Jupyter Notebook

## Implementation Steps

1. Import necessary libraries
2. Create a synthetic dataset:
   - Concentric circles using sine and cosine (polar coordinates)
   - Added random noise points
3. Visualize the raw data
4. Train and visualize:
   - **K-Means** with a fixed number of clusters
   - **AgglomerativeClustering** with Euclidean distance
   - **DBSCAN** with chosen `eps` and `min_samples`
5. Compare how each algorithm:
   - Handles **arbitrary-shaped clusters**
   - Treats **noise / outliers**

## Algorithms and Parameters

### Dataset

- Synthetic 2D data:
  - Multiple concentric circular patterns
  - Additional uniformly distributed noise points

### K-Means

```python
KMeans(n_clusters=4, random_state=42)
```

### Agglomerative Clustering

```python
AgglomerativeClustering(
    n_clusters=4,
    affinity="euclidean"
)
```

### DBSCAN

```python
DBSCAN(
    eps=30,
    min_samples=6
)
```

## Results

- **K-Means**:
  - Forces the data into a fixed number of clusters.
  - Struggles with **arbitrary-shaped clusters**.
  - Includes noise points inside clusters.

- **Hierarchical (Agglomerative) Clustering**:
  - Similar limitations on arbitrary shapes.
  - Also fails to properly treat noise separately.

- **DBSCAN**:
  - Successfully identifies **ring-shaped clusters**.
  - Marks scattered points as **noise** instead of forcing them into clusters.
  - Demonstrates the strength of density-based clustering for this kind of data.

## Learning Outcomes

From this project, I learned:

- How DBSCAN works conceptually (density, eps, min_samples).
- The difference between **centroid-based**, **hierarchical**, and **density-based**clustering.
- How to generate and visualize synthetic clustering datasets.
- How DBSCAN can better handle noise and arbitrary-shaped clusters compared to K-Means and hierarchical clustering.

## Project Structure

```bash
day_13_DBSCAN/
│── day_13_DBSCAN.ipynb
│── README.md
```

## Future Improvements

- Use a **real-world dataset** to apply DBSCAN.
- Experiment with:
  - Different values of `eps` and `min_samples`.
  - Other clustering algorithms like **DBSCAN vs. OPTICS**.
- Add evaluation metrics and cluster quality analysis.

## Author

**Arvind**

This notebook is part of my daily ML practice series, where I implement and document different machine learning algorithms step by step.
