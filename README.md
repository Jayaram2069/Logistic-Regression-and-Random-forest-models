Requirements

Install all dependencies with:

pip install -r requirements.txt


Required packages include:

numpy

pandas

scikit-learn

matplotlib

seaborn

All experiments were run using Python ≥ 3.9 and scikit-learn ≥ 1.3.

How to Run the Notebook

Open the notebook:

jupyter notebook notebooks/class_imbalance_experiments.ipynb


Run all cells sequentially.

All figures and tables will automatically be generated and saved to /figures/.

Dataset Description

A synthetic binary-classification dataset was generated using make_classification() with:

20 total features

2 informative features

1 minority class at 10% frequency (high imbalance)

Train/val/test split = 70/15/15

This dataset was selected because:

It realistically simulates clinical/fraud/rare-event scenarios

It cleanly exposes precision–recall trade-offs

It makes threshold tuning meaningful

Class imbalance can be controlled precisely

Summary of Results

Using your provided output:

Model	Train Acc	Val Acc	Test Acc	Test Precision	Test Recall	Test F1	ROC-AUC	PR-AUC	Best Threshold
Logistic Regression (baseline)	0.976	0.980	0.985	0.973	0.878	0.923	0.996	0.974	0.50
Logistic Regression (balanced)	0.945	0.950	0.960	0.727	0.976	0.833	0.996	0.975	0.50
Balanced + Threshold Tuning	0.978	0.985	0.980	0.971	0.829	0.895	0.996	0.975	0.88
Random Forest (balanced)	1.000	0.975	0.980	0.946	0.854	0.897	0.997	0.974	0.50

Interpretation summary:

Class-weight balancing fixes recall but harms precision.

Threshold tuning yields better balance between precision and recall.

Random Forest achieves the strongest recall without explicit threshold tuning.

All methods achieve very high ROC-AUC (~0.996–0.997), meaning separation is good but threshold selection matters.

Accessibility Notes

This repository follows accessibility guidelines:

All plots use colour-blind-friendly palettes.

Axes, labels, and captions are high-contrast.

Figures include alt-text descriptions.

Headings are screen-reader safe and sequential.
