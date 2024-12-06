# **Energy Price Forecasting**  
*Verizon AI Studio Challenge – Fall 2024*

---

## **Table of Contents**  
1. [Business Focus](#business-focus)  
2. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
3. [Data Preparation and Validation](#data-preparation-and-validation)  
4. [Modeling Approach](#modeling-approach)  
5. [Key Findings and Insights](#key-findings-and-insights)  
6. [Challenges](#challenges)  
7. [Acknowledgments](#acknowledgments)  

---

## **Business Focus**  
This project tackles the challenge of predicting electricity prices across U.S. states and sectors to optimize Verizon’s energy management strategies. With over $1 billion spent annually on electricity, Verizon seeks a robust forecasting solution to enhance budgeting, improve decision-making, and reduce operational costs.  

By building a predictive model, we aimed to:  
- Forecast electricity prices by state and sector through 2030.  
- Provide actionable insights into pricing trends to support strategic planning.  
- Develop an interactive dashboard for easy visualization of predictions and trends.  

Successful implementation will empower Verizon to anticipate price fluctuations, optimize energy procurement, and enhance operational efficiency.  

### **Objectives and Goals**  
- **Primary Objective**: Develop a predictive model for electricity prices that can help optimize energy strategies and inform policy decisions.  
- **Goals**:
  - Analyze historical energy pricing data through comprehensive exploratory data analysis (EDA).  
  - Engineer features that capture key patterns, such as seasonal trends and sector-based distinctions.  
  - Build and evaluate machine learning models to predict electricity prices accurately.  

---

## **Exploratory Data Analysis (EDA)**  
- Identified correlations among key variables (sales, revenue, customers, price).  
- Visualized distributions and trends across states and regions using tools like SweetViz, KLib, and Dabl.  
- Highlighted invalid data points (e.g., zero customers with non-zero revenue) and addressed them.  

---

## **Data Preparation and Validation**  

### **Dataset Description**  
- **Source**: Public U.S. electricity market data (2001–2024).  
- **Features**: Prices (cents/kWh), sales, revenue, customers, states, and sectors (residential, commercial, industrial).  

### **Data Preprocessing Steps**  
1. **Handling Missing Values**:  
   - Imputed missing data in the customers column using mean imputation to preserve correlations.  
2. **Addressing Invalid Data Points**:  
   - Removed records with contradictory zero-value combinations (e.g., customers = 0 but revenue ≠ 0).  
3. **Standardization**:  
   - Normalized numerical features (price, sales, revenue, customers) using Min-Max scaling.  
4. **Feature Leakage Mitigation**:  
   - Excluded dependent variables (sales, revenue, customers) from model training to avoid leakage.  
5. **Feature Engineering**:  
   - Created a Season feature to capture temporal trends in energy consumption.  

---

## **Modeling Approach**  

### **Selected Models**  
1. **ARIMA**:  
   - Chosen for its simplicity and effectiveness in time-series forecasting.  
   - RMSE: 11.5%.  
2. **SARIMA**:  
   - Tested but showed higher RMSE due to weak seasonality in the dataset.  
3. **Exploratory Models**:  
   - VAR and LSTM models were explored but deprioritized due to computational inefficiency and dataset limitations.  

### **Validation Strategy**  
- Split the dataset into 200 subsets (50 states × 4 sectors) to ensure accurate predictions for regional and sector-specific data.  
- Used train-test splits and cross-validation to assess model performance.  

---

## **Key Findings and Insights**  

### **Model Performance**  
- **ARIMA Model**:  
  - RMSE: 11.5%, making it the most reliable predictor.  

### **Visualizations**  
- Heatmaps of correlations.  
- Bar charts showing state-wise distributions of price, revenue, and sales.  
- Forecasting plots comparing predicted prices to actual values.  

### **Dashboard Highlights**  
- **Interactive Visualization**: Developed a Tableau dashboard with features such as:  
  - **Energy Price Mapping**: State-wise electricity prices in cents/kWh.  
  - **Price Trends**: Time-series analysis by sector (residential, commercial, industrial).  
  - **Price Rankings**: Top states based on electricity costs.  

### **Insights**  
- **Linear Price Growth**: Electricity prices are increasing linearly, driven by factors like infrastructure investments and market demand.  
- **Sector Variability**: Residential sectors show higher pricing trends compared to commercial and industrial sectors.  
- **Regional Disparities**: States like California and Alaska demonstrate significantly higher prices due to unique market conditions.  

### **Potential Next Steps**  
- Incorporate external factors such as weather data or fuel prices to improve predictions.  
- Experiment with deep learning models (e.g., LSTMs) for better time-series forecasting.  
- Deploy the model as an API for real-time electricity price prediction.  

---

## **Credits & Acknowledgments**  

We extend our gratitude to:  
- **Verizon AI Studio**: For providing this challenge and the opportunity to contribute meaningful solutions.  
- **Team Members**: Sneha Nangunoori, Pooja Ginjupalli, Kelly Chan, Emily-Ann Willix, and Annie Zhang, for their dedication and collaboration.  
- **Advisors**: Nandini Proothi, Christian Winter, and Frankie Delgado for their guidance and support.  
- **Break Through Tech AI Program**: For fostering this learning experience and connecting us with industry leaders.  
