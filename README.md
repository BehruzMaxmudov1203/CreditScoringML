# CreditDefaultPrediction 🚀

![GitHub Repo stars](https://img.shields.io/github/stars/yourusername/CreditDefaultPrediction?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/CreditDefaultPrediction?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/CreditDefaultPrediction)
![Python](https://img.shields.io/badge/python-3.12-blue)
![ROC-AUC](https://img.shields.io/badge/ROC--AUC-0.87-brightgreen)

![Banner](https://media.giphy.com/media/3o7TKtnuHOHHUjR38Y/giphy.gif)

A predictive analytics project for forecasting **loan defaults** using machine learning techniques like **Random Forest**, **SVM**, and **LightGBM**. This project helps banks and fintech companies assess credit risk and make informed lending decisions.

---

## 🔹 Features

- **Data Cleaning & Preprocessing**: Handles missing values, categorical encoding, and feature scaling.  
- **Machine Learning Models**:  
  - Random Forest Classifier  
  - SVM Classifier  
  - LightGBM Classifier  
- **Evaluation Metrics**: ROC-AUC, confusion matrix, and feature importance visualization.  
- **Imbalanced Data Handling**: SMOTENC oversampling for categorical + numerical features.  
- **Interactive Visualization**: ROC curves and model performance plots.  

---

## 🧩 Project Structure

```
CreditDefaultPrediction/
│
├── data/           # CSV datasets
│   └── merged.csv
├── notebooks/      # Jupyter notebooks for EDA and modeling
│   └── CreditDefault.ipynb
├── src/            # Python scripts
│   ├── preprocessing.py
│   ├── models.py
│   └── evaluation.py
├── README.md       # Project overview
└── requirements.txt # Dependencies
```

---

## 📈 Example Output

### Interactive ROC Curve

```python
import plotly.graph_objects as go
from sklearn.metrics import roc_curve, auc

# Misol uchun RandomForest modelidan olingan y_test va y_proba
fpr, tpr, _ = roc_curve(y_test, y_proba)
roc_auc = auc(fpr, tpr)

fig = go.Figure()
fig.add_trace(go.Scatter(x=fpr, y=tpr, mode='lines', name=f'ROC Curve (AUC={roc_auc:.2f})'))
fig.add_trace(go.Scatter(x=[0,1], y=[0,1], mode='lines', name='Random', line=dict(dash='dash')))
fig.update_layout(title='Interactive ROC Curve', xaxis_title='False Positive Rate', yaxis_title='True Positive Rate')
fig.show()
```

### Feature Importance (Random Forest)

![Feature Importance](https://media.giphy.com/media/3o7TKtdrhzV8U2zQ2U/giphy.gif)

### Live Metrics Badge

![ROC-AUC](https://img.shields.io/badge/ROC--AUC-0.87-brightgreen)

> GitHub Actions workflow yordamida modelni har push’dan so‘ng train qilib, metrics’ni badges shaklida avtomatik yangilash mumkin.

---

## ⚡ How to Run

1. Clone the repository:

```bash
git clone https://github.com/yourusername/CreditDefaultPrediction.git
cd CreditDefaultPrediction
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the main notebook:

```bash
jupyter notebook notebooks/CreditDefault.ipynb
```

Visualize model performance and feature importance.

---

## 📊 Dependencies

- pandas  
- numpy  
- scikit-learn  
- imbalanced-learn  
- matplotlib  
- seaborn  
- xgboost  
- lightgbm  
- plotly  

---

## 🎯 Goals

- Build a reliable credit default prediction model  
- Explore feature interactions and risk factors  
- Provide actionable insights for lenders and fintech companies  

---

## 💡 Future Improvements

- Deploy as web app for real-time predictions  
- Add SHAP values for model interpretability  
- Optimize hyperparameters with Optuna or GridSearchCV  
- Add interactive dashboards using Plotly or Streamlit  

---
