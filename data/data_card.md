# Data Card — Student Performance Data

## Dataset identification and provenance

- **Name**: Student Performance Data  
- **Domain**: Education  
- **Source**: https://www.kaggle.com/datasets/devansodariya/student-performance-data?resource=download
- **Original context**: Analysis of factors influencing student academic performance  
- **Collection method**: Survey-based data and academic records  
- **Population**: Secondary school students  

## Target variables

Though the dataset contains multiple grade-related columns, I select two targets for my models:

- **Target 1**: G3-final grade  
- **Target 2**: G2-second period grade

This choice allows training two distinct regression models while keeping the dataset simple.

## Feature overview

- Total rows: 395  
- Total columns: 33  
- Numerical features: 16
- Categorical features: 17

## Data quality analysis

### Missing values
No missing values were detected in the dataset. All 395 rows contain complete information for all 33 features.

### Duplicates
No duplicate rows were found in the dataset.

### Outliers
Some numerical variables show high variability. In particular:
- "absences" ranges from 0 to 75, indicating a small number of students with unusually high absence counts.
- Student age ranges from 15 to 22, which is expected but includes older students compared to the median.

These values were kept, as they likely represent real student situations rather than data errors.


## Descriptive statistics

Key statistics for numerical variables include:

- Average student age: 16.7 years (median: 17)
- Average number of absences: 5.7 days (median: 4, max: 75)
- Average first period grade (G1): 10.9
- Average second period grade (G2): 10.7
- Average final grade (G3): 10.4

Grades range from 0 to 20, which corresponds to the standard grading system.

## Correlation analysis

Correlation analysis highlights several strong relationships:

- G2 is strongly correlated with G3 (correlation ≈ 0.90)
- G1 also shows a strong positive correlation with both G2 and G3
- The number of past failures is moderately negatively correlated with final grades
- Parental education ("Medu", "Fedu") shows a weak but positive correlation with grades

Non-academic and lifestyle-related variables generally show weak correlations with student performance.

## Bias and limitations

- The dataset represents students from a specific educational and cultural context and may not generalize to other regions or school systems.
- Several socio-economic and family-related variables may introduce bias.
- Grades may be influenced by subjective evaluation methods specific to the institutions involved.

## Data dictionary

| Column | Type | Unit | Description |
|------|------|------|-------------|
| school | categorical | — | School attended by the student |
| sex | categorical | — | Gender of the student |
| age | integer | years | Student age |
| Medu | integer | level | Mother’s education level |
| Fedu | integer | level | Father’s education level |
| studytime | integer | category | Weekly study time |
| failures | integer | count | Number of past class failures |
| absences | integer | days | Number of school absences |
| G1 | integer | grade (0–20) | First period grade |
| G2 | integer | grade (0–20) | Second period grade (target) |
| G3 | integer | grade (0–20) | Final grade (target) |

## Data cleaning and normalization

The following preprocessing steps were applied to the raw dataset:

- Target variables (G2, G3) were separated from input features
- Categorical variables were encoded using one-hot encoding
- Numerical features were normalized using Min-Max scaling
- No rows were removed, as the dataset contained no missing or duplicate values

The processed dataset was exported as: "student_data_cleaned.csv"

## Data lineage

- Raw dataset: data/raw/student_data.csv
- Cleaning notebook: notebooks/02_cleaning.ipynb
- Processed dataset: data/processed/student_data_cleaned.csv

This lineage ensures traceability between the original data and the dataset used for model training.


