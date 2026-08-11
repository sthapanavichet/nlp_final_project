# AI-Generated Text Detection

SEA 820 NLP Final Project

## Overview

This project compares a classic NLP baseline with a fine-tuned Transformer for classifying text as human-written (`0`) or AI-generated (`1`). The baseline combines TF-IDF bigram features with Logistic Regression. The advanced model fine-tunes `distilbert-base-uncased` using Hugging Face Transformers.

## Repository structure

```text
AI_Text_Detector_Colab.ipynb  Complete training and evaluation notebook
README.md                     Setup and reproduction instructions
PROJECT_PLAN.md               Three-week plan and team assignments
Final_Report.docx             Report draft; replace marked result fields
Final_Report.pdf              PDF copy of the report draft
Presentation.pptx             5-7 minute presentation deck
Presentation.pdf              PDF copy of the presentation
```

## Run in Google Colab

1. Open `AI_Text_Detector_Colab.ipynb` in Google Colab.
2. Select **Runtime > Change runtime type > T4 GPU**.
3. Run the notebook cell.
4. Wait for training to finish. The default run uses a reproducible stratified sample of 12,000 documents.
5. Download `/content/ai_text_detector_results` after execution.

The public Kaggle dataset is downloaded automatically. If Kaggle requests authentication, upload your Kaggle API token in Colab when prompted.

## Optional configurations

Run a fast pipeline check before the full experiment:

```python
%env MAX_SAMPLES=4000
%env EPOCHS=1
```

For the final experiment, restart the runtime and use:

```python
%env MAX_SAMPLES=12000
%env EPOCHS=2
%env BATCH_SIZE=16
%env MAX_LENGTH=256
```

For an additional hyperparameter experiment, change only one variable at a time, such as `LEARNING_RATE=3e-5` or `MAX_LENGTH=128`, then record the resulting test metrics.

## Generated outputs

- `model_comparison.csv`: accuracy, precision, recall, and F1 for both models
- `eda.png`: class balance and text-length distributions
- `transformer_confusion_matrix.png`: Transformer confusion matrix
- `baseline_errors.csv`: baseline false positives and false negatives
- `transformer_errors.csv`: Transformer false positives and false negatives
- `tfidf_logistic_regression.joblib`: saved classic model
- `distilbert_detector/`: saved Transformer model and tokenizer
- `train.csv`, `validation.csv`, `test.csv`: reproducible dataset splits

## Reproducibility

The random seed defaults to `42`. Sampling and all dataset splits are stratified. Software dependencies are installed by the notebook. Hardware, package updates, and nondeterministic GPU operations may cause small differences between runs.

## Limitations and responsible use

This system is a research classifier, not proof of authorship or misconduct. Its decisions can reflect dataset bias, topic differences, text length, editing style, and model-family coverage. Results should be reviewed by a person and supported by independent evidence. The detector should not be used as the sole basis for disciplinary action.

## Dataset

Shane Gerami, [AI vs Human Text](https://www.kaggle.com/datasets/shanegerami/ai-vs-human-text), Kaggle.

