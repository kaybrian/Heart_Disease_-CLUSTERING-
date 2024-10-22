#  Heart Disease Dataset Analysis


# Heart Disease Analysis

This project focuses on clustering and analyzing the **Heart Disease Dataset** from the UCI Machine Learning Repository. The dataset contains 303 instances with 14 attributes, including age, sex, chest pain type, blood pressure, serum cholesterol, and a target variable indicating the presence or absence of heart disease.

The analysis involves clustering patients into groups based on their medical history, identifying potential risk factors for heart disease, and evaluating the performance of various clustering algorithms.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Data Preprocessing](#data-preprocessing)
- [Clustering Algorithms Applied](#clustering-algorithms-applied)
- [Dimensionality Reduction](#dimensionality-reduction)
- [Model Evaluation](#model-evaluation)
- [Results and Conclusions](#results-and-conclusions)
- [Installation and Usage](#installation-and-usage)

## Project Overview
The objective of this project is to cluster patients based on their medical history to gain insights into groups that are at higher risk for heart disease. We used various clustering algorithms like **K-means**, **Hierarchical Clustering**, and **DBSCAN** to create patient groups. Additionally, **Gaussian Mixture Models (GMMs)** were employed to identify risk factors associated with heart disease.

To evaluate the clustering algorithms, we used metrics such as the **Davies-Bouldin Index** and **Silhouette Score**. Principal Component Analysis (PCA) and t-SNE were applied to visualize the clusters and explore the relationships between variables.

## Dataset
The heart disease dataset used in this project contains the following 14 attributes:
- **Age**: Patient's age in years
- **Sex**: Gender (1 = male, 0 = female)
- **cp**: Chest pain type (categorical)
- **trestbps**: Resting blood pressure (mm Hg)
- **chol**: Serum cholesterol (mg/dl)
- **fbs**: Fasting blood sugar > 120 mg/dl (1 = true, 0 = false)
- **restecg**: Resting electrocardiographic results (categorical)
- **thalach**: Maximum heart rate achieved
- **exang**: Exercise-induced angina (1 = yes, 0 = no)
- **oldpeak**: ST depression induced by exercise relative to rest
- **slope**: Slope of the peak exercise ST segment (categorical)
- **ca**: Number of major vessels colored by fluoroscopy
- **thal**: Thalassemia (categorical)
- **target**: Presence or absence of heart disease (1 = disease, 0 = no disease)

## Exploratory Data Analysis (EDA)
Before performing clustering, an exploratory data analysis was conducted to understand the distribution of each feature and the relationships between them. The EDA includes:
- Descriptive statistics
- Correlation matrix to identify relationships between variables
- Visualization of key features using histograms and box plots

## Data Preprocessing
To ensure that the dataset is ready for clustering, we performed the following preprocessing steps:
- Handled missing values by imputing or removing them
- Scaled the numerical features using **StandardScaler** to normalize the data
- Encoded categorical variables using one-hot encoding

## Clustering Algorithms Applied
1. **K-means Clustering**:
   - Optimized the number of clusters (k) using the **Elbow Method** and **Silhouette Score**.
   - Applied K-means clustering with k=5 and k-means++ initialization.
2. **Hierarchical Clustering**:
   - Applied agglomerative hierarchical clustering and evaluated the clusters formed.
3. **DBSCAN**:
   - Applied Density-Based Spatial Clustering to group patients based on density.

## Dimensionality Reduction
We used **Principal Component Analysis (PCA)** and **t-SNE** to reduce the dimensionality of the data and visualize the clusters:
- PCA helped us understand the variance explained by different components and how the features contribute to the clustering.
- t-SNE provided a non-linear embedding of the clusters, giving us insights into how the clusters are formed.

## Model Evaluation
To evaluate the clustering performance, we used the following metrics:
- **Davies-Bouldin Index**: A lower value indicates better clustering.
  - K-means: 2.735
  - Hierarchical Clustering: 1.999
- **Silhouette Score**: Measures how similar each point is to its own cluster compared to others.

Based on the results, Hierarchical Clustering performed better than K-means in this dataset, with a lower Davies-Bouldin Index.

## Results and Conclusions
- Hierarchical clustering outperformed K-means in creating more distinct and compact clusters, based on the Davies-Bouldin Index.
- Gaussian Mixture Models helped identify the top risk factors associated with heart disease for each cluster. For example:
  - **Cluster 0**: Key risk factors include the number of major vessels (ca), resting blood pressure (trestbps), and ST depression (oldpeak).
  - **Cluster 4**: The major risk factor is fasting blood sugar (fbs), indicative of diabetes.
  
The results suggest that hierarchical clustering is more effective in grouping patients based on their medical history, and certain features like fasting blood sugar and exercise-induced angina play a key role in determining heart disease risk.

## Installation and Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/kaybrian/Heart_Disease_-CLUSTERING-.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Heart_Disease_-CLUSTERING-
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Open the Jupyter notebook `heart_disease.ipynb` and run the cells to reproduce the analysis and visualizations.
