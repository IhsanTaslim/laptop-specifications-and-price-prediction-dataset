# **Laptop Specifications and Price Prediction Dataset**

## **Business Problem**

### "What influences laptop price point?"

## 

##### Dataset

[Laptop Specification and Price Dataset from Kaggle](https://www.kaggle.com/datasets/muhammadmusharraf444/laptop-specifications-and-price-prediction-dataset?resource=download)

## 

##### Tools

* Python
* Pandas
* NumPy
* Matplotlib
* Statsmodels
* Scikit-learn
* Seaborn
* ISLP



##### Methodology

* **Data Preparation & EDA**: Cleaned alphanumeric columns (e.g., stripping "GB" from RAM), used Regex to extract distinct memory types, and consolidated granular categorical features (like GPU brands) to reduce dimensionality.
* **Feature Engineering**: Applied one-hot encoding for categorical variables, combined display dimensions into a single Pixels feature, and selected final features using a ±0.3 correlation threshold.
* **Model Development**: Built a Multiple Linear Regression (MLR) model using Ordinary Least Squares (OLS) via statsmodels.
* **Optimization & Diagnostics**: Standardized continuous variables using Z-scores to ensure matrix stability and confirmed the absence of multicollinearity using Variance Inflation Factor (VIF) testing.
* **Evaluation**: Partitioned data with an 80/20 train-test split, achieving a Mean Absolute Error (MAE) of 13,638.00.


## Findings

* **The Market Landscape**: The standard market centers around the 50,000 price point, heavily dominated by Windows 10 notebooks from Dell, Lenovo, and HP.
* **Memory is King**: RAM and SSD capacity are the strongest predictors of price (0.74 and 0.67 correlation, respectively). Standardized coefficients confirm that upgrading RAM drives price significantly more than CPU speed or screen resolution.
* **The "Gaming" Premium**: Laptops categorized as "Gaming" or equipped with Nvidia GPUs carry a strong price premium, whereas standard "Notebook" labels negatively impact price.
* **Model Limitations**: The model acts as a highly accurate baseline for budget to mid-tier laptops. However, it slightly under-predicts extreme luxury workstations due to the heavy concentration of consumer-grade laptops in the training data (resulting in an RMSE of 19,419.81).



## Repository Structure

```
├── Data/
│   ├── laptop\_data.csv   #raw Data
│   └── sub\_laptop.csv    #final transformed data
├── Data/
│   ├── .ipynb\_checkpoints/
│   └── laptop\_price\_prediction.ipynb
├── Presentation Deck/
│   ├── Laptop Data Price Prediction.pdf
│   └── Laptop Data Price Prediction.pptx
├── Visuals/
│   ├── Actual vs. Predicted Laptop Prices (Test Set).png
│   ├── Correlation of Features with Price (Targeted Heatmap).png
│   ├── Full\_Laptop\_Correlation\_Heatmap.png
│   ├── Laptop Manufacturer Distribution.png
│   ├── Laptop Operation System Distribution.png
│   ├── Laptop Price Distribution.png
│   ├── Laptop Type Distribution.png
│   ├── Multiple Linear Regression Results (Scaled).png
│   └── Relationship between Ram and Price.png
├── README.md
└── Requirements.md #list of libraries version
```

## Authors

Abdullah Ihsan - *Data Analyst* - [IhsanTaslim](https://github.com/IhsanTaslim)

Muhammad Musharraf - *Data Provider* - [MuhammadMusharraf](https://github.com/Muhammad-Musharraf)

