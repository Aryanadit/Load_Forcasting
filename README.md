# 🎯 PJM East Load Forecasting: Machine Learning Pipeline

A **production-ready time series forecasting project** for hourly electricity load in the PJM East (PJME) region using pandas, scikit-learn, LightGBM, and XGBoost. This end-to-end pipeline is designed for easy reproduction, benchmarking, and deployment.

**Perfect for:**  
Portfolios, learning, and demonstrating ML skills for real-world time series forecasting.

---

## 🔍 Project Objectives

- **Forecast** hourly electricity load (MW) 24 hours ahead.
- **Benchmark** linear regression, LightGBM, and XGBoost on a real-world time series.
- **Optimize** model hyperparameters using cross-validation.
- **Visualize** and interpret predictions for grid operators and analysts.

---

## 📊 Dataset

- **Name:** PJM East (PJME) Hourly Energy Consumption
- **Source:** [Kaggle Dataset](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)
- **Size:** ~145,000 hourly records (2002–2018)
- **Columns:**  
  - **Datetime:** Timestamp (hourly, your local timezone)
  - **PJME_MW:** Actual load (megawatts)

---

## 🏗️ Feature Engineering & Pipeline

- **Lags:** Previous hour, day, and week values
- **Rolling Statistics:** Mean and standard deviation over past hours
- **Cyclical Time:** Encode hour of day and month with sine/cosine for smooth seasonality
- **Categorical:** Day of week, weekend flag
- **Train/Test Split:** Time-based, preserving temporal order
- **Validation:** TimeSeriesSplit for robust cross-validation
- **Hyperparameter Tuning:** RandomizedSearchCV on LightGBM

---

## 🧠 Model Comparison

| Model         | Test RMSE   | MAE      | R²        |
|---------------|------------|----------|-----------|
| Linear Regression | 962.04   | 662.90   | 0.978     |
| LightGBM          | 655.62   | 418.90   | 0.990     |
| XGBoost           | 769.54   | 510.52   | 0.986     |

**Production Model:**  
**Tuned LightGBM** achieved the lowest RMSE (559.97) and was used for final 24-hour ahead forecasting.

---

## 🛠️ Technologies Used

- **Python 3.11+**
- **pandas, numpy** (data manipulation)
- **scikit-learn** (metrics, cross-validation, linear models)
- **LightGBM, XGBoost** (gradient boosting)
- **matplotlib, seaborn** (visualization)
- **joblib** (model persistence)

---

## 🚀 Quick Start

1. **Clone the repository**
git clone https://github.com/Aryanadit/Load_Forcasting.git
cd Load_Forcasting
2. **Download dataset**  
Download [PJME_hourly.csv](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption) and place it in `data/` (or adjust path in notebook).
3. **Install dependencies**
pip install -r requirements.txt

4. **Run the notebook**
jupyter notebook notebooks/PJME_Load_Forecasting.ipynb

(or upload the notebook directly to Kaggle, Google Colab, etc.)

---

## 📈 Results & Visualization

The notebook includes **plots of actual vs forecasted load**, feature importance analysis, and performance metrics—making it easy to present your work or extend for further experimentation.

---

## 🔜 Future Directions

- **Integrate weather data** for improved accuracy
- **Experiment with deep learning** (LSTM, Transformer)
- **Build a Streamlit app** for interactive forecasting
- **Deploy as a FastAPI service** for real-time API access

---

## 🙋 Author & Contact

**Aryan Adit**  
[GitHub](https://github.com/Aryanadit) | [LinkedIn](https://linkedin.com/in/aryanadit)  
Open to feedback, collaboration, and improvements!

---

## ⭐ Support

If you find this project useful, **star the repo** and share it with your network.  
Contributions and suggestions are always welcome!

