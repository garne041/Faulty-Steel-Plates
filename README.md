# Model Deployment Project - Faulty Steel Plates

The Semion Research Center of Sciences of Communication released a dataset based on image characteristics of faulty steel plates. Six types of defects () plus an "Other" categories were identified. The input feature space was based on 27 indicators supplied by the Centro Sviluppo Materiali. 

Objectives:
- Load the original csv data into a Databricks table for tracking
- Analyze the anonymized data of 1941 across the 7 identified defects
- Build a machine learning model to predict the top 3 defects which made up over 75% of all identifiable defects
- Utilize explainability packages on the model to identify possible actions an operator could take to reduce defects moving forward
- Put this model into production on Databricks by using experiment tracking, model registry, and model deployment 


|--- images/ :Contains all images
|--- Data Load - Faulty Steel Plates.ipynb :Loading data onto Databricks into a table
