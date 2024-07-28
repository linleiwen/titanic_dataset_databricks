<h2 align="center">
  Databricks-DataScience-Titanic<br/>
</h2>
<div align="center">
  <img alt="Demo" src="./img/dbsTitanic.png" />
</div>
<br/>
<center>
</center>
## Summary

A comprehensive walk-through of data science fundamentals using [PySpark](https://spark.apache.org/docs/latest/api/python/index.html), [MLflow](https://mlflow.org/), and the [Titanic dataset](https://www.kaggle.com/c/titanic/).

**Author**: Max (Leiwen) Lin  
**GitHub URL**: [https://github.com/linleiwen/titanic_dataset_databricks](https://github.com/linleiwen/titanic_dataset_databricks)

## Table of Contents
- [Intro to Spark and Databricks]
- [Setup and Environment]
- [Data Extraction]
- [Data Cleaning]
- [Introduction to Machine Learning]
- [Machine Learning Workflows]
- [Model Selection]
- [Model Serving]

## Introduction
In this project, we will explore the basics of data science using Databricks, PySpark, and MLflow. The Titanic dataset, a classic in the data science community, will serve as our case study. This guide aims to provide a step-by-step approach to data extraction, cleaning, machine learning workflows, model selection, and model serving.

## Setup and Environment
To get started, import the [`Databricks-DataScience-Titanic.dbc`](https://github.com/linleiwen/titanic_dataset_databricks/blob/main/Databricks-DataScience-Titanic.dbc) URL into your Databricks workspace. This will set up the necessary environment for our project.

### Requirements
- Databricks Account
- PySpark
- MLflow

## Data Extraction
The first step in our data science journey is extracting the Titanic dataset. We will use PySpark to read the dataset into our environment.

```python
# Sample code to read data
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("TitanicDataExtraction").getOrCreate()
df = spark.read.csv("/path/to/titanic.csv", header=True, inferSchema=True)
df.show()