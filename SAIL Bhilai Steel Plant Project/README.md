
# 🔥 Fuel Rate Prediction using Blast Furnace Operational Data

## 📊 Project Overview

This project focuses on predicting the **fuel rate** (in kg/thm) in **blast furnace ironmaking**, a key performance indicator that significantly impacts both cost and environmental sustainability. The analysis uses a dataset containing critical blast furnace parameters such as:

- Moisture content
- CO efficiency
- Hot blast temperature
- Slag rate
- Flame temperature
- Top pressure

The project involves data cleaning, outlier removal, data visualization, model training, and evaluation using various regression algorithms.

## 📁 Folder Structure

```
├── fuel_rate_prediction.ipynb       # Jupyter notebook version of the analysis
├── blastfurnacedata.csv             # Raw dataset (input)
├── cleaned_blast_furnace_data.csv   # Cleaned dataset (output)
├── fuel_rate_rf_model.pkl           # Trained Random Forest model
├── feature_importance.png           # Feature importance plot
├── correlation_heatmap.html         # Interactive correlation heatmap
├── README.md                        # Project documentation
```

## ⚙️ Technologies Used

- **Python**
- **Pandas, NumPy** – data handling and preprocessing
- **Seaborn, Matplotlib, Plotly** – data visualization
- **Scikit-learn** – model building and evaluation
- **Joblib** – model saving and loading

## 🧼 Data Preprocessing

1. Renamed inconsistent column headers.
2. Converted values to numeric types.
3. Removed missing values.
4. Applied **IQR method** to remove outliers using the 30th–70th percentile range.

## 📈 Data Visualization

- **Correlation heatmap** using Plotly
- **Scatter plots** with OLS trendlines between each feature and fuel rate
- **Feature importance bar plot**

## 🤖 Machine Learning Models

| Model               | Description               |
|--------------------|---------------------------|
| Linear Regression   | Baseline model             |
| Decision Tree       | Non-linear decision rules  |
| Random Forest       | Ensemble of decision trees (Best) |
| Gradient Boosting   | Boosted ensemble of trees  |

- Best performing model: **Random Forest Regressor**

## 📍 Results

- Evaluation based on **R² score** and **Mean Squared Error (MSE)**
- Visual comparison of model performance using bar plot

## 🔮 Prediction

Interactive user input allows prediction of the fuel rate based on new values of input parameters.

## 💾 Model Deployment

- Trained Random Forest model saved as: `fuel_rate_rf_model.pkl`
- Ready for integration into web dashboards, APIs, or desktop GUIs.

## 🚀 How to Run

1. Clone the repo or download the notebook.
2. Place your dataset as `blastfurnacedata.csv` in the same directory.
3. Run `fuel_rate_prediction.ipynb` in Jupyter or VS Code.
4. Follow the instructions for entering new values and getting predictions.

## 📌 Author

**Piyush Narayan Rai**  
B.Tech – Metallurgical & Materials Engineering  
National Institute of Technology, Durgapur  
