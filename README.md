# Task-6

Here’s a **full documentation** for your KNN Breast Cancer project. You can include this as markdown in a notebook or as a separate report.

---

# **K-Nearest Neighbors (KNN) Classification – Breast Cancer Dataset**

## **1. Objective**

The goal of this project is to implement a **K-Nearest Neighbors (KNN) classifier** to predict whether a tumor is **malignant** or **benign** based on the **Breast Cancer Wisconsin (Diagnostic) dataset**.

Key objectives:

* Preprocess real-world dataset
* Scale numeric features
* Find optimal K using cross-validation
* Evaluate the model using metrics like accuracy and confusion matrix
* Visualize KNN decision boundaries in 2D space using PCA

---

## **2. Dataset**

* **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29)
* **Samples:** 569
* **Features:** 30 numeric features (mean, standard error, worst of cell measurements)
* **Target:** 2 classes

  * 1 → Malignant (cancerous)
  * 0 → Benign (non-cancerous)

**Preprocessing steps:**

1. Map categorical diagnosis to numeric labels (`M=1`, `B=0`)
2. Split into **train-test sets** with stratification to preserve class balance
3. Standardize features using **StandardScaler**



## **3. Model**

* **Algorithm:** K-Nearest Neighbors (KNN)
* **Hyperparameter tuning:** Number of neighbors (K) tested from 1 to 20 using **GridSearchCV** with 5-fold cross-validation
* **Distance metric:** Euclidean (default)

**Rationale:** KNN is a **distance-based classifier**, making feature scaling critical for performance.



## **4. Evaluation Metrics**

* **Accuracy:** Measures overall correctness of the classifier
* **Confusion Matrix:** Shows true positives, false positives, true negatives, and false negatives
* **Classification Report:** Includes precision, recall, F1-score per class

**Example Output:**

```
Accuracy: 0.95
Confusion Matrix:
[[...]]
Classification Report:
             precision    recall  f1-score   support
   Benign       0.97       0.95      0.96       107
 Malignant      0.92       0.95      0.94        64
```

## **5. K vs Accuracy Curve**

* Plots **accuracy** of the model on the test set for K = 1 to 20
* Helps identify the **optimal K** for best performance
* Ensures K selection is **data-driven**, not arbitrary



## **6. Visualization (PCA)**

* Applied **Principal Component Analysis (PCA)** to reduce 30 features to 2 dimensions for visualization
* Trained KNN on 2D PCA space to **plot decision boundaries**
* Highlights **training points** (solid colors) and **test points** (yellow star markers)
* Visual representation helps understand **model behavior** and **class separation**



## **7. Industry-Level Enhancements**

1. **Feature scaling** – required for distance-based algorithms
2. **Cross-validation** – robust K selection using `GridSearchCV`
3. **K vs Accuracy plot** – supports hyperparameter analysis
4. **PCA visualization** – interpretable 2D representation of high-dimensional data
5. **Comprehensive evaluation metrics** – accuracy, confusion matrix, classification report



## **8. Conclusion**

* The KNN classifier achieved **high accuracy (>90%)** on the Breast Cancer dataset
* Optimal **K** is selected using **cross-validation**
* PCA visualization confirms **good class separation**
* The workflow demonstrates **industry-ready ML pipeline practices** for tabular classification tasks

