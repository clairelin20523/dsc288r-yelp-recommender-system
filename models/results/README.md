# dsc288r-yelp-recommender-system
Project Group 07: Yelp-Powered Insights: Building a Business Recommender System

## Overview
Our project aims to create a recommendation algorithm to help users discover businesses that match their preferences while also gaining insights into user behavior. By analyzing the businesses users have reviewed and comparing them with predicted recommendations, the model can refine its suggestions, enhancing personalization. 
Data Source: Yelp Complete Open Dataset 2024 - Kaggle

Link: https://www.kaggle.com/datasets/adamamer2001/yelp-complete-open-dataset-2024

## Summary

Online platforms have grown rapidly due to user-centered designs that make products and services more accessible through their user-friendly interfaces. One component of the user-centered design has been recommender systems. These recommender systems leverage big data to analyze users’ interactions, similar user experiences, and overall reviews. Recommender systems enhance user engagement and drive possible user retention, which in turn helps to create revenue growth. Platforms (such as Yelp) are always looking for ways to enhance these algorithms to better understand how the user behaves. The goal of this project is to understand users preferences and to give better recommendations on what businesses to visit next. The first model was an item-based collaborative filtering technique to find similar businesses and return back highly rated businesses that the user had not reviewed. The second and third models were K-Nearest Neighbors (KNN) and Singular Value Decomposition (SVD) for predicting companies that users have likely reviewed before and to predict the rating a user could give for a business that they have not seen before. By improving the accuracy and efficiency of recommendations, this project aims to drive increased user engagement and retention, ultimately generating more revenue and growth for online platforms.

# Model 5 file  - Predicts likelihood user will review a business and predicts the rating a user will give for a business

## Setup Instructions - This is for compiling the code and running it on a local server. Also ran this in Anaconda.

### 1. Clone the Repository
```sh
git clone https://github.com/clairelin20523/dsc288r-yelp-recommender-system.git
cd dsc288r-yelp-recommender-system
```

### 2. Install Dependencies
Using pip:
```sh
pip install -r requirements.txt
```

### 3. Download Dataset 
This model uses Yelp dataset files. Ensure they are placed in the same directory as the notebook:
- `yelp_academic_dataset_business.json`
- `yelp_academic_dataset_review.json`

You can download them from [Yelp Open Dataset](https://www.yelp.com/dataset).

### 4. Run the Notebook  After loading the Jupyter Lab run line by line.
```sh
jupyter lab
```

### NOTE ################
# If you do not want to run all of this code you can just run the bottom lines which will use the existing .pkl files that were created from the hyperparameters to create the model.
##### Example of how to run this code is below. This example will load both KNN and SVD and run the prediction on one user/business to predict if the user would review the business.

```
 from surprise import dump
    model_file = 'svd_binary.pkl'
   loaded_model = dump.load(model_file)[1]
   knn_file = 'knn_binary.pkl'
   knn_model = dump.load(knn_file)[1]

   user_id = "BL2YwAB7he2PrDIg31VQ"
   business_id = "H26zRyQkXXYzUZUOtppFcA"
   pred = loaded_model.predict(user_id, business_id)
   print(f"Predicted review status (0 or 1): {pred.est}")

   knn_pred = knn_model.predict(user_id, business_id)
   print(f"KNN Predicted review status: {knn_pred.est}")
```

Authors:
Claire Lin - cll015@ucsd.edu
Rongrong (Cassy) Xu - rox002@ucsd.edu
Timothy Indrieri - tindrieri@ucsd.edu
