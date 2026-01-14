# Flood Prediction in Uttarakhand (Machine Learning + GEE)

## Overview
This repository contains the machine learning part of a flood risk prediction system for Uttarakhand. It covers data collection from Google Earth Engine (GEE), feature engineering, model training in Python, and a simple console-based tool to query live flood risk for any location and month. [web:59]

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
- Collected and processed geospatial and environmental data using GEE. [web:59]  
- Performed data cleaning and feature engineering for flood prediction.  
- Trained and evaluated a Random Forest model for binary classification (flood / no flood).  
- Integrated the trained model with live GEE data to predict flood risk for arbitrary coordinates and months.  
- Built a simple interactive console tool to test the model for real historical cases (for example, Haridwar and Rishikesh in 2013). [web:59]

## Tech Stack
- Python  
- pandas, numpy  
- scikit-learn  
- Google Earth Engine Python API [web:59]  
- Jupyter Notebook  

## Dataset
The training dataset contains roughly 1.2k samples derived from Google Earth Engine. Each record includes environmental and geospatial features such as rainfall, elevation, slope, and aspect, along with a binary label indicating whether a flood occurred. [web:59]

## Model Details
- **Algorithm:** Random Forest Classifier  
- **Task:** Binary classification (Flood / No Flood)  
- **Key Features:** GEE-derived rainfall and terrain variables  
- **Metrics:** Accuracy, precision, recall, F1-score  
- **Saved Model:** `flood_model.pkl`

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/25f1001872/flood-prediction-uttarakhand-ml.git
cd flood-prediction-uttarakhand-ml

2. Install dependencies
bash
pip install -r requirements.txt
3. Set up Google Earth Engine
You need a GEE account and credentials. Configure authentication (for example, using your usual ee.Authenticate() / ee.Initialize() flow or environment variables) so the notebooks can access GEE. [web:59]

4. Train or inspect the model
Open the training notebook:

bash
jupyter notebook flood_prediction_ml_model.ipynb
Re-run the cells to reproduce training, evaluation, and model saving if needed.

5. Run live flood risk predictions
Open the GEE integration notebook:

bash
jupyter notebook gee_flood_api.ipynb
Then:

Run the cells that initialize GEE and load flood_model.pkl.

Run the cells that define the helper functions for rainfall and terrain extraction.

Run the cell that defines and calls flood_assessment().

In the console prompts, enter latitude, longitude, year, and month (or press Enter to use defaults).

The notebook prints a summary with predicted probability and risk level (LOW / MODERATE / HIGH).
