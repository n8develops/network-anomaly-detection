# Network Anomaly Detection Using Machine Learning

This project aims to detect malicious network activity (for example, DDoS traffic) by training machine learning models on real network flow data.

The goal: automatically classify traffic as normal (BENIGN) or attack by learning patterns in features like packet counts, byte rates, and flow duration.

## Current Progress

- Set up an isolated Python environment (`venv`) and installed pandas / scikit-learn / jupyter.
- Loaded a 50,000-row slice of the CICIDS2017 dataset into pandas.
- Cleaned column names.
- Inspected dataset shape and first few rows.
- Counted how many rows are BENIGN vs DDoS.

See `notebooks/01_data_exploration.ipynb` for this work.

## Next Steps

- Build a smaller feature set (duration, packets, bytes/sec, etc.).
- Create a binary label (`is_attack`: 0 = BENIGN, 1 = attack).
- Train a RandomForestClassifier to predict `is_attack`.
- Evaluate model performance using precision/recall.
- Add an anomaly detection model (Isolation Forest) to flag unusual network behavior.

## Tools / Stack

- Python
- pandas (data loading / cleanup)
- scikit-learn (ML models)
- Jupyter Notebook (experiments)
- CICIDS2017 dataset

## Dataset

This repo uses the CICIDS2017 dataset from the Canadian Institute for Cybersecurity.  
The dataset is **not** included in this repo due to size and licensing.

See `data/README.md` for instructions on obtaining it.

## Reproducing the environment

```bash
python -m venv venv
.\venv\Scripts\activate    # on Windows
pip install -r requirements.txt
jupyter notebook
