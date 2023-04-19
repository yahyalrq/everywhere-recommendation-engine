# Everywhere recommendation
<img align="center" width="700" height="150" src="assets/logo.jpg" > 


#
# Introduction

Everywhere is a mobile app that promotes events for users. In order to enhance the user experience, we propose implementing a recommendation system to determine which events a user is likely to attend. The system will take into account historical data, such as clubs the user has already visited, as well as demographic information, such as gender and nationality, and music preferences. Additionally, the recommendation system will also try to recommend other users who might have similar preferences, thus helping users find and connect with new friends who share their interests.

# Methodology

The recommendation system will be based on a hybrid version type of collaborative and content based filtering  approach, which utilises past user behaviour to predict future preferences. The system will use a [Dataset](/docs/source/datasets.md) to analyse the user's past event attendance history, demographic information, and music preferences to suggest events that align with the user's interests.

# Data Preprocessing
Before training the recommendation system models, we performed some data preprocessing. We first used centroid sampling and random undersampling techniques to handle class imbalance in the dataset. Additionally, we tried hypertuning the random undersampler to improve performance. After evaluating different models, we found that the best sampling method is the centroid sampling approach.

# Model development 

We implemented continuous integration and continuous deployment (CI/CD) to ensure secure development practices were followed. Many models have been tried in combination with undersampled data and orifinal data. Among these models we find random forest, LIGHTgbm without bagging and lightGBM with bagging. The best model was a combination of centroid resampling technique and light GBM without bagging. The score was 0.88 of roc_auc.

# Metrics

The metrics we used  throughout the development are Accuracy,confusion matrix, roc auc, precision, recall, f1-score, and Normalized Discounted Cumulative Gain .

# Model Deployment
After selecting the best model, we deployed it using Azure, Azure Databricks, and Azure Cosmos DB through the use of Bicep. We also implemented continuous integration and continuous deployment (CI/CD) to ensure secure development practices were followed.


# Conclusion
In summary, we developed a hybrid collaborative and content-based recommendation system for Everywhere that takes into account historical data and demographic information to suggest events that align with the user's interests. We also implemented various preprocessing techniques and evaluated different models to identify the best-performing one. Finally, we deployed the model using Azure and implemented CI/CD to ensure secure development practices.

## Create a virtual environment

```bash
python3 -m venv venv
```

## Activate the virtual environment

```bash
source venv/bin/activate
```

## Install the project package
```bash
pip install -e .
```
