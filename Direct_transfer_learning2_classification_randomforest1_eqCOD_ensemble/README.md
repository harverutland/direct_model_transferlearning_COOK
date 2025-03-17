##############################
# Hepworth Training and Transfer Learning README
##############################
## Overview ##
This project utilizes a transfer learning approach with classification techniques to predict Chemical Oxygen Demand (COD) ranges in the equalisation tank, specifically designed for contexts with limited data availability. The model architecture employs a Random Forest classifier within a voting classifier framework.

## Hepworth Training ##
The foundational model was developed using a five-fold cross-validation method on the Hepworth Trial 1 Brewery dataset.

Training Dataset: Utilized an interpolated daily dataset from the Hepworth dataset.
Model File: The optimal model is stored as 'best_model_fold_4.keras' in this directory.

## Transfer Learning ##
This phase extends the Hepworth model to classify COD ranges, adapting it to a new dataset via a robust transfer learning protocol.

Initial Models: Developed using 5-fold cross-validation with random splits, available in 'base_training_ml_pipeline1.iynb'.
Voting Classifier: Further elaborated in 'transfer_learning_ml_pipeline1.ipynb', which also evaluates the model on an alternative field trial dataset.
Scaler Usage: The scaler from the initial training phase is employed to preprocess the new dataset, ensuring data consistency across models.

## Implementation Methodology ##
Designed to function as a soft sensor, the dataset is bifurcated into two distinct partitions for training and validation:

First Half - Primarily used for model training, with subsequent predictions generated for the second half.
Second Half - Similarly employed for training, with predictions aimed at the first half.
Recalibration Measures: To enhance model reliability, an additional 10 days from each partition are interchanged and incorporated into the training of the opposite half.

## File Structure ##
best_model_fold_4.keras - The trained model from the initial Hepworth dataset.
cook_data_Cleaned.csv - Prepared dataset for transfer learning application.
hepworth_data_Cleaned.csv - The base dataset used for initial model training.
robust_scaler.joblib - Scaler file for data normalization.
README.txt - Documentation file for this directory.

For additional information or inquiries, please refer to the project documentation or contact the development team.
