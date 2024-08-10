# Machine Learning for Surface Coating Optimization

## Overview

This project focuses on optimizing surface coating processes using machine learning techniques. Surface coatings are crucial in prolonging the lifespan of materials used in various industries, from household goods to industrial machinery. This project, sponsored by PPG Industries, aims to leverage historical data and machine learning models to predict and minimize surface corrosion.

## Project Objectives

The project has two primary objectives:

1. **Regression Task**: Predict the fraction of the surface that corroded after testing, based on chemistry, manufacturing process inputs, and the machine used.
2. **Classification Task**: Classify whether the corroded surface fraction will be less than 33%, and identify the key inputs influencing this outcome.

## Data Description

The dataset used in this project contains the following inputs and outputs:

- **Chemistry Variables**: `x1`, `x2`, `x3`, `x4`
- **Manufacturing Process Variables**: `v1`, `v2`, `v3`, `v4`, `v5`
- **Machine Used**: `m` (categorical variable)
- **Response Variable**: Fraction of the specimen surface that corroded after testing (`output`)

Additional derived features were also considered, such as:
- `x5`: Balance constituent, calculated as `x5 = 1 - (x1 + x2 + x3 + x4)`
- `w`: Ratio defined as `w = x2 / (x3 + x4)`
- `z`: Ratio defined as `z = (x1 + x2) / (x4 + x5)`
- `t`: Product of process variables `v1 * v2`

## Methodology

### 1. Data Exploration
- **Visualization**: Analyzed the distributions of both the input and output variables, including the logit-transformed response.
- **Correlation Analysis**: Examined the relationships between input variables and their impact on the response.

### 2. Regression Modeling
- **Linear Models**: Trained nine different linear models using both base and expanded feature sets. Evaluated model performance and selected the best model based on key metrics.
- **Bayesian Linear Models**: Fit two Bayesian linear models to account for uncertainty in residuals. Selected the best model based on posterior summaries and uncertainty analysis.
- **Complex Methods with Resampling**: Trained and tuned advanced models such as Neural Networks, Random Forests, and Gradient Boosted Trees using both feature sets.

### 3. Classification Modeling
- **Generalized Linear Models (GLM)**: Trained nine different GLMs and selected the best model based on classification accuracy.
- **Bayesian GLMs**: Implemented Bayesian methods to account for uncertainty in classification tasks and identified key features influencing the outcome.
- **Advanced Methods with Resampling**: Applied advanced classification methods including Elastic Net, Neural Networks, and Random Forests, comparing performance using different resampling schemes.

### 4. Interpretation and Optimization
- **Model Interpretation**: Identified the most important variables and visualized their impact on the predicted outcomes.
- **Optimization**: Investigated the optimal input settings to minimize surface corrosion and explored the variation in these settings across different machine categories.

## Results

- **Best Performing Models**: The project identified the top models for both regression and classification tasks. These models were evaluated based on their predictive accuracy and the ability to generalize to unseen data.
- **Key Features**: Certain chemistry and process variables were identified as critical factors in predicting corrosion outcomes, aligning with the insights provided by Subject Matter Experts (SMEs).
- **Optimization Recommendations**: Provided actionable recommendations for adjusting input settings to minimize corrosion, with a focus on practical applications in industrial settings.

## Bonus Achievements

- **Synthetic Data Generation**: Created synthetic data to validate the model’s ability to recover true parameters under different sample sizes.
- **Presentation for PPG**: Developed a PowerPoint presentation summarizing the project’s findings and providing insights into optimizing surface coating processes.

## Files in This Repository

- `data/`: Contains the dataset used for modeling.
- `scripts/`: Includes the R scripts for data exploration, model training, and evaluation.
- `models/`: Saved models and their performance metrics.
- `results/`: Visualizations and results from the analysis.
- `synthetic_data/`: Synthetic datasets and analysis.
- `presentation/`: PowerPoint presentation for PPG.

## How to Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Kr-Yan/surface-coating-optimization.git
   cd surface-coating-optimization

