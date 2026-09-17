# Trajectory Clustering Using Similarity Measures

## 📌 Overview

This project presents a comparative study of **trajectory clustering** using the **DBSCAN** algorithm with different trajectory similarity and distance measures.

The objective is to investigate how the choice of similarity measure affects the clustering of trajectories and to compare the resulting performance using clustering evaluation metrics.

The study is applied to GPS trajectories of taxis operating in **Beijing, China**.

---

## 🎯 Objectives

* Apply DBSCAN to trajectory data.
* Compute similarity/distance matrices between trajectories.
* Compare different trajectory similarity measures.
* Analyze the impact of the `eps` parameter on clustering.
* Evaluate clustering results using the **Silhouette Score**.
* Compare the execution time of the different similarity measures.

---

## 🧠 Methodology

The project follows these main steps:

1. Load and explore taxi trajectory data.
2. Preprocess GPS trajectory data using **scikit-mobility**.
3. Compute pairwise trajectory similarity/distance matrices.
4. Apply **DBSCAN** using precomputed distance matrices.
5. Test different `eps` values with `min_samples = 4`.
6. Measure the number of clusters and the proportion of anomalies.
7. Evaluate clustering quality using the Silhouette Score.
8. Compare execution time and clustering performance across similarity measures.

DBSCAN is particularly suitable because it is density-based, does not require specifying the number of clusters in advance, can identify clusters of different shapes, and treats isolated trajectories as noise.

---

## 📏 Similarity & Distance Measures

The project investigates several approaches for comparing trajectories:

* **Dynamic Time Warping (DTW)** – handles temporal distortions between trajectories.
* **Fréchet Distance** – considers the position and ordering of points along trajectories.
* **Partial Curve Mapping (PCM)** – compares trajectories using partially matching curves.
* **Hausdorff Manhattan Distance**
* **Hausdorff Euclidean Distance**
* **Hausdorff Chebyshev Distance**

These measures are used to construct pairwise distance matrices that are subsequently provided to DBSCAN.

---

## 🚕 Dataset

The case study uses GPS mobility data from approximately **100 taxis operating in Beijing during February 2008**.

The dataset contains spatial and temporal information, including taxi identifiers, timestamps, latitude, and longitude coordinates.

Expected input structure:

```text
taxi_id | time | lat | long
```

---

## 🛠️ Technologies & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Scikit-Mobility
* SimilarityMeasures
* Hausdorff
* Jupyter Notebook

Main libraries used in the notebook include:

```python
import pandas as pd
import numpy as np
import skmob

from sklearn.cluster import DBSCAN
from similaritymeasures import dtw
from similaritymeasures import frechet_dist
from similaritymeasures import pcm
from similaritymeasures import area_between_two_curves
from hausdorff import hausdorff_distance
```

---

## 📊 Evaluation

For each similarity measure, the project analyzes:

* Number of generated clusters
* Proportion of detected anomalies/noise
* Silhouette Score
* Execution time
* Influence of the DBSCAN `eps` parameter

The project emphasizes that selecting an appropriate similarity measure and DBSCAN configuration is an important part of trajectory clustering.

---

## 📁 Project Structure

```text
Trajectory-Clustering-Similarity-Measures/
│
├── Comparison_of_Similarity_Measures_for_trajectory_clustering.ipynb
├── taxi_trajectory_data.csv
└── README.md
```

---

## 🚀 Installation

Install the required Python packages:

```bash
pip install pandas numpy matplotlib scikit-learn
pip install scikit-mobility similaritymeasures hausdorff
```

Then open the notebook:

```bash
jupyter notebook
```

and run:

```text
Comparison_of_Similarity_Measures_for_trajectory_clustering.ipynb
```

---

## 🎓 Academic Context

**Project:** Comparison of Similarity Measures for Trajectory Clustering

**Program:** Master Professional in Data Science for Business

**Institution:** Institut Supérieur de Gestion de Tunis (ISGT)

**Academic Year:** 2023–2024



---

## 📚 References

The project is based on trajectory clustering concepts, DBSCAN, and trajectory similarity measures including DTW, Fréchet Distance, LCSS, PCM, and Hausdorff-based distances.

---

## 📌 Conclusion

This project provides a comparative framework for studying the influence of different trajectory similarity measures on DBSCAN-based trajectory clustering. The experimental analysis highlights the importance of selecting an appropriate distance measure and clustering configuration according to the characteristics of the trajectory data.
