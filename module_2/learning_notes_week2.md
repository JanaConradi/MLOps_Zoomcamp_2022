# Learning notes -  Module 2

## 2.1 Introduction to Experiment tracking

Concepts:
* **ML experiment** is the process of building and training an ML model 
* Experiment run: every time we run an experiment (a trial), is called a run
* Run artifact: any file that is associated with an ML run
* Experiment metadata, everything that is related to the experiment

Experiment tracking:

In order to optimize and reproduce a ML model, the results of each experiment need to be documented. All revelant information from an ML experiment, e.g. source code, environment, data model, hyperparameters, metrics etc. have to be organized. One possibility is to store the information in spreadsheets. However, it is error prone (manual typing), lacks standard formats and collaboration possibilities.

A better way is using tracking tools like **MLflow**. Mlflow is an open source platform for machine learning lifecycles, basically an Python package (with pip installation). It contains four modules:
* Tracking 
* Models
* Model Registry
* Projects (will not be covered in this course)

MLflow tracking organizes the runs of an experiment, like parameters, metrics, metadata, artifacts etc. (an example for an artifact could be a visualization of your model) Further, it generates extra log information about code, version(git), time, author.




## 2.2 Getting started with MLFlow

* Installation of MLFow

```
pip install mlflow
```

-> best practice is to include the command into requirements.txt

* Launch the the MLFlow UI and create a table in SQLite to store the results

```
mlflow ui --backend-store-uri sqlite:///mlflow.db
```
uri: uniform resource identifier, name and/or locator of a online resource

* Connect to MLFLow

To keep track of the history when running a model. A simple way of adding tracking is defining a new run:

```
with mlflow.start_run():

    mlflow.set_tag("developer", "jana")

    mlflow.log_param("train-data-path", "./data/...")
    mlflow.log_param("valid-data-path", "./data/...")

    alpha = 0.01
    mlflow.log_param("alpha", alpha)
    lr = Lasso(alpha)
    lr.fit(X_train, y_train)

    y_pred = lr.predict(X_val)
    rmse = mean_squared_error(y_val, y_pred, squared=False)
    mlflow.log_metric("rmse", rmse)
```

## 2.3 Experiment tracking with MLflow

* Add hyperparameter tuning to the notebook
    To define the range of the hyperparameters, that shall be optimized, we use "search space", a dictionary with all hyperparameters and their ranges.

* Show how it looks like in MLFlow
* Select the best one
* Autolog


## 2.4 Model management

Experiment tracing is part of the model management. When the model is optimized, we want to save it and deploy it.

Wrong and error prone: manually save models in folders, versioning is hard, evolution of models untrackable



**NOTE:** Useful link with many MLOps-related articles: https://neptune.ai/blog

## 2.5 Model registry

## 2.6 MLflow in practice

## 2.7 Homework

Code Homework: (link)

Hours spent:

Social media post:

Just go with the flow

Keeping track on your work!


🙌 

✔️ Experiment tracking in machine learning


👀 



💻 Code: 

#mlopszoomcamp #datatalksclub #machinelearning #mlflow

*picture messy desk*

Link: https://www.linkedin.com/posts/janaconradi_mlopszoomcamp-mlopszoomcamp-datatalksclub-activity-6934508924033196034--oKD?utm_source=linkedin_share&utm_medium=member_desktop_web
