# 🌸 Clustering des Iris : Identifier des Groupes Naturels dans les Fleurs

> 🎯 *Objectif : Identifier des classes homogènes d’iris sans utiliser les étiquettes d’espèces — en utilisant uniquement leurs caractéristiques physiques.*

Ce notebook Jupyter (`Clustering_Iris.ipynb`) met en œuvre une **analyse non supervisée** avec l’algorithme **K-Means** pour regrouper les fleurs d’iris en **3 classes naturelles**, basées sur la longueur et la largeur de leurs sépales et pétales.

---

## 🌿 Contexte & Objectif

Le jeu de données **Iris** est l’un des plus célèbres en Machine Learning. Il contient 150 échantillons de 3 espèces d’iris :
- *Iris setosa*
- *Iris versicolor*
- *Iris virginica*

Chaque échantillon possède 4 mesures :
- `SepalLength` → Longueur du sépale
- `SepalWidth`  → Largeur du sépale
- `PetalLength` → Longueur du pétale
- `PetalWidth`  → Largeur du pétale

> 🤔 **Dans ce projet, on fait comme si on ne connaissait pas les espèces !**  
> On va laisser l’algorithme **K-Means** découvrir tout seul les groupes naturels — c’est ce qu’on appelle le **clustering (ou segmentation)**.

---

## 👥 Pour qui est ce projet ?

| Public | Ce qu’il y trouvera |
|--------|----------------------|
| 👩‍🎓 **Étudiants en data / stats / ML** | Un tutoriel simple et visuel pour comprendre le clustering avec K-Means, étape par étape. |
| 👨‍🏫 **Enseignants** | Un exemple pédagogique parfait pour illustrer l’apprentissage non supervisé et la visualisation de clusters. |
| 👩‍💻 **Data Scientists juniors** | Une implémentation rapide et propre avec `sklearn`, `pandas`, `seaborn` — idéal pour réviser ou s’inspirer. |
| 👔 **Curieux / Non-techniciens** | Des explications simples, des graphiques parlants, et une démonstration concrète de comment les machines “trouvent des groupes” dans les données. |

---

## ⚙️ Étapes du Projet

### 1. 🔍 Lecture & Exploration des Données
- Chargement du fichier `iris.csv` avec `pandas`.
- Attribution des noms de colonnes : `SepalLength`, `SepalWidth`, `PetalLength`, `PetalWidth`.
- Visualisation des distributions et relations avec `sns.pairplot(..., diag_kind='kde')`.

### 2. 🧠 Clustering avec K-Means
- Import de `KMeans` depuis `sklearn.cluster`.
- Création de **3 clusters** (car on sait qu’il y a 3 espèces — mais l’algo, lui, ne le sait pas !).
- Entraînement du modèle sur les 4 variables mesurées.
- Récupération des **centres de clusters** (points moyens représentatifs de chaque groupe).

### 3. 🏷️ Attribution des Clusters
- Chaque fleur est assignée à un cluster (0, 1 ou 2).
- Ajout d’une colonne `Cluster` au DataFrame pour visualiser les résultats.
- Comptage des individus par cluster avec `np.unique(..., return_counts=True)`.

### 4. 📊 Visualisation des Résultats
- Nouveau `pairplot` avec coloration par cluster (`hue="Cluster"`).
- Comparaison visuelle : les groupes trouvés par K-Means correspondent-ils aux vraies espèces ? *(Spoiler : oui, très bien !)*

---

## 🧩 Technologies & Bibliothèques Utilisées

```python
import pandas as pd           # Manipulation des données
import numpy as np            # Calculs numériques
import seaborn as sns         # Visualisations avancées
import matplotlib.pyplot as plt # Graphiques
from sklearn.cluster import KMeans  # Algorithme de clustering
from IPython.display import Image   # Affichage d’image explicative
