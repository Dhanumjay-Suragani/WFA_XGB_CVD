# Current Complete Folder Structure - wfa_xgb_cvd_prediction

**As of:** Current State (No files removed)

```
wfa_xgb_cvd_prediction/
│
├── 📁 app/
│   ├── api.py
│   ├── 📁 backend/                    [empty]
│   └── 📁 frontend/                   [empty]
│
├── 📁 data/
│   ├── feature_metadata.json
│   ├── 📁 processed/
│   │   ├── heart_disease_processed.csv
│   │   └── heart_Verified.csv
│   └── 📁 raw/                        [empty]
│
├── 📁 experiments/
│   └── results_summary.csv
│
├── 📁 models/
│   ├── 📁 baseline/                   [empty]
│   ├── 📁 baselines/
│   │   └── baseline_models.pkl
│   └── 📁 wfa_xgb/
│       ├── calibrator_model.h5
│       ├── shap_background.npy
│       └── wfa_xgb_model.json
│
├── 📁 notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 01_data_overview.ipynb
│   ├── 02_baseline_models.ipynb
│   ├── 03_shap_analysis.ipynb
│   ├── 04_feature_augmentation.ipynb
│   ├── 05_wfa_xgb_training.ipynb
│   ├── 06_evaluation.ipynb
│   └── 07_ablation_study.ipynb
│
├── 📁 reports/
│   ├── 📁 draft_paper/                [empty]
│   ├── 📁 figures/
│   │   ├── .gitkeep
│   │   ├── 📁 calibration_plots/      [empty]
│   │   ├── 📁 roc_curves/             [empty]
│   │   └── 📁 shap_summary/           [empty]
│   └── 📁 tables/
│       └── .gitkeep
│
├── 📁 src/
│   ├── 📁 config/
│   │   ├── model_config.yaml
│   │   ├── paths.py
│   │   └── training_config.yaml
│   │
│   ├── 📁 data/
│   │   ├── load_data.py
│   │   └── split_data.py
│   │
│   ├── 📁 deployment/                 [empty]
│   │
│   ├── 📁 evaluation/
│   │   ├── ablation.py
│   │   ├── metrics.py
│   │   └── statistical_tests.py
│   │
│   ├── 📁 explainability/
│   │   ├── shap_interactions.py
│   │   └── shap_plots.py
│   │
│   ├── 📁 features/
│   │   ├── feature_augmentation.py
│   │   ├── mutual_information.py
│   │   ├── sample_weighting.py
│   │   └── shap_extractor.py
│   │
│   ├── 📁 models/
│   │   ├── baseline_models.py
│   │   ├── calibrator.py
│   │   ├── wfa_xgb.py
│   │   └── xgb_focal_loss.py
│   │
│   ├── 📁 training/
│   │   └── train_pipeline.py
│   │
│   └── 📁 utils/
│       ├── logger.py
│       └── seed.py
│
├── 📁 tests/
│   └── test_pipeline.py
│
├── 📁 wfa_xgb_cvd_prediction/         [nested folder]
│   ├── .gitignore
│   ├── 📁 app/
│   │   ├── 📁 backend/
│   │   │   ├── main.py
│   │   │   └── requirements.txt
│   │   └── 📁 frontend/
│   │       └── index.html
│   ├── 📁 experiments/
│   │   └── experiment_log.json
│   └── 📁 src/
│       └── 📁 deployment/
│           ├── inference.py
│           ├── model_loader.py
│           └── response_schema.py
│
├── FOLDER_STRUCTURE.md
├── LICENSE
├── README.md
└── requirements.txt
```

## File & Directory Statistics

### Total Counts:
- **Total Directories**: 29 (including nested and empty)
- **Total Python Files**: 26 (.py files)
- **Total Notebooks**: 8 (.ipynb files)
- **Total Config Files**: 3 (2 YAML, 1 Python)
- **Total Data Files**: 3 (CSV files)
- **Total JSON Files**: 2 (feature_metadata.json, experiment_log.json)
- **Total Binary Files**: 4 (.pkl, .h5, .npy)
- **Total Markdown Files**: 3 (README.md, FOLDER_STRUCTURE.md, CURRENT_FOLDER_STRUCTURE.md)
- **Empty Directories**: 8

### Empty Directories List:
1. `app/backend/`
2. `app/frontend/`
3. `data/raw/`
4. `models/baseline/`
5. `reports/draft_paper/`
6. `reports/figures/calibration_plots/`
7. `reports/figures/roc_curves/`
8. `reports/figures/shap_summary/`
9. `src/deployment/` (in root)
10. `wfa_xgb_cvd_prediction/src/deployment/` (in nested folder)

### Python Files (26):
1. `app/api.py`
2. `src/config/paths.py`
3. `src/data/load_data.py`
4. `src/data/split_data.py`
5. `src/evaluation/ablation.py`
6. `src/evaluation/metrics.py`
7. `src/evaluation/statistical_tests.py`
8. `src/explainability/shap_interactions.py`
9. `src/explainability/shap_plots.py`
10. `src/features/feature_augmentation.py`
11. `src/features/mutual_information.py`
12. `src/features/sample_weighting.py`
13. `src/features/shap_extractor.py`
14. `src/models/baseline_models.py`
15. `src/models/calibrator.py`
16. `src/models/wfa_xgb.py`
17. `src/models/xgb_focal_loss.py`
18. `src/training/train_pipeline.py`
19. `src/utils/logger.py`
20. `src/utils/seed.py`
21. `tests/test_pipeline.py`
22. `wfa_xgb_cvd_prediction/app/backend/main.py`
23. `wfa_xgb_cvd_prediction/src/deployment/inference.py`
24. `wfa_xgb_cvd_prediction/src/deployment/model_loader.py`
25. `wfa_xgb_cvd_prediction/src/deployment/response_schema.py`

### Notebooks (8):
1. `notebooks/01_data_exploration.ipynb`
2. `notebooks/01_data_overview.ipynb`
3. `notebooks/02_baseline_models.ipynb`
4. `notebooks/03_shap_analysis.ipynb`
5. `notebooks/04_feature_augmentation.ipynb`
6. `notebooks/05_wfa_xgb_training.ipynb`
7. `notebooks/06_evaluation.ipynb`
8. `notebooks/07_ablation_study.ipynb`

### Configuration Files:
- `src/config/model_config.yaml`
- `src/config/training_config.yaml`
- `requirements.txt` (at root)
- `wfa_xgb_cvd_prediction/app/backend/requirements.txt` (nested)

### Data Files:
- `data/feature_metadata.json`
- `data/processed/heart_disease_processed.csv`
- `data/processed/heart_Verified.csv`

### Model Files (Placeholders/Generated):
- `models/baselines/baseline_models.pkl`
- `models/wfa_xgb/calibrator_model.h5`
- `models/wfa_xgb/shap_background.npy`
- `models/wfa_xgb/wfa_xgb_model.json`

### Documentation Files:
- `LICENSE`
- `README.md`
- `FOLDER_STRUCTURE.md`
- `CURRENT_FOLDER_STRUCTURE.md`

### Other Files:
- `wfa_xgb_cvd_prediction/.gitignore`
- `experiments/results_summary.csv`
- `wfa_xgb_cvd_prediction/experiments/experiment_log.json`
- `wfa_xgb_cvd_prediction/app/frontend/index.html`
- `reports/figures/.gitkeep`
- `reports/tables/.gitkeep`

## Notes:

- ⚠️ **Nested Folder**: There is a nested `wfa_xgb_cvd_prediction/` folder inside the main project with additional files. This may be intentional or accidental.
- All empty directories are preserved as shown
- No files or directories have been removed
- Structure includes both specified structure files and additional files that were created
