# Conor-Hogan-exploratory-data-analysis-EDA-Zomato-Food-Delivery-Dataset

# Zomato Delivery Operations Analytics - EDA Project

## Project Overview
This project performs comprehensive exploratory data analysis on Zomato delivery operations data to uncover insights about delivery efficiency and customer satisfaction.

## Dataset
Food Delivert Dataset contains 45,584 rows and 20 columns, with a memory usage of 33.64 MB. This represents a substantial dataset for food delivery analysis with comprehensive coverage across multiple variables.

## Key Findings
Missing Values require attention:
   - Delivery_person_Ratings: 1,988 (4.19%)
   - Delivery_person_Age: 1,854 (4.06%)
   - Time_Orderd: 1,731 (3.80%)
   - City: 1,200 (2.63%)
No duplicate rows found.
Performance Metrics
   - Average delivery time: 26.29 minutes
   - Average rating: 4.63/5 stars
   - Delivery person age: Mean 29.73 years

Key Insights
Dataset shows good service quality with room for operational improvements. Missing values in critical fields need addressing before predictive modeling. Geographic and timing data well-distributed for delivery optimization analysis.


## Data cleaning & Pre-processing
This preprocessing creates a robust foundation for subsequent analysis and modeling tasks
Missing Value Treatment
   - Numerical columns (int64, float64): Missing values are filled with the median to maintain data distribution
   - Categorical columns (object): Missing values are filled with the mode (most frequent value)
   - Special handling: When the mode is empty for categorical columns, 'Unknown' is used as a placeholder

Data Type Conversions
Several datetime conversions were performed to enable time-based analysis:
   - Order_Date: Converted to datetime format with 'coerce' error handling
   - Time_Orderd: Converted to datetime format
   - Time_Order_picked: Converted to datetime format
   - Combined datetime fields: Created new columns by combining date and time components for analysis


### Feature Engineering
The creation of actionable features for time series analysis, geospatial modeling, and performance evaluation
Time-Based Features
   - The code extracts comprehensive temporal information from the order datetime
   - Order Processing Time
   - Geospatial Distance Calculation
   - Delivery Performance Metrics
   - Rating Categorization

## EDA Visualizations
   - Distribution Analysis
   - Categorical Analysis
   - Time-Based Performance Charts

## Models
two machine learning approaches for delivery time prediction and rating categorization:
Delivery Time Prediction (Regression)

A Random Forest Regressor was trained to predict delivery times with strong performance:
   -  RMSE: 7.5530 minutes
   -  R² Score: 0.3533 (explains 35% of variance)

Top predictive features include delivery_speed (0.358762), distance_km (0.210201), delivery_person_ratings (0.187508), and multiple_deliveries (0.116880).

Two models were developed for predicting delivery person rating categories:

Logistic Regression:
   - Overall Accuracy: 0.6459 (64.59%)
   - Shows varying performance across rating categories, with "Good" ratings achieving the highest precision (0.80)

Random Forest Classifier:
   - Perfect Performance: 0.9999 accuracy (99.99%)
   - Achieves perfect precision, recall, and F1-scores (1.00) across all rating categories (Poor, Average, Good, Excellent)

## Summary
Further feature engineering might be required for person rating model. The categories might be causing overfitting.
Predicting ratings and delivery time efficiency could be very beneficial to the business. 
