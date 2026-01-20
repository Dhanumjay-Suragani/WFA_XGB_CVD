# WFA-XGB CVD Prediction

A research-grade pipeline for **Weighted Feature Augmented (WFA) XGBoost**–based prediction of cardiovascular disease (CVD), with feature engineering, SHAP explainability, and experiment tracking.

---

## Features

- **End-to-end ML pipeline**
  - Data loading, splitting, feature engineering, model training, evaluation.
- **Baseline models**
  - Logistic Regression, Random Forest, and tuned XGBoost baselines.
- **WFA-XGB model**
  - Custom Weighted Feature Augmented XGBoost with focal loss support.
- **Explainability**
  - Global and local SHAP analyses, feature importance, and augmented weights.
- **Experiment tracking (lightweight)**
  - CSV-based logging of ablations, mutual information scores, and SHAP summaries.
- **Deployment-ready skeleton**
  - API entrypoint, deployment utilities, and inference stubs for future productionization.
- **Reproducibility**
  - Centralized paths, configs, seeded randomness utilities.

---

## Tech Stack

- **Language**: Python 3.10+  
- **ML & Data**:
  - `numpy`, `pandas`, `scikit-learn`, `xgboost`, `shap`, `joblib`, `matplotlib`
- **Experimentation**:
  - Jupyter Notebooks
- **API / Deployment**:
  - Python app entrypoint in `app/api.py`
  - Deployment stubs in `src/deployment/`
- **Environment / Tooling**:
  - `pip` for dependency management  
  - Git / GitHub for version control

---

## Folder Structure

---
wfa_xgb_cvd_prediction/
├── app/
│   └── api.py
├── data/
│   ├── feature_metadata.json
│   └── processed/
│       ├── heart_disease_processed.csv
│       └── heart_Verified.csv
├── experiments/
│   ├── ablation_results.csv
│   ├── baseline_results.csv
│   ├── feature_augmented_weights.csv
│   ├── mi_scores.csv
│   ├── results_summary.csv
│   └── shap_global_importance.csv
├── models/
│   ├── baselines/
│   └── wfa_xgb/
├── notebooks/
│   ├── 01_data_overview.ipynb
│   ├── 02_baseline_models.ipynb
│   ├── 03_shap_analysis.ipynb
│   ├── 04_feature_augmentation.ipynb
│   ├── 05_wfa_xgb_training.ipynb
│   ├── 06_evaluation.ipynb
│   └── 07_ablation_study.ipynb
├── reports/
│   ├── figures/
│   └── tables/
├── src/
│   ├── config/
│   │   ├── model_config.yaml
│   │   ├── training_config.yaml
│   │   └── paths.py
│   ├── data/
│   │   ├── load_data.py
│   │   └── split_data.py
│   ├── features/
│   │   ├── feature_augmentation.py
│   │   ├── mutual_information.py
│   │   ├── sample_weighting.py
│   │   └── shap_extractor.py
│   ├── models/
│   │   ├── baseline_models.py
│   │   ├── wfa_xgb.py
│   │   ├── xgb_focal_loss.py
│   │   └── calibrator.py
│   ├── evaluation/
│   │   ├── metrics.py
│   │   ├── ablation.py
│   │   └── statistical_tests.py
│   ├── explainability/
│   │   ├── shap_interactions.py
│   │   └── shap_plots.py
│   ├── training/
│   │   └── train_pipeline.py
│   └── utils/
│       ├── logger.py
│       └── seed.py
├── tests/
│   └── test_pipeline.py
├── requirements.txt
├── LICENSE
└── README.md

---
Setup Instructions
1. Prerequisites
Python 3.10+ (3.11 recommended)

Git installed

(Optional) virtualenv or conda
---
2. Clone the repository
bash
Copy code
git clone https://github.com/<YOUR_USERNAME>/wfa-xgb-cvd-prediction.git
cd wfa-xgb-cvd-prediction
---
3. Create & activate a virtual environment
bash
Copy code
python -m venv .venv

# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
---
4. Install dependencies
bash
Copy code
pip install --upgrade pip
pip install -r requirements.txt
Environment Variables
No mandatory environment variables are hard-coded.
---
Recommended for production:

env
Copy code
WFA_ENV=dev
WFA_LOG_LEVEL=INFO
WFA_DATA_ROOT=./data
Create a .env file locally (not committed).

Run Commands
1. Run notebooks
bash
Copy code
pip install jupyter
jupyter notebook
Open notebooks in order:

01_data_overview.ipynb

02_baseline_models.ipynb

03_shap_analysis.ipynb

04_feature_augmentation.ipynb

05_wfa_xgb_training.ipynb

06_evaluation.ipynb

07_ablation_study.ipynb
---
2. Run training pipeline (when implemented)
bash
Copy code
python -m src.training.train_pipeline
---
3. Run API (when implemented)
bash
Copy code
uvicorn app.api:app --reload
Build Commands (Optional)
bash
Copy code
cd app/frontend
npm install
npm run build
Testing Commands
bash
Copy code
pip install pytest
pytest -q
Deployment Notes
Treat models/ as generated artifacts.
---
Re-generate models using:

bash
Copy code
python -m src.training.train_pipeline
Store production models in object storage (S3, GCS) or a model registry.

Containerize API + models for production.

Add centralized logging in src/utils/logger.py.
---
Common Errors & Fixes
ModuleNotFoundError: No module named 'xgboost'
→ Run pip install -r requirements.txt.

ImportError: cannot import name 'XGBClassifier'
→ Pin:

text
Copy code
xgboost==1.7.6
MemoryError during SHAP/XGBoost
→ Reduce n_estimators, subsample data, or shrink SHAP background.
---
Notebooks cannot find data
→ Verify src/config/paths.py.

Inconsistent results
→ Ensure src/utils/seed.py is used.

Contribution Guidelines
bash
Copy code
git checkout -b feature/my-feature
Follow PEP 8

Add docstrings

Add/update tests

Commit format:

feat:, fix:, docs:, refactor:, chore: