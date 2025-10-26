#Time Series Forecasting and Anomaly Detection using ARIMA, SARIMAX, and Isolation Forest


Project Overview :

This project provides an integrated pipeline for forecasting time-series data and detecting anomalies using a hybrid approach that combines classical statistical models (ARIMA/SARIMAX) with modern
machine learning techniques (Isolation Forest).The system is designed to be scalable and robust across diverse applications such as finance, healthcare, and retail where temporal patterns and outliers 
are crucial for decision-making.


 Published in : 
 
 International Journal of Research Publication and Reviews,Vol 5, no 12, pp 475-479 December 2024 
 Research Paper - https://ijrpr.com/uploads/V5ISSUE12/IJRPR36074.pdf
 certificate - https://ijrpr.com/certificate/download.php?paper_id=22668


Architecture & Pipeline :

A[Data Loading (.xlsx)] --> B[Exploratory Data Analysis (EDA)]
B --> C[Preprocessing (Missing values & Encoding)]
C --> D[Stationarity Testing (ADF Test)]
D --> E[Time-Series Forecasting]
E --> F1[ARIMA Modeling]
E --> F2[SARIMAX Modeling]
C --> G[Outlier Detection (Z-score)]
C --> H[Anomaly Detection (Isolation Forest)]
F1 --> I[Model Evaluation & Visualization]
F2 --> I
G --> I
H --> I


Technical Stack :

Programming Language: Python 3
Libraries:
 pandas, numpy: Data handling
 matplotlib, seaborn: Visualization
 statsmodels, pmdarima: ARIMA/SARIMAX modeling
 sklearn.ensemble: Isolation Forest for anomaly detection
 scipy.stats: Z-score for outlier detection


Methodology :

1. Data Loading & Inspection -
  Excel dataset loaded using pandas.read_excel()
  Checked for column types and null values

2. Exploratory Data Analysis (EDA) -
  Visualized categorical data distribution (e.g., type) using bar plots
  Box plots used to detect outliers in amount and newbalanceOrig

3. Preprocessing -
  Missing Values: Imputed with "None" for categoricals, -999 for numericals
  Encoding: Categorical columns encoded using LabelEncoder

4. Stationarity Check -
  Augmented Dickey-Fuller (ADF) test used on time-series columns
  Differencing applied if p-value > 0.05 to achieve stationarity

5. Forecasting Models -
  ARIMA -
    Auto ARIMA used for automatic selection of (p,d,q) parameters
    Evaluated using AIC, BIC, residual analysis
  SARIMAX -
    Seasonal and exogenous variables modeled with (p,d,q)x(P,D,Q,s)
    Used when time-series shows seasonal trend

6. Outlier Detection (Z-score) -
  Z-score calculated for each numerical feature
  Values with |Z| > 3 marked as outliers

7. Anomaly Detection (Isolation Forest) -
  i. Used for high-dimensional, multivariate data
 ii. Outputs binary labels (-1 for anomaly, 1 for normal)
iii. Visualized anomaly separation for interpretation


Results Summary :

1. ARIMA & SARIMAX provided stable and interpretable forecasts
2. Z-score identified extreme deviations in transaction amounts
3. Isolation Forest captured rare and unexpected patterns not visible to statistical methods
4. Visuals clearly showed trends, seasonality, and detected anomalies


Evaluation Metrics :

1. ADF p-values: to ensure stationarity
2. AIC/BIC: model selection for ARIMA/SARIMAX
3. Residual Diagnostics: for checking white noise
4. Anomaly Detection Count: to quantify rare events
5. Visual Interpretability: to validate results


Future Scope :

1. Integration of deep learning models (e.g., LSTM) for improved forecasting
2. Real-time streaming anomaly detection
3. Deployment via Flask/FastAPI + dashboard (e.g., Streamlit/Plotly)


Acknowledgments : 

Bhilai Institute of Technology, Raipur Project Mentors & Reviewers Team: Aparna Pandey Mam (Mentor) ,S. Shubham ,Rishi Nirmalkar ,Tanya Wadhwani ,V. Shivani


Contact :

For queries or collaborations, feel free to reach out: GMAIL - sshubham22062003@gmail.com LINKEDIN - https://www.linkedin.com/in/s-shubham-317359229
