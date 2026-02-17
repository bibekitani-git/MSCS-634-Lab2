# MSCS 634 Lab 2: Classification Using KNN and RNN Algorithms

## Purpose
This lab explores the classification performance of K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) using the Scikit-learn Wine dataset. The goal is to observe how hyperparameter tuning (k-value and radius) affects accuracy.

## Key Insights
* **KNN Performance:** Higher k-values often smooth out decision boundaries, but in this specific dataset, lower k-values (like 1 or 5) typically yield high accuracy because the wine classes are relatively distinct.
* **RNN Performance:** Radius selection is highly sensitive. If the radius is too small, a point might have no neighbors (leading to errors/outliers); if too large, it captures the entire dataset, losing local nuance.
* **Comparison:** KNN is generally more robust because it guarantees a fixed number of neighbors, whereas RNN's performance fluctuates significantly based on the density of the data points within the chosen radius.

## Challenges & Decisions
* **Outlier Handling:** In RNN, I used the `outlier_label='most_frequent'` parameter. This ensures the model doesn't crash if a test point has zero neighbors within the specified radius.
* **Feature Scaling:** (Optional Note) While not strictly required by the prompt, the Wine dataset features have different scales, which can impact distance-based models.
