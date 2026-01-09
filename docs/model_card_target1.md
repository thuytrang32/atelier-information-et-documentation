# Model Card — Model 1 (G2 Prediction)

## Model overview
- **Objective**: Predict the second period grade 
- **Model type**: Linear Regression
- **Target variable**: G2

## Development context
- Developed as part of an educational project focused on documentation practices
- Priority given to simplicity and reproducibility over performance

## Training data
- Dataset name: Student Performance Data
- Dataset version: student_data_cleaned.csv
- Number of samples: 395
- Number of input features: 40
- Preprocessing:
  - One-hot encoding of categorical variables
  - Min-Max normalization of numerical features

Note: The number of input features increased compared to the raw dataset due to one-hot encoding of categorical variables.

## Model architecture
The model is a standard linear regression model implemented using scikit-learn.

## Hyperparameters
- No hyperparameter tuning was performed
- Default scikit-learn parameters were used

## Evaluation metrics
The model was evaluated on a held-out test set (20% of the data).

- RMSE: 1.75
- R² score: 0.79

The results indicate that the model explains a significant portion of the variance in the second period grade.

## Limitations
- The model relies on strong correlations between academic grades
- Linear relationships may not fully capture complex educational factors
- The model is not intended for real-world deployment
