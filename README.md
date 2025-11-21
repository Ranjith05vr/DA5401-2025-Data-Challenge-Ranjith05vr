# DA5401 Competition - Incremental Improvements Pipeline

This repository contains the code for the DA5401 competition solution featuring improved feature engineering, model training, ensemble prediction, and calibration. It includes data visualizations to aid analysis.

---

## Requirements

- Python 3.7+
- Packages (install via pip):
pip install numpy pandas scikit-learn matplotlib seaborn sentence-transformers catboost xgboost lightgbm


- Jupyter Notebook or JupyterLab recommended for running the code and viewing plots inline.

---

## Data Files Needed

Place the following files in the same directory as the script before running:

- `train_data.json`: Training data with text and score fields.
- `test_data.json`: Test data for prediction.
- `metric_names.json`: List of metric names used in embeddings.
- `metric_name_embeddings.npy`: Precomputed embeddings for each metric name.

---

## How to Run

1. Open the Jupyter notebook or Python script.
2. Run the code cells or execute the script sequentially.
3. The script performs:

 - Loading and encoding of text and metric embeddings.
 - Feature engineering with original and new distance/similarity features.
 - Feature scaling and train-validation splitting.
 - Training three base models (CatBoost, XGBoost, LightGBM) with tuned hyperparameters.
 - Additional CatBoost quantile model training for distribution shift handling.
 - Weighted ensemble prediction.
 - Isotonic regression calibration on validation set.
 - Post-processing shift correction to match target mean.
 - Saving final predictions in `submission.csv`.

4. Visualization plots are saved as `viz_*.png` files and displayed inline (if using notebook).

---

## Output

- `submission.csv`: CSV file with predicted scores for the test set.
- Visualization PNG files showing distributions, scatter plots, and prediction diagnostics.
- Console logs show training progress and statistics.

---

## Notes

- To see plots inline and save them, plotting functions include both `plt.savefig()` and `plt.show()`.
- Ensure data files are correctly formatted and embeddings are consistent with metric names.
- The environment should have compatible versions of Jupyter widgets if using interactive outputs (see troubleshooting for widget errors).

---

## Troubleshooting

- Widget version mismatch errors in JupyterLab: Update `ipywidgets` and rebuild JupyterLab extensions.
- `NameError` for `metric_emb_dict`: Confirm metric embeddings and metric names files load correctly and run full script from top.
- Install missing Python packages using pip.

---

## References

- [CatBoost](https://catboost.ai/)
- [XGBoost](https://xgboost.readthedocs.io/)
- [LightGBM](https://lightgbm.readthedocs.io/)
- [Sentence Transformers](https://www.sbert.net/)
- [Scikit-learn](https://scikit-learn.org/)

---

## Author
- Ranjith V R
- EE24S034
- MS Research Scholar
