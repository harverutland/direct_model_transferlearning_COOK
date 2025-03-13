# Hepworth Training and Transfer Learning README

## Hepworth Training:
This approach utilizes an out-of-fold prediction model. The best-performing model was selected through a five-fold cross-validation evaluation using the **Hepworth Trial 1 Brewery dataset**.

- The model was trained on an **interpolated daily dataset** derived from the Hepworth dataset.
- The trained model is included in this directory and saved as **'best_model_fold_4.keras'**.

## Transfer Learning:
A **cleaned version of the WASE Trial 2 dataset** from the **Cook site** has been added. This dataset has been refined to match the key features identified through the feature importance analysis of the original Hepworth model.

- The machine learning pipeline **retrains the last two neurons** of the Hepworth model using the Cook dataset.

## Implementation Methodology:
Since this model is intended for use as a **soft sensor**, the dataset is **split into two partitions**:

1. **First Half** - Used for training, then predictions are made on the second half.
2. **Second Half** - Used for training, then predictions are made on the first half.

To account for **recalibration**, **10 additional days from each split** have been injected into the opposite partition.

---

### File Structure:
- **best_model_fold_4.keras** → Trained model from Hepworth dataset
- **WASE_Trial2_Cook_Cleaned.csv** → Processed dataset for transfer learning
- **README.txt** → This documentation

For further details, refer to the project documentation or contact the development team.
