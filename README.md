# DRW Crypto Market Prediction 
# DRW - Crypto Market Prediction 🪙📈

This project was developed as part of an academic assignment for the FDA (Fundamentals of Data Analytics) course, and it was also submitted to the [Kaggle competition](https://www.kaggle.com/competitions/drw-crypto-market-prediction) hosted by DRW.

Our goal was to build a machine learning model capable of predicting short-term price movements in the crypto market using a high-dimensional dataset composed of both proprietary features and public market statistics.

---

## 📁 Project Structure

DRW---Crypto-Market-Prediction/
├── data/ # (optional) for local use only - raw datasets
├── notebooks/
│ └── DRW - Crypto Market Prediction.ipynb
├── reports/
│ ├── Final Reports.docx
│ └── Final Reports.pdf
├── requirements.txt
└── README.md

yaml
Copy
Edit

---

## 📊 Dataset

The dataset was provided by DRW and contains:
- Market microstructure data at 1-minute frequency
- Anonymized engineered features (X1 to X890)
- Target column: `label` (short-term return)
- Separate test set without labels (for Kaggle submission)

Due to Kaggle terms, datasets are **not included** in this repo. You can download them from the [competition page](https://www.kaggle.com/competitions/drw-crypto-market-prediction/data).

---

## 🧠 Models Tested

Before applying feature engineering, the following models were evaluated:

| Model                   | MAE   | RMSE  | R²        |
|------------------------|-------|-------|-----------|
| Linear Regression       | 345.1 | 516.8 | -247288.6 |
| Decision Tree Regressor | 0.73  | 1.10  | -0.116    |
| XGBoost Regressor       | 0.83  | 1.22  | -0.381    |
| LightGBM Regressor      | 0.87  | 1.26  | -0.468    |
| CatBoost Regressor      | 0.78  | 1.13  | -0.198    |

After feature engineering and hyperparameter tuning using **Optuna**, CatBoost achieved:

MAE: 0.026
RMSE: 0.073
R²: 0.995
Kaggle score (public leaderboard): 0.00487

yaml
Copy
Edit

---

## 🛠 Feature Engineering

- Created lag features and rolling statistics
- Applied SelectKBest (f_regression) to reduce dimensionality to top 100 features
- Removed features containing infinite values (e.g., X697–X717)
- Performed ADF stationarity test to ensure suitability for time series modeling

---

## ⚙️ Tools & Libraries

- Python (3.10+)
- CatBoost, XGBoost, LightGBM
- Optuna for hyperparameter tuning
- Pandas, Scikit-learn, Matplotlib, Statsmodels

Install all dependencies with:

```bash
pip install -r requirements.txt
📎 Report
You can read the full academic report here, including:

EDA and stationarity testing

Model comparisons

Feature selection and Optuna tuning

Kaggle results and conclusions

📬 Author
Sima Niaz
MSc Data Analytics @ BSBI Berlin
📫 https://www.linkedin.com/in/sima-niaz-954952124/ | ✉️ sima.niaz@gmail.com

📝 License
This project is for educational purposes only. Data remains the property of DRW and is subject to Kaggle competition rules.
### Dataset
DRW provided the dataset used in this project via Kaggle:  
🔗 [DRW - Crypto Market Prediction](https://www.kaggle.com/competitions/drw-crypto-market-prediction/data)  
Please download `train.csv` and `test.csv` and place them in the `data/` folder before running the notebook.

