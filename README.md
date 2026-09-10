# Solar Power Output Predictor

Predict solar power generation from weather and system data using machine learning. This repository contains data preprocessing, model training, evaluation, and example notebooks to reproduce results.

Badges
- Build / CI: ![CI](https://img.shields.io/badge/ci-passing-brightgreen) (add real CI later)
- License: ![License](https://img.shields.io/badge/license-MIT-blue)
- Python version: ![Python](https://img.shields.io/badge/python-3.8%2B-blue)

Table of contents
- [Demo](#demo)
- [Features](#features)
- [Getting started](#getting-started)
  - [Requirements](#requirements)
  - [Install](#install)
- [Usage](#usage)
  - [Quick start](#quick-start)
  - [Run training](#run-training)
  - [Run inference](#run-inference)
- [Data](#data)
- [Model & results](#model--results)
- [Reproducing experiments](#reproducing-experiments)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

Demo
Include a short GIF or image here showing predictions vs ground truth (add screenshots under `docs/` or `assets/`).

Features
- Preprocessing pipeline for weather and PV-system inputs
- Baseline models (Linear Regression, Random Forest)
- Neural network models for time-series regression
- Training scripts and Jupyter notebooks for analysis
- Evaluation metrics: RMSE, MAE, R²

Getting started

Requirements
- Python 3.8 or newer
- Recommended: 8+ GB RAM (depending on dataset size)
- Optional: GPU for deep learning training

Install
1. Clone the repo:
   git clone https://github.com/sanjayrobin28/Solar-Power-Output-Predictor.git
   cd Solar-Power-Output-Predictor

2. Create virtual environment and install:
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate     # Windows
   pip install -r requirements.txt

If you don't have a requirements.txt yet, create one with packages used (e.g., scikit-learn, pandas, numpy, matplotlib, tensorflow/torch).

Usage

Quick start (example)
- Preprocess data:
  python src/preprocess.py --input data/raw/solar.csv --output data/processed/solar_processed.csv

- Train a model:
  python src/train.py --data data/processed/solar_processed.csv --model random_forest --output models/rf.pkl

- Evaluate:
  python src/evaluate.py --model models/rf.pkl --data data/processed/solar_processed.csv

- Predict on new data:
  python src/predict.py --model models/rf.pkl --input data/new_samples.csv --output predictions.csv

Run training (detailed)
See `src/train.py` or `notebooks/training.ipynb` for options:
- --model: linear_regression | random_forest | mlp
- --epochs: (for neural nets)
- --batch-size, --learning-rate, etc.

Run inference
Use `src/predict.py` or load saved model in notebooks to run batch predictions.

Data
Describe or link to the dataset(s) used, e.g.:
- Source: [PVDAQ / Local dataset / Kaggle link] (replace with actual source)
- Columns: timestamp, irradiance, temperature, wind_speed, panel_angle, system_capacity, measured_power
- Preprocessing steps: timezone normalization, missing-value handling, outlier filtering, feature engineering (lag features, rolling means, sin/cos for time-of-day)

Model & results
- Baseline results (placeholders — update with real numbers):
  - Linear Regression — RMSE: 0.45 kW, R²: 0.72
  - Random Forest — RMSE: 0.30 kW, R²: 0.86
  - MLP — RMSE: 0.28 kW, R²: 0.88

Include a `results/` folder with plots: predicted vs actual, residuals, feature importance.

Reproducing experiments
- Fix random seeds (show how in README or config)
- Provide example config files in `configs/` for runs
- Use notebooks in `notebooks/` to replicate key figures and tables
- Add a requirements.txt and mention hardware (CPU/GPU) used for experiments

Project structure (example)
- data/ — raw and processed datasets (do NOT commit raw private data)
- src/
  - preprocess.py
  - train.py
  - predict.py
  - evaluate.py
- models/ — saved model files
- notebooks/ — exploratory analysis and experiments
- docs/ or assets/ — images, screenshots
- requirements.txt
- LICENSE
- CONTRIBUTING.md

Contributing
- Please open issues for bugs and feature requests.
- To contribute: fork the repo, create a branch, add tests if possible, and open a PR.
- Add a `CONTRIBUTING.md` with contribution guidelines and coding style.

License
This project is licensed under the MIT License — see the LICENSE file for details.

Contact
Your Name — your.email@example.com  
Project link: https://github.com/sanjayrobin28/Solar-Power-Output-Predictor

Acknowledgements
- Mention datasets, libraries, or papers you used (e.g., scikit-learn, TensorFlow, relevant papers).

References
- Add references to papers or tutorials used to design the models or preprocessing.
