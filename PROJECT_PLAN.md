# SEA 820 NLP Final Project Plan

**Project:** Detecting AI-Generated Text  
**Team:** [Student 1] and [Student 2]  
**Duration:** Three weeks

## Goal

Build and compare a TF-IDF classic classifier and a fine-tuned DistilBERT classifier, evaluate both with accuracy, precision, recall, and F1, inspect errors, and discuss the ethical limits of AI-text detection.

## Week 1: Data and baseline

- Student 1: repository setup, dataset download, data validation, class-distribution analysis, and text-length plots.
- Student 2: TF-IDF pipeline, Logistic Regression training, baseline metrics, and reproducibility checks.
- Joint checkpoint: review preprocessing choices, confirm the stratified train/validation/test split, and record baseline results.

## Week 2: Transformer experiments

- Student 1: Hugging Face dataset conversion, tokenizer setup, DistilBERT fine-tuning, and model checkpoint management.
- Student 2: hyperparameter log, metric comparison, confusion matrix, and experiment reproducibility.
- Joint checkpoint: select the strongest valid model based primarily on F1 while considering precision and recall.

## Week 3: Analysis and submission

- Student 1: false-positive analysis, false-negative analysis, limitations, and ethical discussion.
- Student 2: report integration, figures and tables, README, and presentation draft.
- Joint tasks: verify all claims against saved outputs, rehearse the 5-7 minute presentation, check repository links, and submit the notebook, report PDF, and slide PDF.

## Acceptance criteria

- Both required model families run from a clean Colab session.
- The same held-out test set is used for final comparison.
- Accuracy, precision, recall, and F1 are reported for both models.
- At least three false positives and three false negatives are examined.
- No fabricated measurements appear in the report or slides.
- Ethical risks and intended-use limits are stated clearly.

