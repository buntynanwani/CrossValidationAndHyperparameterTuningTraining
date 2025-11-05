# 🎓 Cross-Validation & Hyperparameter Tuning Training

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive training repository covering Cross-Validation techniques and Hyperparameter Tuning strategies in Machine Learning. This project includes theoretical documentation, practical notebooks, interactive demos, and a full web application.

## 📚 Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Notebooks](#notebooks)
- [Presentation Link](https://gamma.app/docs/Cross-Validation-Hyperparameter-Tuning-Training-fsqja7q7s70zigm)

## 🎯 Overview

This repository serves as a complete training resource for understanding and implementing:

### 🧩 1. Cross-Validation (CV)
- **The Problem**: Why simple train-test splits aren't enough
- **The Solution**: How cross-validation provides robust model evaluation
- **Types of CV**:
  - K-Fold Cross-Validation
  - Stratified K-Fold
  - Leave-One-Out (LOO)
  - Time Series Cross-Validation
  - Group K-Fold

### ⚙️ 2. Hyperparameter Tuning
- **What are Hyperparameters?**: Understanding model configuration parameters
- **Algorithms Covered**:
  - Decision Trees (`max_depth`, `min_samples_split`)
  - Random Forest (`n_estimators`, `max_features`)
  - k-Nearest Neighbors (`n_neighbors`, `weights`)
  - Neural Networks (`learning_rate`, `layers`, `neurons`)
- **Tuning Methods**:
  - Grid Search
  - Random Search
  - Bayesian Optimization
  - Optuna Framework

## 📁 Project Structure

```
CrossValidationAndHyperparameterTuningTraining/
│
├── backend/                    # Backend API and ML models
│   ├── api/                    # Flask/FastAPI application
│   ├── models/                 # CV and tuning implementations
│   └── utils/                  # Helper functions
│
├── frontend/                   # Frontend applications
│   └── streamlit_app/          # Streamlit interactive demos
│
├── docs/                       # Detailed documentation
│   ├── 01_cross_validation/    # CV theory and guides
│   └── 02_hyperparameter_tuning/  # Tuning theory and guides
│
├── notebooks/                  # Jupyter notebooks
│   ├── 01_cross_validation/    # CV examples and tutorials
│   └── 02_hyperparameter_tuning/  # Tuning examples
│
├── datasets/                   # Sample datasets for practice
│
├── outputs/                    # Results, figures, and models
│   ├── figures/                # Visualizations
│   ├── models/                 # Trained models
│   └── reports/                # Experiment reports
│
└── tests/                      # Unit tests
```

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/buntynanwani/CrossValidationAndHyperparameterTuningTraining.git
cd CrossValidationAndHyperparameterTuningTraining
```

### Step 2: Create Virtual Environment

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```


## 🎬 Quick Start

### Launch Jupyter Notebooks

```bash
jupyter notebook
```

Navigate to `notebooks/` and start with `01_cross_validation/01_intro_to_cv.ipynb`



## 📖 Documentation

Detailed documentation is available in the `docs/` folder:

### Summary of Notebook using Supplement_Sales_Weekly_Expanded
1. [Summary of Notebook using Supplement_Sales_Weekly_Expanded](docs/FinalConcusionOfSupplementSalesWeeklyExpandedUsedInNotebooks.md)

### Cross-Validation
1. [What is Cross-Validation?](docs/01_cross_validation/01_what_is_cv.md)
2. [The Problem CV Solves](docs/01_cross_validation/02_the_problem.md)
3. [CV as a Solution](docs/01_cross_validation/03_the_solution.md)
4. [Types of Cross-Validation](docs/01_cross_validation/04_types_of_cv.md)

### Hyperparameter Tuning
1. [What are Hyperparameters?](docs/02_hyperparameter_tuning/01_what_are_hyperparameters.md)
2. [Decision Tree Tuning](docs/02_hyperparameter_tuning/02_decision_tree.md)
3. [Random Forest Tuning](docs/02_hyperparameter_tuning/03_random_forest.md)
4. [k-NN Tuning](docs/02_hyperparameter_tuning/04_knn.md)
5. [Neural Network Tuning](docs/02_hyperparameter_tuning/05_neural_networks.md)
6. [Tuning Methods](docs/02_hyperparameter_tuning/06_tuning_methods.md)

## 📓 Notebooks
- **`eda_Supplement_Sales_Weekly_Expanded.ipynb`** - EDA Notebook Structure
- **`FinalConcusionOfSupplementSalesWeeklyExpandedUsedInNotebooks.ipynb`** - Summary of Notebook using Supplement_Sales_Weekly_Expanded.csv

### Cross-Validation Notebooks
- **`01_intro_to_cv.ipynb`** - Introduction and basics (Done)
- **`02_kfold_cv.ipynb`** - K-Fold implementation (Done)
- **`03_time_series_cv.ipynb`** - Time series specific techniques **(NEW NEXT STEP)**
- **`04_stratified_cv.ipynb`** - Stratified K-Fold for imbalanced data
- **`05_leave_one_out_cv.ipynb`** - LOO cross-validation


### Hyperparameter Tuning Notebooks
- `01_grid_search_decision_tree.ipynb` - Grid search on Decision Trees
- `02_random_search_random_forest.ipynb` - Random search on Random Forests
- `03_bayesian_optimization_knn.ipynb` - Bayesian optimization for k-NN
- `04_optuna_neural_network.ipynb` - Optuna framework for Neural Networks
- `05_combined_cv_and_tuning.ipynb` - Combining CV with hyperparameter tuning

### Project Presentation Link:
https://gamma.app/docs/Cross-Validation-Hyperparameter-Tuning-Training-fsqja7q7s70zigm
