# **Data-Driven Analysis and Optimization of Blast Furnace Fuel Rate**

Project By: Piyush Narayan Rai | National Institute of Technology Durgapur  

## **1\. Abstract**

This project presents a comprehensive, data-driven analysis of key operational parameters influencing fuel rate optimization in Blast Furnace 8 at SAIL Bhilai Steel Plant (BSP). As fuel costs can comprise up to 60% of hot metal production costs, minimizing fuel consumption is critical for economic and environmental sustainability.

Using real-time industrial data, this analysis develops and evaluates various machine learning models to predict the fuel rate. The core finding reveals that simple correlations in operational data often contradict established metallurgical theory due to complex, compensatory control strategies employed by operators. The project deciphers this operational logic to provide actionable insights for improving energy efficiency and reducing costs.

## **2\. Key Features**

* **In-depth Process Analysis:** Detailed examination of vital blast furnace parameters, including hot blast temperature, moisture content, CO utilization, slag rate, and flame temperature.  
* **Predictive Modeling:** Development and comparison of multiple machine learning models to predict fuel rate, with a **Tuned Random Forest** model selected as the best performer (R² Score: 0.42).  
* **Insightful Visualizations:** Data visualizations that uncover the complex, non-linear relationships between operational parameters and fuel consumption.  
* **Actionable Recommendations:** Practical, data-backed recommendations for optimizing fuel consumption in blast furnace operations.

## **3\. Tech Stack**

* **Languages & Environments:** Python, Jupyter Notebook, VS Code  
* **Data Handling & Analysis:** pandas, numpy  
* **Machine Learning:** scikit-learn (RandomForestRegressor, GradientBoostingRegressor, LinearRegression)  
* **Data Visualization:** plotly, matplotlib, seaborn  
* **Model Persistence:** joblib

## **4\. The Paradox: Operational Data vs. Metallurgical Theory**

A central theme of this project is the discrepancy between theory and observed data. While metallurgical principles provide a theoretical baseline, they often fail to capture the reality of a 24/7 industrial operation where multiple parameters are adjusted simultaneously to maintain stability.

**Our analysis shows that operators' compensatory control actions create correlations in the data that appear counter-intuitive but reveal a deeper operational logic.**

### **Key Findings Summary:**

| Parameter | Theoretical Relationship with Fuel Rate | Observed Trend in Data | Primary Reason for Discrepancy |
| :---- | :---- | :---- | :---- |
| **Hot Blast Temp** | Negative (Higher temp \= less fuel) | **Positive** | Used to compensate for the cooling effect of high PCI rates. |
| **Moisture Injection** | Positive (Moisture cools \= more fuel) | **Negative** | Used as a coolant only when the furnace is already hot and efficient. |
| **Slag Rate** | Positive (More slag \= more fuel) | **Positive** | Direct energy penalty; not used as a control lever. |
| **CO Efficiency** | Negative (Higher efficiency \= less fuel) | **Flat** | Evidence of successful process control keeping efficiency stable. |

## 

## **5\. The Fuel Rate Prediction Model**

A model was developed to predict the fuel rate based on key input parameters. The **Tuned Random Forest** model was selected for its superior performance in capturing the complex, non-linear interactions within the furnace data.

### **Model Performance Comparison**

Model | Description-

**Linear Regression | Baseline linear model |
Decision Tree     | Non-linear decision rules |
Random Forest     | Ensemble of trees (Best Model) |
Gradient Boosting | Boosted ensemble of trees |**

The **Random Forest Regressor** was selected as the best model, achieving the highest R² score (≈0.41) and demonstrating its ability to capture the complex, non-linear relationships in the data.

### **Feature Importances**

The model identified **Hot Blast Temperature** and **Slag Rate** as the most significant predictors of the fuel rate.

### **Example Prediction**

The model provides accurate predictions that align closely with actual operational data.

Enter moisture: 5.5  
Enter co efficiency: 46.65  
Enter hot blast temp: 1181.71  
Enter slag rate: 507  
Enter flame temp: 2208.6  
Enter top pressure: 2.26

Actual Fuel Rate: 573.3  
Predicted Fuel Rate for New Data: 573.52

## **6\. Key Insight & Justification**

The counter-intuitive positive trend between Hot Blast Temperature (HBT) and Fuel Rate is explained by **compensatory control for high Pulverized Coal Injection (PCI) rates**. To use cheaper coal (PCI) instead of expensive coke, operators must add extra heat via a higher HBT to maintain thermal balance.

The plot below proves this: the "High PCI" regime not only has higher fuel rates but also operates at a higher average HBT. This justifies the paradox by showing that **high HBT doesn't cause high fuel rates; it is the necessary enabler for a high-PCI, cost-saving strategy.**

## **7\. Recommendations for Optimization**

Based on the analysis, the following strategic recommendations were formulated:

1. **Prioritize Raw Material Quality:** A lower slag rate is the most reliable lever for reducing fuel consumption. Efforts should focus on securing higher-grade iron ore and coke.  
2. **Adopt a Holistic High-Injection Strategy:** To minimize costs, pursue a strategy that combines:  
   * **High PCI Rate:** To replace expensive coke.  
   * **High Hot Blast Temperature:** To provide the necessary heat to combust the coal.  
   * **High Oxygen Enrichment:** To further boost flame temperature and enable even higher PCI rates.  
3. **Maintain High Top Pressure:** Operate at a consistently high top pressure to improve gas residence time and maximize CO utilization efficiency.  
4. **Use RAFT as a Stability Constraint:** Treat the flame temperature (RAFT) as a stability parameter to be kept within an optimal window, not a target to be maximized, to ensure equipment longevity.

## **9\. Acknowledgements**

Sincere gratitude to **Shri. H.K. Verma (General Manager)** and **Shri. Satyabrata Sutar (Assistant General Manager)** at SAIL, Bhilai Steel Plant for their invaluable guidance, support, and insights throughout this project.
