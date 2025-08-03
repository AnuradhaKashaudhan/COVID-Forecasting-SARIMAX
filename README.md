# COVID-Forecasting-SARIMAX

# 📊 COVID-19 Forecasting Using ARIMA and SARIMAX

### 🔬 Project Title:
**Forecasting COVID-19 Active Cases and Deaths Using Time Series Models**

This project analyzes and forecasts the progression of COVID-19 using time series forecasting models. The data used includes confirmed cases, deaths, recoveries, and active cases over time across multiple countries.

Two statistical forecasting models are compared:

- **ARIMA (AutoRegressive Integrated Moving Average)**
- **SARIMAX (Seasonal ARIMA with eXogenous factors)**

The primary goal is to determine which model provides better accuracy and reliability in forecasting COVID-19 trends.

---

## 📁 Dataset

- Source: [Johns Hopkins University CSSE COVID-19 Dataset](https://github.com/CSSEGISandData/COVID-19)
- Columns:
  - `Province/State`
  - `Country/Region`
  - `Lat`
  - `Long`
  - `Date`
  - `Confirmed`
  - `Deaths`
  - `Recovered`
  - `Active`
  - `WHO Region`

---

## 📚 Libraries Used

python
import pandas as pd           # For data handling
import numpy as np            # For numerical operations
import matplotlib.pyplot as plt   # For visualizations
import seaborn as sns             # For better visual aesthetics
import statsmodels.api as sm      # For time series modeling
from statsmodels.tsa.statespace.sarimax import SARIMAX
from statsmodels.tsa.arima.model import ARIMA
from sklearn.metrics import mean_squared_error   # For model evaluation
from math import sqrt                           # For RMSE calculation
import gradio as gr                             # For deploying interactive UI

🔄 Preprocessing
Filtered the dataset to focus on global totals.

Grouped data by Date and aggregated case numbers.

Checked and handled missing values.

Converted Date to a datetime format for time series operations.

🧠 Modeling
ARIMA Model
Focuses on non-seasonal data trends.

Model configuration: (p, d, q) tuned using observations and performance metrics.

SARIMAX Model
Incorporates seasonality and external regressors.

Offers improved accuracy over ARIMA for pandemic data which shows weekly/monthly patterns.

📊 Evaluation
Metric Used: RMSE (Root Mean Squared Error)

Results:

ARIMA RMSE: 149,692.46

SARIMAX RMSE: 69,679.74 ✅ (Better)

SARIMAX outperformed ARIMA due to its ability to capture seasonality in case trends.

🎛️ Gradio Web App
An interactive web interface was created using Gradio for:

Forecasting active cases or deaths.

Visualizing prediction graphs.

Exporting the results to CSV.

💡 Conclusion
SARIMAX is better suited for forecasting COVID-19 due to seasonal effects in the data.

Time series modeling can aid public health authorities in planning and resource allocation.






