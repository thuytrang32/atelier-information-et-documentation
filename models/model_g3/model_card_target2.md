# Model Card — Model 2 (G3 Prediction)

## Model overview
- **Objective**: Predict the final grade 
- **Model type**: Linear Regression
- **Target variable**: G3

## Development context
This model was developed as part of an educational project focused on documentation practices.
The objective was to maintain consistency with the first model while predicting a different target.

## Training data
- Dataset name: Student Performance Data
- Dataset version: student_data_cleaned.csv
- Number of samples: 395
- Number of input features: 40
- Preprocessing:
  - One-hot encoding of categorical variables
  - Min-Max normalization of numerical features

## Model architecture
The model is a standard linear regression model implemented using scikit-learn.

## Hyperparameters
- No hyperparameter tuning was performed
- Default scikit-learn parameters were used

## Evaluation metrics
The model was evaluated on a held-out test set representing 20% of the dataset.

- RMSE: 2.9
- R² score: 0.59

These metrics indicate the model’s ability to predict final student grades.

## Limitations
- Strong dependence on intermediate grades (G1, G2)
- Linear assumptions may oversimplify complex educational dynamics
- Not suitable for production use
