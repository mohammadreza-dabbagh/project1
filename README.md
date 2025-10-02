IoT Fridge Data Analysis and Classification
🚀 Project Overview
This project focuses on data analysis and machine learning classification using the IoT Fridge dataset. The primary goal is to build and evaluate multiple classification models to predict a target variable (likely a status or label) associated with the smart fridge data.

The workflow includes essential steps such as data cleaning, feature engineering, Exploratory Data Analysis (EDA), handling class imbalance using SMOTE, feature scaling, and rapid model evaluation with LazyPredict.

🛠️ Prerequisites and Setup
To run this code, you will need the following Python libraries. You can install them using pip:

Bash

pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn lazypredict
Key Libraries Used:
numpy

pandas

matplotlib & seaborn (for visualization)

imblearn.over_sampling.SMOTE (for handling imbalance)

lazypredict.Supervised.LazyClassifier (for automated model comparison)

sklearn utilities (train_test_split, StandardScaler)

📊 Data Analysis and Modeling Steps
1. Data Loading and Cleaning
Loading: The dataset is loaded from the IoT_Fridge.csv file.

Data Transformation/Feature Engineering:

The time and date columns are converted from string formats into numerical values (seconds from midnight and an aggregate day count, respectively).

The categorical temp_condition is encoded into numerical values (e.g., high=1, low=0).

Missing Values: A check for missing values is performed.

Duplicates: Duplicate records are identified and removed from the dataset.

2. Exploratory Data Analysis (EDA)
Correlation: A heatmap is generated to visualize the correlation matrix between the features.

Univariate Analysis: Custom functions (summary, cont_plots, disc_plots, cat_plots) are defined and executed to generate comprehensive statistical summaries and visualization plots (histograms, box plots, count plots) for continuous, discrete, and categorical features.

3. Data Splitting and Resampling
Split: The data is split into training (
X 
train
​
 ,y 
train
​
 
) and testing (
X 
test
​
 ,y 
test
​
 
) sets with a 70:30 ratio (test_size = 0.3).

Imbalance Handling (SMOTE): The target variable's distribution reveals a class imbalance. The SMOTE (Synthetic Minority Over-sampling Technique) algorithm is applied to the training set to equalize the number of samples in both classes, improving model training stability.

4. Feature Scaling
StandardScaler is fit to the balanced training data and used to transform (standardize) both the training and testing feature sets, ensuring all features contribute equally to the models.

5. Automated Model Selection with LazyPredict
The LazyClassifier tool is employed to rapidly train and benchmark over a dozen different classification algorithms.

The models are trained on the SMOTE-resampled and scaled training data and evaluated on the scaled test data.

The final output is a performance table that allows for quick comparison and selection of the best model candidate for the classification task.

🔑 Modeling Results
The script's final output is a sorted table provided by LazyClassifier, detailing the performance metrics (e.g., Accuracy, F1 Score, ROC AUC) of all evaluated models on the test set.

Example LazyPredict Output Table:

Model	Accuracy	Balanced Accuracy	ROC AUC	F1 Score	...
[Top Performing Model]	...	...	...	...	...
...	...	...	...	...	...
[Worst Performing Model]	...	...	...	...	...
