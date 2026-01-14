# Flood Prediction in Uttarakhand (Machine Learning)

## Overview
This repository contains the machine learning component of a flood prediction system
for Uttarakhand. The work here focuses on data collection, preprocessing, and
training a Random Forest model to predict flood occurrences.

## My Contribution
- Collected and processed geospatial and environmental data using Google Earth Engine (GEE)
- Performed data cleaning and feature engineering
- Built and evaluated a Random Forest classification model
- Analyzed model performance using standard ML metrics

Frontend and backend components are not included in this repository.

## Tech Stack
- Python
- pandas
- numpy
- scikit-learn
- Jupyter Notebook

## Dataset
The dataset consists of approximately 1200 records derived from Google Earth Engine (GEE),
containing environmental and geospatial features relevant to flood prediction.

## Model Details
- Algorithm: Random Forest Classifier
- Task: Binary classification (Flood / No Flood)
- Evaluation Metrics: Accuracy, Precision, Recall, F1-score

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook flood_prediction_random_forest.ipynb
