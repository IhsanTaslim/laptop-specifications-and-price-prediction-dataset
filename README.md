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

* Data Cleaning \& Preprocessing (ETL)

  1. Data Type Formatting: Removed text characters from numerical columns (e.g., stripping "GB" from RAM and "kg" from Weight) and converted them to appropriate integer/float data types.
  2. Feature Extraction: Used Regular Expressions (Regex) to deconstruct complex string columns into usable metrics. For example, the Memory column was split into separate numerical capacities for SSD, HDD, Flash, and Hybrid drives.
  3. Categorical Grouping: Extracted overarching brand names from highly specific columns (e.g., parsing specific GPU models down to core manufacturers like Nvidia, Intel, and AMD) to reduce dimensionality.
* Exploratory Data Analysis (EDA)

  1. Univariate Analysis: Visualized the distribution of individual variables using histograms, count plots, and pie charts (e.g., verifying that the target variable Price is right-skewed).
  2. Bivariate Analysis: Used boxplots to analyze the relationship between categorical features (like RAM) and the continuous target variable (Price).
* Feature Engineering \& Selection

  1. One-Hot Encoding: Converted categorical variables (like TypeName) into dummy variables to prepare them for mathematical modeling.
  2. Multicollinearity Prevention: Consolidated Resolution\_Width and Resolution\_Height into a single Pixels feature to avoid semantic overlap.
  3. Correlation Filtering: Generated a correlation matrix heatmap and isolated features that exhibited a moderate-to-strong correlation with the target variable (> 0.3 or < -0.3) for the final model.
* Model Development \& Optimization

  1. Algorithm Selection: Built a Multiple Linear Regression (MLR) model using Ordinary Least Squares (OLS) via the statsmodels library.
  2. Diagnostic Testing: Evaluated the Variance Inflation Factor (VIF) to mathematically prove the absence of dangerous multicollinearity between features like TypeName\_Gaming and Gpu\_Nvidia.
  3. Feature Scaling: Applied Z-score standardization (StandardScaler) to continuous variables to resolve matrix instability (high condition numbers) caused by vastly different data scales (e.g., GHz vs. total Pixels).
* Model Evaluation

  1. Train-Test Split: Partitioned the data using an 80/20 split to train the model and test its ability to generalize to unseen data.
  2. Performance Metrics: Evaluated the model's accuracy using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).
  3. Visual Diagnostics: Plotted the model's Actual vs. Predicted prices on a scatterplot against a perfect-prediction identity line to visually confirm model reliability across different price tiers.



## Findings

* Market Landscape \& Dominance

  1. The Standard Market: The vast majority of consumer laptops sit around the 50,000 price range.
  2. Top Manufacturers: The hardware market is heavily led by Dell, Lenovo, and HP.  Form Factor \& OS: Standard "Notebooks" represent the most common form factor, with quantities more than double any other category. Additionally, Windows 10 heavily dominates the operating system landscape, holding 82.3% of the market share.
  3. Ecosystem Hardware Quirks: Specific brands favor specific hardware architectures; for example, Mac OS X correlates highly with Flash storage, indicating Apple's heavy reliance on this memory type. Furthermore, gaming laptops show a strong correlation with higher weight.



* What Drives Laptop Prices?

  1. Memory is King: RAM and SSD capacity are the absolute strongest predictors of a laptop's final price. The correlation matrix revealed that RAM has a 0.74 correlation with price, followed closely by SSD capacity at 0.67.
  2. The Hardware Hierarchy: The final scaled regression model proved the exact hierarchy of hardware value. Standardized coefficients confirm that upgrading RAM impacts the price significantly more than upgrading the CPU speed or the screen resolution.
  3. The "Gaming" Premium: Having an Nvidia GPU (0.35 correlation) or a "Gaming" label (0.38 correlation) carries a moderate to strong positive impact on the price. Conversely, standard "Notebook" labels have a strong negative correlation (-0.55) with price.



* Model Performance \& Limitations

  1. Strong Baseline Accuracy: The model is highly accurate at predicting the price of budget and mid-tier laptops, with an overall Mean Absolute Error (MAE) of 13,638.00.
  2. The Luxury Blindspot: The model struggles to accurately price extreme luxury laptops and high-end workstations. Because 95% of the market data consists of reasonably priced consumer laptops, the model optimizes for the average and slightly under-predicts the price tags of top-tier outliers. This is reflected in the Root Mean Squared Error (RMSE) of 19,419.81, which heavily penalizes these large outlier misses.



## Repository Structure

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



## Authors

Abdullah Ihsan - *Data Analyst* - [IhsanTaslim](https://github.com/IhsanTaslim)

Muhammad Musharraf - *Data Provider* - [MuhammadMusharraf](https://github.com/Muhammad-Musharraf)

