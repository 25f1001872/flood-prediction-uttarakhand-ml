# Flood Prediction in Uttarakhand (Machine Learning + GEE)

## Overview
This repository contains the machine learning part of a flood risk prediction system for Uttarakhand. It covers data collection from Google Earth Engine (GEE), feature engineering, model training in Python, and a simple console-based tool to query live flood risk for any location and month. 

## Academic Context
This project was developed as part of **CEC201 – App Development: Geospatial Solutions for Civil Engineering**  
(Civil Engineering Department, IIT Roorkee).

The coursework required identifying a real-world civil engineering problem in the Uttarakhand region, designing a geospatial solution, and demonstrating its utility through data-driven analysis, case studies, and impact assessment. Flood prediction was selected under the *Flood* domain.

## Problem Statement & Objective
Frequent flood events in Uttarakhand pose significant risks to lives, infrastructure, and economic activity.  
The objective of this project was to develop a machine learning–based flood risk prediction module using geospatial and environmental data, which could support early warning, planning, and disaster preparedness.

## Contents
- `flood_prediction_ml_model.ipynb`  
  - Exploratory data analysis  
  - Feature engineering  
  - Training and evaluation of a Random Forest classifier  
  - Saving the trained model to `flood_model.pkl`  

- `gee_flood_api.ipynb`  
  - Loading the trained model  
  - Connecting to Google Earth Engine  
  - Fetching rainfall and terrain features (CHIRPS + DEM)  
  - Command-line style predictor (`flood_assessment()`) that uses live GEE data  

- `Aqualert_data.csv`  
  - Processed dataset used for training (flood / no-flood labels with environmental features)

## My Contribution
- Collected and processed geospatial and environmental data using GEE.   
- Performed data cleaning and feature engineering for flood prediction.  
- Trained and evaluated a Random Forest model for binary classification (flood / no flood).  
- Integrated the trained model with live GEE data to predict flood risk for arbitrary coordinates and months.  
- Built a simple interactive console tool to test the model for real historical cases (for example, Haridwar and Rishikesh in 2013). 

## Tech Stack
- Python  
- pandas, numpy  
- scikit-learn  
- Google Earth Engine Python API  
- Jupyter Notebook  

## Dataset
The training dataset contains roughly 1.2k samples derived from Google Earth Engine. Each record includes environmental and geospatial features such as rainfall, elevation, slope, and aspect, along with a binary label indicating whether a flood occurred. 
The model was tested using historical flood events, including the 2013 Uttarakhand floods (Haridwar and Rishikesh), as part of the required case-study demonstration.

## Model Details
- **Algorithm:** Random Forest Classifier  
- **Task:** Binary classification (Flood / No Flood)  
- **Key Features:** GEE-derived rainfall and terrain variables  
- **Metrics:** Accuracy, precision, recall, F1-score  
- **Saved Model:** `flood_model.pkl`

## Documentation
The official course brief and evaluation guidelines for **CEC201 – App Development: Geospatial Solutions for Civil Engineering** are provided in the `/docs` folder for reference.

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/25f1001872/flood-prediction-uttarakhand-ml.git
cd flood-prediction-uttarakhand-ml
```
### 2. Install dependencies
```bash
pip install -r requirements.txt
```
### 3. Set up Google Earth Engine
You need a GEE account and credentials. Configure authentication (for example, using your usual `ee.Authenticate()` / `ee.Initialize()` flow or environment variables) so the notebooks can access GEE. 

### 4. Train or inspect the model
Open the training notebook:

```bash
jupyter notebook flood_prediction_ml_model.ipynb
```
Re-run the cells to reproduce training, evaluation, and model saving if needed.


### 5. Run live flood risk predictions
Open the GEE integration notebook:

```bash
jupyter notebook gee_flood_api.ipynb
```
Then:

1.Run the cells that initialize GEE and load flood_model.pkl.

2.Run the cells that define the helper functions for rainfall and terrain extraction.

3.Run the cell that defines and calls flood_assessment().

4.In the console prompts, enter latitude, longitude, year, and month (or press Enter to use defaults).

5.The notebook prints a summary with predicted probability and risk level (LOW / MODERATE / HIGH).
