# Melbourne-Short-Term-Rental-Analytics-Airbnb-Price-Prediction
## Project Overview
This project is a predictive analytics submission for a Macquarie University competition that forecasts Airbnb listing prices in Melbourne, Australia. The goal is to build a complete analytics workflow from data preparation, feature engineering, and model training to final Kaggle-style forecast submission.
Link to the competiton: https://www.kaggle.com/competitions/asba-predictive-analytics-competition/overview
## Competition Information
- **Competition:** Melbourne Airbnb Price Prediction
- **Start date:** 26 April 2025
- **Close date:** 6 June 2025
- **Objective:** Predict the price of Airbnb listings in Melbourne using property, host, review, availability, and location data
- **Evaluation metric:** Mean Absolute Error (MAE)
- **Submission format:** CSV with two columns: `ID` and `price` (numeric, no `$` or commas)
- **Leaderboard:** Public leaderboard uses 50% of the test set; final leaderboard uses the remaining 50% and is revealed after competition close

## Dataset Description
The competition dataset contains the following files:
- `train.csv` — training set
- `test.csv` — test set
- `sample_submission.csv` — sample submission format
- `metaData.csv` — supplemental metadata describing each feature

### Dataset size and structure
- Training records: `3,735`
- Test records: `1,601`
- Target variable: `price`
- Data type: `csv`
- Total size: `25.23 MB`

### Key variables
- `price` — daily price in local currency (target)
- `ID` — unique listing identifier
- `name`, `description`, `neighborhood_overview`, `host_about` — text fields
- `host_response_time`, `host_response_rate`, `host_acceptance_rate`, `host_is_superhost` — host behavior and quality
- `latitude`, `longitude`, `neighbourhood`, `neighbourhood_cleansed` — location attributes
- `property_type`, `room_type`, `accommodates`, `bathrooms`, `bedrooms`, `beds` — listing details
- `amenities` — JSON string describing available features
- `minimum_nights`, `maximum_nights`, `availability_30`, `availability_365` — calendar and availability features
- `number_of_reviews`, `review_scores_rating`, `review_scores_cleanliness`, `review_scores_value` — review-based metrics

## Key Learning Outcomes
This competition is designed to test practical analytics skills on a real-world business problem. The main learning outcomes are:
- Problem understanding and framing
- Data cleaning and missing value handling
- Feature engineering from raw Airbnb listing information
- Model building and validation
- Forecasting using test data
- Model evaluation using MAE
- Leaderboard performance and competitive benchmarking

## Project Approach
The notebook follows a task-based process:
1. **Problem description and initial data analysis**
   - Defined the forecasting problem and its business value
   - Evaluated model performance using Mean Absolute Error
   - Categorised dataset variables
   - Assessed missingness in both train and test sets
   - Performed univariate analysis on key features

2. **Data cleaning and feature engineering**
   - Cleaned numerical fields such as `price`, `host_response_rate`, and `host_acceptance_rate`
   - Created new features from multi-value fields like `host_verifications` and `amenities`
   - Imputed missing values for both training and test datasets
   - Encoded categorical variables using both ordinal mapping and one-hot encoding

3. **Model training and tuning**
   - Explored tree-based models including Random Forest, XGBoost, and CatBoost
   - Used cross-validation to tune hyperparameters
   - Evaluated model results using log-transformed price and MAE
   - Selected the best performing model for final predictions

## Modeling Results
- **Best model:** `CatBoost`
- **Best cross-validated log-MAE:** `0.21305`
- **Random Forest log-MAE:** `0.2344`
- **XGBoost log-MAE:** `0.2145`
- **Final Kaggle score:** `268.713`
- **Leaderboard rank:** `5th` place at time of submission

## What makes this project strong
- Ranked 5th places / 100+ competitors
- Thorough EDA and careful handling of skewed price distribution
- Practical feature engineering from host verification and amenities data
- Robust missing-value imputation strategy
- Model selection based on cross-validated performance
- Final submission based on the model developed in the notebook

## How to use this repository
1. Open the notebook `Mebourne Short-Term Rental Analytics.ipynb`
2. Load the dataset files from the project folder
3. Run the notebook from top to bottom to reproduce the analysis
4. Export final predictions to a CSV with columns `ID` and `price`

## Notes
- The notebook is the main deliverable for competition grading and includes both code and written explanations
- Submission must be generated from code in the notebook, as required by the competition rules
- This README is intended to highlight the structure, process, and outcomes for portfolio presentation
