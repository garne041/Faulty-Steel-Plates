# Model Deployment Project - Faulty Steel Plates

The Semion Research Center of Sciences of Communication released a dataset based on image characteristics of faulty steel plates. Six types of defects (Pastry, Z Scratch, K Scratch, Stains, Dirtiness, and Bumps) plus an "Other" categories were identified. The input feature space was based on 27 indicators supplied by the Centro Sviluppo Materiali. 

## Objectives:
- Load the original csv data into a Databricks table for tracking
- Analyze the anonymized data of 1941 across the 7 identified defects
- Build a machine learning model to predict the top 3 defects which made up over 75% of all identifiable defects
- Utilize explainability packages on the model to identify possible actions an operator could take to reduce defects moving forward
- Put this model into production on Databricks by using experiment tracking, model registry, and model deployment 

## Project Overview

```
.
├── images/                                                             : Contains all images
├── Data Load - Faulty Steel Plates.ipynb                               : Loading data onto Databricks into a table
├── Model Testing, Fit, and Feature Importance.ipynb                    : EDA, feature engineering, model training, feature importance
├── Experiment Tracking, Model Registry, and Model Deployment.ipynb     : Model productionalization
├── LICENSE                                                             : License
└── README.md                                                           : Project Report 
```

## ML Model to Predict Top 3 Identifiable Defects 

This data can be used to predict which type of defect based on the 27 features. With expanded understanding of the features, a model like this could be used to recommend process actions to prevent these defects in the future. In this project, I scaled the data before applying PCA to identify relationships between the features. After that, I used Pycaret with PCA enabled to compare and tune models. 

Since the major focus of this project is to demonstrate putting models in production, the model testing notebook was to create a working viable model which would be needed to demonstrate productionalization. I've broken it down into three sections: experiment tracking, model registry, and model deployment inside of Databricks using mlflow.

## Skills Reviewed: 
### Experiment Tracking
- Incorporating the preprocessing steps of data cleaning and scaling into the mlflow model
- Saving PCA variance plots and PCA components csv as artifacts for future reference
- Converting the PCA transform into an mlflow predict method

### Establishing Context
- Generating signatures to define input and output schemas for the model to validate model data consistency before and after training.
- Generating Conda environment to make sure the same versions of relevant packages are used every time this model is trained or served. 

### Model Registry 
- Establishing a centralized model store across the entire model lifecycle stage
- Registering the preprocessing/PCA model as well as the machine learning model
- Capturing model lineage and metadata
- Tracking model hyperparameters, performance metrics, source code, and artifacts. 

### Model Deployment for Online Serving
- Updating most recent version and upgrading from Staging to Production 
- Predicting with current model in production
