# Model Lineage & Invariants

## Model
- Name: WFA-XGB (safe)
- Artifact: models/wfa_xgb_model.json

## Dataset
- File: data/processed/heart_Verified.csv
- Version: regenerated on training run
- Split: train / val / test via src.data.split_data

## Feature Contract
- Feature order MUST match training
- No column addition/removal without retraining
- Encoding & scaling must remain unchanged

## Training Invariants
- Any change to dataset → retrain model
- Any change to feature engineering → retrain model
- Any change to sample weighting → retrain model

## Evaluation Invariants
- Evaluation notebooks NEVER retrain
- Evaluation uses raw probabilities only
- ROC-AUC is computed ONLY on raw y_prob

## Violation Consequence
Results are INVALID even if code executes successfully.
