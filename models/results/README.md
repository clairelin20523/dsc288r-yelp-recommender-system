# Model 5 - Predicts likelihood user will review a business and predicts the rating a user will give for a business

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
##### Example of how to run this code is below

## from surprise import dump
## model_file = 'svd_binary.pkl'
## loaded_model = dump.load(model_file)[1]  

## knn_file = 'knn_binary.pkl'
## knn_model = dump.load(knn_file)[1]

## user_id = "BL2YwAB7he2PrDIg31VQ"
## business_id = "H26zRyQkXXYzUZUOtppFcA"
## pred = loaded_model.predict(user_id, business_id)
## print(f"Predicted review status (0 or 1): {pred.est}")

## knn_pred = knn_model.predict(user_id, business_id)
## print(f"KNN Predicted review status: {knn_pred.est}")

## This example will load both KNN and SVD and run the prediction on one user/business to predict if the user would review the business.
