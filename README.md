**********************************BUILD PROJECT TIMELINE ANALYSIS**********************************


-- This README file provides an overview of the Build Project Timeline Analysis for New Asset Deployments in the RAN Network. This project analyses project timelines and cost-impacting variables to improve forecasting for new asset deployments using machine learning models such as Random Forest, Linear Regression, and LSTM.

-- The following sections provide details on prerequisites, how to run the code, key steps involved, and methods for analysing and forecasting project timelines.

# Prerequisites

Ensure you have the following software and libraries installed before running the code:

### 1. Software Requirements
- Python 3.x: Ensure you have Python 3.x installed on your system.
- Jupyter Notebook or any Python IDE (like PyCharm, VSCode, etc.).

### 2. Python Libraries
You will need the following Python libraries installed. You can install them using "pip":

 "pip install numpy pandas matplotlib seaborn scikit-learn xgboost tensorflow"

	- pandas: For data manipulation and analysis.
	- numpy: For numerical operations.
	- matplotlib and seaborn: For data visualization.
	- scikit-learn: For machine learning algorithms like Linear Regression and Random Forest.
	- xgboost: For feature selection and model building.
	- tensorflow: For LSTM-based deep learning models.

### 3. Dataset
You need the dataset stored in CSV files in the following folder structure:

"./SiteTracker Projecttracker milestones/"

- Ensure that the dataset files are located under this folder with appropriate filenames.

# How to Run the Code

### Step-1: Set Up Directory Structure
- Place all your CSV files for project milestones in a folder named SiteTracker Projecttracker milestones in the same directory as your Python script or notebook.

### Step-2: Load the Necessary Libraries
- Ensure that the required libraries are loaded at the beginning of your script: (ALREADY USED IN THE CODE)

### Step-3: Load the Data
- The data is loaded from the folder containing the project milestone CSV files. The relative path ensures that the script can run on different systems without needing to change the path for the files.

- Subsequently, other CSV files are concatenated to create a unified DataFrame.

### Step-4: Data Filtering and Pre-processing
- After loading the data, filter out the rows that are not needed. (ALREADY IN THE CODE)

### Step-5: Null Data Analysis
- A function called "get_null_data(df)" is used to analyse null values. It provides the percentage of missing data in each column, which can be further used to drop or impute columns.

	- null_df = get_null_data(cleaned_data)

- A bar plot is created to visualize the percentage of missing data.

### Step-6: Feature Selection using XGBoost
- The code uses XGBoost to select the top features that impact the target variable "Tech_TTO_A" (the predicted timeline of the project). The top features are selected based on feature importance.

- The top "N" features can be visualized via a bar plot.

### Step-7: Correlation Matrix
- A correlation matrix is generated to identify relationships between milestones. This helps in detecting and removing highly correlated features if necessary.

- A heatmap is plotted to visualize the correlations.

### Step-8: Model Building and Evaluation
- The project uses three different approaches for predicting the target column (project timeline):

- A Random Forest Regressor model, Linear Regression model and Long Short-Term Memory (LSTM) model are trained and evaluated using Milestone-based Duration Calculation and Forecasted Date and Delay based prediction.

- The performance of the models is also measured using MAE and R² Score.

### Step-9: New Data Predictions
- You can make predictions on new data by pre-processing it and feeding it into the trained Random Forest Regressor:

	- dats = new_data_preprocess(new_data_for_pred, 'rf_model')

## Results

- The results of the predictions are visualized using scatter plots comparing **Actual vs. Predicted** milestone dates. The project compares the performance of different models and approaches in predicting the completion timelines for projects.

## Conclusion

This project demonstrates an efficient way to analyse project timelines and predict future milestone completion dates using machine learning models. Different approaches such as Random Forest, Linear Regression, and LSTM are tested, with results showing how well each model performs in forecasting new RAN network deployments.

-----------------------------------This completes the README file for the Project Timeline Analysis and Forecasting project-----------------------------------


