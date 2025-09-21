# Iris Clustering: Identifying Natural Groups in Flowers

> *Objective: Identify homogeneous classes of iris flowers without using species labels — relying solely on their physical characteristics.*

This Jupyter notebook (`Clustering_Iris.ipynb`) implements an **unsupervised analysis** using the **K-Means** algorithm to group iris flowers into **3 natural clusters**, based on sepal and petal length and width measurements.

---

## Context & Objective

The **Iris** dataset is one of the most famous in Machine Learning. It contains 150 samples from 3 iris species:
- *Iris setosa*
- *Iris versicolor*
- *Iris virginica*

Each sample includes 4 measurements:
- `SepalLength` → Sepal length
- `SepalWidth`  → Sepal width
- `PetalLength` → Petal length
- `PetalWidth`  → Petal width

> 🤔 **In this project, we pretend we don’t know the species labels!**  
> We let the **K-Means** algorithm discover natural groupings on its own — this is known as **clustering (or segmentation)**.

---

## Target Audience

| Audience | What They Will Find |
|----------|----------------------|
| **Students in Data / Stats / ML** | A simple, visual tutorial to understand K-Means clustering, step by step. |
| **Teachers** | A perfect pedagogical example to illustrate unsupervised learning and cluster visualization. |
| **Junior Data Scientists** | A quick, clean implementation using `sklearn`, `pandas`, and `seaborn` — ideal for review or inspiration. |
| **Curious Non-Technical Readers** | Simple explanations, intuitive plots, and a concrete demonstration of how machines “find groups” in data. |

---

## Project Steps

### 1. Data Loading & Exploration
- Load `iris.csv` using `pandas`.
- Assign column names: `SepalLength`, `SepalWidth`, `PetalLength`, `PetalWidth`.
- Visualize distributions and pairwise relationships using `sns.pairplot(..., diag_kind='kde')`.

### 2. Clustering with K-Means
- Import `KMeans` from `sklearn.cluster`.
- Create **3 clusters** (we know there are 3 species — but the algorithm doesn’t!).
- Train the model on all 4 measured features.
- Retrieve **cluster centroids** (mean representative points of each group).

### 3. Cluster Assignment
- Assign each flower to a cluster (0, 1, or 2).
- Add a `Cluster` column to the DataFrame for result visualization.
- Count members per cluster using `np.unique(..., return_counts=True)`.

### 4. Visualization of Results
- Generate a new `pairplot` colored by cluster (`hue="Cluster"`).
- Visual comparison: Do the clusters found by K-Means match the true species? *(Spoiler: Yes, very well!)*

---

## Technologies & Libraries Used

```python
import pandas as pd           # Data manipulation
import numpy as np            # Numerical computations
import seaborn as sns         # Advanced visualizations
import matplotlib.pyplot as plt # Plotting
from sklearn.cluster import KMeans  # Clustering algorithm
from IPython.display import Image   # Display explanatory image
