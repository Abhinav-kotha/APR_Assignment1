# Anime Score Classification using SVM

## Overview
This project classifies anime shows into **score categories** (`Very Good`, `Good`, `Average`, `Low`) based on their metadata such as episodes, duration, genres, producers, studios, licensors, source material, and rating.

The task is part of **Assignment-1** for the Applied Pattern Recognition (APR) course.

---

## Dataset
- **Name:** Anime Dataset (`anime.csv`)
- **Source:** Public dataset containing anime metadata and scores.
- **Target Variable:** `Score_Class` (derived from numeric score)
  - `Very Good`: Score ≥ 8.0
  - `Good`: 7.0 ≤ Score < 8.0
  - `Average`: 6.0 ≤ Score < 7.0
  - `Low`: Score < 6.0

---

## Algorithm
We used **Support Vector Machine (SVM)** for classification with the following steps:
1. Data cleaning and preprocessing (handling missing values, numeric conversion).
2. Feature engineering:
   - Duration converted to minutes.
   - Multi-label features (Genres, Producers, Studios, Licensors) encoded using top-K binary features.
   - Source and Rating one-hot encoded.
3. Feature scaling using `StandardScaler`.
4. Training an **SVM classifier** on the processed features.

---

## Results
- **Accuracy:** ~63.5%
- **Observations:**
  - Best performance on `Average` and `Low` classes.
  - Fewer samples in `Very Good` class led to low recall (~0.40).
- **Future Improvements:**
  - Hyperparameter tuning (kernel, C, gamma).
  - Ensemble classifiers (Random Forest, XGBoost).
  - Dimensionality reduction (PCA, feature selection).
  - Use embeddings for multi-label categorical features.

---

## Requirements
Install the following dependencies before running the notebook:
```bash
pip install pandas numpy scikit-learn matplotlib
```

---

## Running the Project
1. Clone the repository:
   ```bash
   git clone <https://github.com/Abhinav-kotha/APR_Assignment1/tree/main>
   cd anime-svm-classifier
   ```
2. Place the dataset file (`anime.csv`) in the project folder.
3. Run the Jupyter notebook:
   ```bash
   jupyter notebook APR_Assignment1.ipynb
   ```

---

## Repository Structure
```
.
├── APR_Assignment1.ipynb   # Main Jupyter notebook with code and analysis
├── anime.csv               # Dataset file 
├── README.md               # Project overview and instructions
└── report.pdf              # Detailed project report
```

---

## Author
- **Name:** Abhinav Reddy  
- **Roll No:** 2201AI20  
