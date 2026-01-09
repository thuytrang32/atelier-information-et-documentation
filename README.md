# Student Performance Prediction

## Project goal
The goal of this project is to analyze student characteristics and educational context in order to predict academic performance.

Two predictive models are developed:
- Model 1 predicts the second period grade (G2)
- Model 2 predicts the final grade (G3)

The models use demographic, social, and academic features to estimate student grades.


## Repository structure
- data/raw/ : original Kaggle dataset
- data/processed/ : cleaned dataset used for training
- models/model_g2/ : trained model for G2 prediction
- models/model_g3/ : trained model for G3 prediction
- notebooks/ : exploration, cleaning, and training notebooks
- docs/ : technical document

## Documentation index 
- Data Card: data/data_card.md
- Model Card - G2: models/model_g2/model_card_target1.md
- Model Card - G3: models/model_g3/model_card_target2.md

## How to reproduce results
1. Create a virtual environment 
2. Install dependencies: pip install -r requirements.txt
