Project Objectives

The main objectives of this project are:

Compute Pearson correlation between numerical features.

Visualize correlations using a heatmap.

Mask the upper triangle of the heatmap for better readability.

Annotate correlation values.

Explore pairwise relationships using scatter plots.

Identify the strongest positive and negative correlations.

Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

Project Structure
Correlation-Heatmap-Analysis
│
├── data
│   └── sales_data_sample.csv
│
├── notebook
│   └── correlation_analysis.ipynb
│
├── images
│   ├── heatmap.png
│   └── pairplot.png
│
└── README.md
Installation

Clone the repository:

git clone https://github.com/yourusername/correlation-heatmap-analysis.git

Navigate to the project directory:

cd correlation-heatmap-analysis

Install required libraries:

pip install pandas numpy matplotlib seaborn
Load the Dataset
import pandas as pd

df = pd.read_csv("sales_data_sample.csv")
df.head()
Pearson Correlation Matrix

Pearson correlation measures the linear relationship between variables.

correlation_matrix = df.corr(method='pearson')
print(correlation_matrix)
Correlation Heatmap

The heatmap provides a visual representation of correlations between variables.

import seaborn as sns
import numpy as np
import matplotlib.pyplot as plt

corr = df.corr()

mask = np.triu(np.ones_like(corr, dtype=bool))

plt.figure(figsize=(10,7))

sns.heatmap(
    corr,
    mask=mask,
    annot=True,
    fmt=".2f",
    linewidths=0.5
)

plt.title("Correlation Heatmap")
plt.show()
Pairwise Relationship Analysis

Pairplots visualize relationships between variables through scatter plots and distributions.

sns.pairplot(df)
plt.show()

Focused pairplot for key variables:

sns.pairplot(df[['Advertising_Spend','Website_Visits','Sales','Repeat_Customers']])
Key Insights
Strong Positive Correlations

Sales vs Website_Visits
Increased website traffic leads to higher sales.

Sales vs Advertising_Spend
Advertising plays a major role in driving sales.

Customer_Satisfaction vs Repeat_Customers
Higher satisfaction results in more returning customers.

Moderate Positive Correlations

Advertising Spend → Website Visits

Sales → Customer Satisfaction

Negative Correlations

Product Price vs Sales
Higher product prices tend to reduce sales.

Business Insights

Increasing advertising budget can increase website traffic and sales.

Improving customer satisfaction can increase customer retention.

Pricing strategy should be optimized to avoid loss in sales.

Conclusion

Correlation analysis helps identify relationships between variables and provides insights for better business decisions.

Using heatmaps and pairplots makes it easier to visually interpret correlations and detect patterns in data.

This project demonstrates an essential Exploratory Data Analysis technique used in real-world data analytics projects.

Future Improvements

Use real-world datasets

Perform feature engineering

Apply regression models

Build predictive analytics models
