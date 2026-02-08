# Implementing and Evaluating K-Means Clustering from Scratch

## 📌 Project Overview
This project implements the K-Means clustering algorithm entirely from scratch using only NumPy. The goal is to understand the internal workings of K-Means, including centroid initialization, distance calculation, cluster assignment, centroid updates, and convergence.

The custom implementation is evaluated using Inertia and Silhouette Score and compared against the standard scikit-learn KMeans implementation.

---

## 🧠 Objectives
- Implement K-Means without using built-in clustering functions
- Understand the impact of random initialization
- Evaluate clustering performance using internal metrics
- Compare custom implementation with scikit-learn

---

## 🛠 Tools & Libraries
- Python
- NumPy
- scikit-learn

---

## 📊 Dataset
Synthetic data is generated using `sklearn.datasets.make_blobs`:
- Number of samples: 500
- Number of clusters: 3
- Controlled variance

---

## 🔁 Step-by-Step Process

### Step 1: Initialize Centroids
Randomly select `K` data points as initial centroids.

### Step 2: Assign Clusters
Each data point is assigned to the nearest centroid using Euclidean distance.

### Step 3: Update Centroids
Centroids are recalculated as the mean of assigned points.

### Step 4: Convergence Check
The algorithm stops when centroid movement is below a tolerance threshold or when max iterations are reached.

### Step 5: Inertia Calculation
Inertia is computed as the sum of squared distances between data points and their assigned centroids.

### Step 6: Multiple Runs
The algorithm is run 10 times with different random seeds to evaluate stability.

### Step 7: Silhouette Score
Silhouette Score is calculated to measure clustering quality.

### Step 8: Comparison with Scikit-learn
Results are compared with scikit-learn’s KMeans implementation.

---

## 📈 Results Summary

### Custom K-Means (10 runs)
- Average Inertia: Computed across runs
- Average Silhouette Score: Indicates good cluster separation
- Inertia variance highlights sensitivity to initialization

### Scikit-learn K-Means
- Lower and more stable inertia
- Slightly higher silhouette score due to optimized initialization (k-means++)

---

## 🔍 Conclusion
The custom K-Means implementation performs comparably to scikit-learn but shows higher variance due to random initialization. This highlights the importance of robust initialization strategies such as k-means++.

---

## ✅ How to Run

```bash
pip install numpy scikit-learn
python experiment.py




## 🔍 Experimental Insights

### Inertia Analysis
The custom K-Means implementation shows slightly higher average inertia compared to scikit-learn. This is primarily due to random centroid initialization, whereas scikit-learn uses the optimized k-means++ strategy.

### Silhouette Score Analysis
The average Silhouette Score achieved by the custom implementation is close to that of scikit-learn, indicating reasonably good cluster separation despite simpler initialization.

### Stability Analysis
Running the algorithm multiple times revealed noticeable variance in inertia values, highlighting the sensitivity of K-Means to initial centroid selection.

### Key Takeaways
- Custom implementation correctly follows K-Means logic
- Random initialization impacts stability and performance
- Improved initialization methods can significantly enhance clustering results

