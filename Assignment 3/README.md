## Assignment 3 – Data Analysis 3

This folder contains all relevant files and outputs for **Assignment 3** of the *Data Analysis 3* course. The assignment focuses on predicting fast-growing firms using a panel dataset from Bisnode (2010–2015). The project involves extensive data cleaning, feature engineering, probability and classification modeling, and performance evaluation using various metrics including RMSE, AUC, and an asymmetric loss function.

### 📁 Folders

- `Data/` – Contains the raw, intermediate, and cleaned datasets used in the analysis.  
- `Figures/` – Stores visual outputs such as ROC curves, calibration plots, and loss curves.

### 📄 Key Files

- `Data_cleaning.Rmd` – Script and rendered report for cleaning the dataset, constructing the target, and engineering predictors.  
- `Tasks 1.Rmd` – Contains the full modeling workflow, including cross-validation, hyperparameter tuning, evaluation, and model comparison.  
- `da_helper_functions.R` – Collection of custom R functions used throughout the project (e.g., plotting and performance evaluation).  
- `theme_bg.R` – Custom ggplot2 theme used for consistent and minimalistic visualizations.

### 📊 Models and Evaluation

The models estimated include:
- Multiple logistic regressions (baseline, expanded, and regularized with LASSO)  
- A random forest classifier, both for probability and class prediction  

Each model is evaluated using 5-fold cross-validation. We compare them based on:
- Prediction error (CV RMSE)  
- Classification quality (CV AUC)  
- Optimal threshold and expected misclassification loss, based on a business-driven cost function (FP = 6, FN = 5)

Final performance is assessed on a holdout set.

### ⚠️ Interpretation and Limitations

The models show moderate predictive performance, with the random forest model slightly outperforming others in terms of AUC and expected loss. However, predicting rare events like rapid firm growth remains challenging. Results should be interpreted with caution: there is a trade-off between false positives and false negatives, and model usefulness will depend heavily on the application context (e.g., credit allocation vs. investment screening). The models can be helpful decision aids but are not substitutes for human judgment.
