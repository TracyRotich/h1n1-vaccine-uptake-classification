# H1N1 Vaccine Uptake Classification

A supervised-learning project that explores the factors associated with H1N1 vaccination and compares classification models for public-health decision support.

## Decision context

Public-health teams need to identify groups that may be less likely to receive a vaccine so that outreach can be targeted effectively. The useful model is therefore not simply the one with the highest accuracy: precision, recall, discrimination, calibration and the operational cost of false decisions all matter.

This framing mirrors actuarial work, where risk classification must combine predictive performance with interpretability, fairness and practical consequences.

## Objectives

- Explore demographic, behavioural and attitudinal factors related to vaccination.
- Prepare mixed numerical and categorical survey data for modelling.
- Compare logistic regression, decision tree and random forest classifiers.
- Translate model results into practical outreach considerations.

## Data and workflow

The project uses features and labels from the National 2009 H1N1 Flu Survey. The analysis includes missing-data treatment, exploratory analysis, categorical encoding, class-imbalance handling, model fitting and evaluation with accuracy, precision, recall, F1 and ROC-AUC.

## Reported model results

| Model | Accuracy | F1 | ROC-AUC | Main observation |
|---|---:|---:|---:|---|
| Logistic regression | 0.75 | 0.75 | 0.828 | Interpretable baseline with moderate discrimination |
| Decision tree | 0.83 | 0.83 | 0.896 | Best reported balance across the selected metrics |
| Random forest | 0.83 | 0.81 | 0.800 | Low recall for the vaccinated class in the reported run |

The notebook selects the decision tree because it reports the strongest overall balance, including class-1 precision of 0.87 and ROC-AUC of 0.896.

## Practical interpretation

- Outreach strategy should focus on patterns associated with concern, perceived risk, health behaviour and access.
- False negatives and false positives should be costed according to the intended intervention.
- Model scores should support, rather than replace, public-health judgment.

## Project outputs

- [Technical notebook](Phase_3_Project_Jupyter_Notebook%20_H1N1_Seasonal_flu_dataset_Machine_learning.ipynb)
- [Non-technical report](NON-TECHNICAL%20REPORT%20%20FOR%20H1N1%20PREDICTION%20MODEL%20FINAL2.pdf)
- `Functions_notebook.ipynb` contains supporting reusable functions.

## Tools

Python, pandas, NumPy, scikit-learn, imbalanced-learn, statsmodels, Matplotlib, seaborn and Jupyter.

## Reproduce the analysis

1. Clone the repository.
2. Create a Python environment with the tools listed above.
3. Open the technical notebook and run the cells in order.

## Limitations and next iteration

The metrics above are those reported in the current notebook and should be treated as development results. A stronger next version should place preprocessing and resampling inside a pipeline, use stratified cross-validation, reserve an untouched test set, tune the decision threshold, report calibration, and examine subgroup performance and fairness. Those checks are required before any real outreach use.
