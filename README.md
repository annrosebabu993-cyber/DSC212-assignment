# Spectral Modularity–Based Community Detection on the Karate Club Graph

## Project Summary

This project implements a **recursive spectral modularity algorithm** to detect community structure in **Zachary’s Karate Club** network.  
It follows the requirements of the *DSC212: Graph Theory* research assignment and includes:

- Modularity-based spectral bisection  
- Community evolution visualization  
- Centrality metric tracking  
- Analytical interpretation of patterns  

---

## Assignment Objectives

### 1. Recursive Spectral Modularity Partitioning

The modularity matrix is defined as:

$B = A - \frac{kk^\top}{2m}$


where  
- \(A\): adjacency matrix  
- \(k\): degree vector  
- \(m\): number of edges  

Procedure:

1. Compute the modularity matrix \(B\).
2. Perform eigenvalue decomposition to obtain the **leading eigenvector**.
3. Use \(\mathrm{sign}(u_1)\) for bipartition.
4. Apply recursive bisection only when:

$\lambda_1 > 0$


---

### 2. Community Evolution Visualization

- Visualize the graph after each split using **distinct colors**.
- Maintain **stable spring layout** for node positions.
- Annotate each split with modularity gain:

$\Delta Q = \frac{s^\top B s}{4m}$

---

### 3. Computation of Centrality Measures

At each iteration, compute:

- Degree centrality  
- Betweenness centrality  
- Closeness centrality  
- Clustering coefficient  

All metrics are computed globally (on the full graph).

---

### 4. Tracking Metric Evolution

- Store all four metrics for each split iteration.
- Generate time-series plots (per-node and per-metric).
- Analyze trends, stability, and shifts in centrality.

---

### 5. Analytical Discussion

Include discussion on:

- Nodes that consistently remain structurally central  
- How recursive segmentation affects centralities  
- Comparison to the historical Karate Club division  

---

## Implemented Features

### Algorithmic Components

- Construction of subgraph-specific modularity matrices  
- Eigenvalue/eigenvector computation using `scipy.linalg.eigh`  
- Recursive splitting with eigenvalue-based stopping rule  
- Linear tree structure to store split history  

---

### Visualization Methods

- Stepwise plots showing graph evolution across splits  
- Stable spring layout  
- Color-coded communities  
- Modularity-gain annotations  

---

### Centrality Metric System

- Computation of all major centrality scores  
- Storage of metrics for each iteration  
- Multi-panel and per-node metric visualizations  

---

## Mathematical Background

### Modularity Matrix

$B = A - \frac{kk^\top}{2m}$

### Modularity Gain After Split

$\Delta Q = \frac{s^\top B s}{4m}$

### Stopping Criterion

$\lambda_1 \le 0 \quad \Rightarrow \quad \text{no further split}$

---


