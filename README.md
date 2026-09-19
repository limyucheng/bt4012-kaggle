# BT4012 Fraud Analytics Kaggle Competition

This repository contains my submission for the BT4012 Fraud Analytics Kaggle competition.

The task is to predict the probability that a Bitcoin transaction is illicit. The dataset contains anonymised transaction features together with a directed transaction graph.

## Approach

My modelling process was:

1. Remove transactions with unknown labels from supervised training.
2. Use the 165 provided transaction features.
3. Create additional graph features using the transaction edge list.
4. Use a chronological validation split instead of a random split, since the test set occurs at later time steps.
5. Compare logistic regression against LightGBM.
6. Train the selected LightGBM model using the labelled training data and generate probabilities for the test set.

For validation, I trained on time steps 1-30 and validated on time steps 31-35. The evaluation metric used is ROC-AUC.

## Repository Structure

```text
.
├── e1120977.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── data/
    └── README.md
