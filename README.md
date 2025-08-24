EXPERIMENT — DATA CLEANING AND PREPROCESSING

OBJECTIVE
Demonstrate essential data cleaning and preprocessing tasks: handling missing values, feature engineering, scaling, and encoding categorical variables to prepare data for modeling.

RATIONALE
Raw datasets commonly contain missing, inconsistent, or ill-formatted values. Correct preprocessing is critical to ensure that models learn from signal rather than noise and to prevent data leakage.

THEORY SUMMARY
	•	Missing-value strategies: mean/median imputation for continuous data, mode for categorical data, forward/backward fill for time series, or dropping rows/columns when appropriate.
	•	Feature engineering: create informative derived features (for example, age squared, interaction terms) to capture nonlinear patterns.
	•	Scaling: MinMaxScaler rescales to [0,1]; StandardScaler centers to zero mean and unit variance; RobustScaler uses median/IQR and is robust to outliers.
	•	Encoding: Label encoding for ordinal categorical fields; one-hot encoding for nominal categorical fields.
	•	Type conversion: convert date strings to datetime and extract year/month/day where useful.

DATA USED
A small illustrative dataset generated in the notebook with columns: age, income, date, marital_status, gender. The notebook saves and reloads data as data.csv.

STEP-BY-STEP PROCEDURE
	1.	Load the dataset (or generate it as provided).
	2.	Inspect missingness using isnull().sum().
	3.	Convert income to numeric and impute missing income with mean or median.
	4.	Forward-fill or appropriately impute missing dates.
	5.	Optionally drop rows/columns with excessive missingness.
	6.	Engineer features (for example, age_squared).
	7.	Rename columns for clarity (for example, income → annual_income).
	8.	Scale numeric features using MinMaxScaler or StandardScaler.
	9.	Encode categorical variables using LabelEncoder or one-hot encoding.
	10.	Export cleaned data if required.

HOW TO RUN
Open the notebook in Google Colab and run cells sequentially. Replace the generated dataset with your file by using pd.read_csv(‘yourfile.csv’) where appropriate.

EXPECTED OUTPUT
	•	Cleaned dataframe with imputed missing values.
	•	Scaled numeric features and encoded categorical variables.
	•	Additional engineered columns to aid modeling.

PRACTICAL NOTES
	•	Fit scalers and encoders on training data only to avoid leakage.
	•	For high-cardinality categorical variables, consider target encoding or embeddings.
	•	Persist transformers (scalers, encoders) to disk for reproducible inference pipelines.
