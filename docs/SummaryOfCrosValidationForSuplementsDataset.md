## **📈 Final Project Conclusion: Sales Price Forecasting Model**

**This report summarizes the findings from a series of data science experiments aimed at building a robust forecasting model for product pricing using the Supplement\_Sales\_Weekly\_Expanded.csv dataset. The focus was on applying correct Cross-Validation and Hyperparameter Tuning techniques, especially for complex, time-dependent data.**

---

## **🎯 Summary of Experiments and Key Takeaways**

| Notebook | Focus | Model & Target | Final Result | Key Insight Learned |
| :---- | :---- | :---- | :---- | :---- |
| **01\_intro\_to\_cv.ipynb** | **Standard K-Fold CV** | **Linear Regression (Price)** | **Avg. MAE: $6.12** | **Established a baseline performance metric. The score is likely overly optimistic because K-Fold ignores the time sequence.** |
| **02\_kfold\_cv.ipynb** | **Stratified K-Fold CV** | **Logistic Regression (Classification)** | **Avg. Accuracy: 96.00%** | **Demonstrated the risk of applying classification models to continuous data. High accuracy is misleading as the true problem is price *forecasting*, not classification.** |
| **03\_time\_series\_cv.ipynb** | **Time Series CV (TSC)** | **Linear Regression (Price)** | **Avg. MAE: $5.08** | **Crucial Step: Correctly acknowledged the data's time dependency. The MAE improved slightly over the naive K-Fold, showing that a simple model with the right CV is a better benchmark.** |
| **04\_optuna\_nn.ipynb** | **Advanced Tuning (Optuna)** | **Neural Network (Price)** | **Best Scaled MAE: 0.6977** | **Successfully used Optuna to find the most efficient Neural Network structure. It found a simple structure (1 hidden layer, 39 units), which hints at the data's complexity vs. size trade-off.** |
| **05\_combined\_cv.ipynb** | **Final Robust Test** | **Tuned Neural Network (Price)** | **Avg. MAE: $8.38 Avg. $\\text{R}^2$: \-2.66** | **The Reality Check: Combined the best tuning with the correct TSC. The negative $\\text{R}^2$ score proves that even the best-tuned Neural Network is not a suitable model for this volatile time-series, failing to beat a simple average guess.** |

---

## **🏆 Identification of the Best Result**

**To determine the "best result," we must choose the score that provides the most reliable and honest estimate of future performance.**

| Metric | Score | Reason for Selection |
| :---- | :---- | :---- |
| **Best Reliable MAE** | **$5.08 (from Notebook 03\)** | **This is the lowest Mean Absolute Error (MAE) achieved using the correct Time Series Cross-Validation (TSC). Although it uses a simpler Linear Regression model, its prediction error ($5.08) is more stable and reliable than the failed Neural Network ($\\text{MAE} \= \\$8.38$).** |
| **Best Tool-Set** | **Notebook 05** | **Despite the poor final performance, this notebook represents the most advanced and correct methodology (Optuna \+ Time Series CV). It provided the non-technical conclusion that the model architecture needs improvement, not just the parameters.** |

### **Final Conclusion for Deployment**

**Based on the experiments, the current best-performing, reliable predictive model is the Linear Regression model evaluated via Time Series Cross-Validation, with an expected average price error of $5.08.**

**The project successfully concluded that the highly flexible Neural Network, despite intensive tuning, is an inappropriate choice for this dataset, failing spectacularly in several key forecasting periods. This strongly suggests that future efforts must focus on:**

1. **More robust modeling techniques (e.g., dedicated time-series models like LSTM or tree-based regressors like XGBoost).**  
2. **Richer feature engineering (e.g., incorporating external factors or market signals).**

**The main success of this study is the realization that a correct cross-validation strategy (TSC) is essential to prevent deployment of a model (the Tuned NN) that would have catastrophically failed in the real world.**

