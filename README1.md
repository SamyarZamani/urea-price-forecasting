# Urea Price Prediction

This project focuses on **forecasting Urea prices** using machine learning models and market data.  
The goal is to provide accurate weekly/monthly price predictions that can be used for decision-making in the fertilizer and agriculture sector.

---

## 📊 Data Sources
The following datasets were used:
- Urea daily and weekly prices (2017–2025)
- Additional features: Corn, Wheat, DXY, Oil, Natural Gas (weekly data)
- Processed data with lag features for time-series modeling

---

## 🧠 Models Used
- **Gradient Boosting (XGBoost)**
- **LSTM (planned for extension)**
- Future improvements: Hybrid models (LSTM + GBoosting), adding weather & sentiment data

---

## ⚙️ Methodology
1. Data cleaning and preprocessing  
   - Removed noisy or unavailable columns (e.g., `Vol.`)  
   - Created lag features for capturing time-series dependencies  
2. Feature engineering across multiple commodities  
3. Model training and evaluation  
4. Visualization of actual vs predicted Urea prices  

---

## 📈 Results
- **R² Score:** 97.63%  
- **Mean Absolute Error (MAE):** 4.28  
- The model closely follows actual Urea price trends with minimal error.

---

## 🚀 Future Work
- Integration of **market sentiment analysis** (news & social media)  
- Adding **weather/climate data** for improved agricultural price prediction  
- Building a **self-learning / auto-updating pipeline** for real-time predictions  
- Long-term forecasts until **end of 2025** (weekly/monthly resolution)

---

## ✨ Author
Developed by SamyarZamani as part of a Urea price forecasting project.
