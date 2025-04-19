<h1 align="center">USAJOBS Automated Data Acquisition & Data Buyer Lead Generation</h1>

## 📖 Overview
This module provides a fully automated pipeline to identify potential public sector third-party data buyers by leveraging the USAJOBS API and a trained NLP classification model.

It includes:
- End-to-end data acquisition and labeling
- Pretrained model inference
- Export of prioritized lead lists for outreach or analysis

---

## 📁 Folder Contents

### 1. `API Call and Full Automatic Data Generator.ipynb`

Fetches and labels federal job postings from the [USAJOBS API](https://developer.usajobs.gov/). Outputs structured `.csv` files ready for modeling.

**Key Features:**
- Fully automated API call and job post wrangling
- Label generation using custom keyword rules
- Output saved in consistent, analysis-ready format

---

### 2. `Automated Modeling and Lead Generating.ipynb`

Uses the labeled job data to classify postings as likely third-party data buyers using a pretrained logistic regression model.

**Workflow Includes:**
- Loading raw and structured job data
- Preprocessing: text vectorization, categorical encoding, feature engineering
- Inference using pretrained `.pkl` model assets
- Export of predicted leads with:
  - `PredictedLabel`: Binary classification (1 = likely buyer)
  - `DataBuyerScore`: Model-predicted probability of buyer status

---

### 3. Pretrained Model Assets (`.pkl`)

These serialized objects are required for running the lead generation notebook without retraining:

| File              | Purpose                             |
|-------------------|-------------------------------------|
| `vectorizer.pkl`  | TF-IDF vectorizer for job descriptions |
| `transformers.pkl`| Preprocessing pipeline for structured data |
| `classifier.pkl`  | Logistic regression classifier       |

> To retrain with new data, use `joblib.dump()` to overwrite these files after fitting your new model pipeline.

---

## ⚙️ Customization

All keyword-based label logic is defined inside the `keywords` variable in the data acquisition notebook. You can easily tailor this to target different job types:

- Cybersecurity roles  
- Behavioral research  
- Geospatial analysis  
- Agency-specific analytics  

This pipeline is modular and can be adapted for additional classification use cases beyond data buyers.

---

## 📦 Dependencies

Ensure the following Python libraries are installed:

- `python 3.8+`
- `requests`
- `pandas`
- `scikit-learn`
- `joblib`

Use `pip install -r requirements.txt` if a requirements file is provided.

---

## 📄 Citation

If this pipeline contributes to your research, outreach, or internal modeling, please cite or link back to this repository.

