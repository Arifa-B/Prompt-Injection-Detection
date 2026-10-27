# Machine Learning for Prompt Injection Detection in AI Applications

## Overview

This project evaluates whether traditional machine learning models can distinguish malicious prompt injection attempts from benign inputs to Large Language Model (LLM) applications. The goal is to assess lightweight text classifiers as a potential screening layer in a defense-in-depth AI security architecture.

## Dataset

[Prompt Injection & Jailbreak Detection Dataset — Hugging Face]

The project uses the dataset's `core` configuration, containing labeled benign and malicious prompts.

## Models

- **Multinomial Naive Bayes** — baseline text classifier
- **Logistic Regression** — linear classification baseline
- **Linear Support Vector Machine (SVM)** — high-dimensional text classification

Prompts are converted into numerical features using TF-IDF vectorization.

## Methodology

1. Load and inspect the dataset, including class distribution, missing values, and duplicates.
2. Prepare the text data and preserve the provided train/validation/test splits.
3. Apply TF-IDF vectorization, fitting the vectorizer on training data only.
4. Train the three classifiers and tune hyperparameters using cross-validation.
5. Evaluate the selected models on the held-out test set.
6. Analyze false positives, false negatives, and detection performance across attack categories where feasible.

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Precision-Recall AUC (PR-AUC / Average Precision)
- Confusion matrix and false-positive rate

Recall and F1-score are emphasized to assess attack detection while accounting for false alarms.

## Security Relevance

The project explores the potential and limitations of ML-based prompt injection detection as one layer of AI application security. A text classifier cannot guarantee detection of novel attacks and does not replace authorization controls, least privilege, or other defense-in-depth measures.

## Tech Stack

Python · pandas · scikit-learn · Hugging Face Datasets

## Project Status

In progress — dataset preparation, model training, and evaluation are planned.

## Disclaimer

This project is for educational and research purposes.
