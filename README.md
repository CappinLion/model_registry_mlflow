# model_registry_mlflow

MLflow is an open source platform for Machine Learning Lifecycles. It is commonly used for the the following perks:
1) MLflow Tracking: MLflow allows you to record and query experiments such as code, data, configs, results and (hyper-)parameters of your trained models

2) MLflow Models: Deploy ML models in diverse serving environments

3) MLflow Projects: Package data science code in a format to reproduce and reuse runs on any platform

4) Model Registry: Store, annotate, discover and manage models in a central repository

In order ro record MLflow runs, Mlflow allows you to log artifacts and FileStores either on the local machine (default approach) which is suitable for stand-alone development projects. Alternatively, you can also interface with a SQL database to log experiment runs and use S3 to log artifacts (best for collaborative environments).

With Python Version 3.9.6 within this project, mlflow conflicts with llvmlite because MLflow depends on shap. shap depends on numba. numbda depends on llvmlite.
Setting `poetry add numba==0.56` fixes the issue. MLFlow doesn't seem to have a fixed numba requirement and llvmlite = ">=0.39.0dev0,<0.40" of numba v0.56

TEST