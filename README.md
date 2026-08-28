# Clinical Data Parsing & Machine Learning Pipeline

A modular engineering workflow for automated text extraction, clinical data anonymization, preprocessing, and machine learning classification of medical records. Developed as part of a diploma thesis in Computer Engineering and Informatics.

## Repository Structure

```text
├── html/                        # Exported HTML versions of Jupyter notebooks
├── Models/                      # Model checkpoints and trained weights (git-ignored)
├── extraction.ipynb             # Raw PDF text extraction and parsing pipeline
├── anonimise.ipynb              # Patient data anonymization and privacy masking
├── preprocess.ipynb             # Data cleaning, normalization, and feature engineering
├── RandomForest.ipynb            # Random Forest classifier training and evaluation
├── XGBoost.ipynb                # Extreme Gradient Boosting model pipeline
├── HistBoost.ipynb              # Histogram-based Gradient Boosting implementation
├── Model_Hierarchical.ipynb     # Hierarchical classification modeling using XGBoost
├── Final_Comparison.ipynb       # Comparative performance analysis across models
├── Patient_Predictor.ipynb      # Real-time inference script for clinical triage
└── .gitignore                   # Exclusion rules for sensitive data, PDFs, and model weights
```

## Workflow & Pipeline Architecture

- **Extraction (`extraction.ipynb`):** Scans multi-year raw hospital PDF archives (e.g., biochemical, cardiovascular, and renal datasets) to extract unstructured text blocks while maintaining structural layout integrity.

- **Anonymization (`anonimise.ipynb`):** Strips and masks protected health information (PHI) and sensitive patient identifiers to ensure compliance and data privacy.

- **Preprocessing (`preprocess.ipynb`):** Applies regular expressions (Regex) and heuristic list-reversal algorithms to resolve token fragmentation, aligning biomarker values (e.g., TSH, Free T4) with their respective clinical keys.

- **Modeling & Classification:** Trains optimized tree-based ensemble algorithms (Random Forest, XGBoost, and Histogram-based Gradient Boosting) capable of capturing non-linear biological relationships.

- **Hierarchical Optimization & Key Finding:** Through comparative evaluation, empirical analysis demonstrated that a multi-stage hierarchical architecture (`Model_Hierarchical.ipynb` and `Hist_Hierarchical.ipynb`) yields the highest clinical predictive performance. By decomposing the problem into staged routing (first separating general outpatients from systemic illness, then sub-routing specialized wards), the pipeline successfully overcomes overlapping biomarker distributions.

- **Inference & Triage (`Patient_Predictor.ipynb`):** Implements a real-time deployment script using the top-performing hierarchical model checkpoints for automated clinical decision support.

- **Evaluation & Comparison (`Final_Comparison.ipynb`):** Benchmarks all approaches using rigorous performance metrics (Precision, Recall, F1-Score). Empirical evaluation demonstrates that both flat ensemble models and the multi-stage hierarchical architecture achieve comparable baseline accuracies (~65–67%), with detailed error analysis provided in the thesis document.

## Privacy & Security Note

To comply with data protection regulations and patient confidentiality, all raw clinical datasets (`*.pdf`, `*.csv`) and trained model binary weights (`*.pkl`) are excluded from version control via the `.gitignore` configuration. Only the source notebooks and architecture logic are tracked.

## Installation & Requirements

Ensure Python 3.10+ is installed, then install the required machine learning and data processing libraries:

```bash
pip install pandas numpy scikit-learn xgboost lightgbm PyMuPDF jupyter joblib
```

## Author

**Panagiotis Chaidos**

Department of Computer Engineering and Informatics (CEID)  
University of Patras
