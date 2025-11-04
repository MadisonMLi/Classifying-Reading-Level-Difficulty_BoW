## Project Summary: Automatic Reading Level Assessment

This project aims to automate the assessment of reading difficulty for text passages to better support students’ reading development. Traditionally, determining a passage’s reading level is done manually—a time-consuming process that limits the availability of appropriately leveled texts and leads to repetitive, one-size-fits-all reading assignments.

To address this, the project develops a machine learning pipeline that automatically classifies text passages by reading level. The approach involves:



**Feature engineering:** Using a Bag-of-Words (BoW) representation to convert text into numerical features. scikit-learn TfidfVectorizer (tuned `min_df`, `max_df`, `ngram_range`, `English stop words`).

**Classifier:** logistic regression (L2) with hyperparameter C (inverse regularization) tuned by grid search. Revising the pipeline based on evaluation results to improve accuracy and robustness.

**Evaluation:** Assessing the classifier’s performance on held-out test data to measure generalization ability. 5‑fold cross validation (`AUROC / roc_auc`) used for model selection. We also compute out‑of‑fold predictions with   cross_val_predict   for fair error analysis.

**Submission:** the notebook writes predictions for `x_test.csv` to   yproba1_test.txt   (integer labels).




## Data citation

This dataset comes from research work by Jordan J. Bird, released in December 2024.
His raw dataset, *UK Key Stage Readability for English Texts* is [available on Kaggle](https://www.kaggle.com/datasets/birdy654/uk-key-stage-readability-for-english-texts) under an MIT license. 

Note that we (the staff of CS 135) have *remixed* the original data, developing our own training and test sets for the purposes of this project. Performance on project A should not be directly comparable to the research by Dr. Bird reported in the manuscript below. Primary differences include a smaller train set (roughly 6000 instead of much more) due to our desire to intentionally limit the number of passages from the same literary work. We also ensure authors in train set never appear in the test set.

<blockquote style="margin-left: 5em">
<p>
  <a href="https://arxiv.org/pdf/2411.17593">
WHAT DIFFERENTIATES EDUCATIONAL LITERATURE? A MULTIMODAL FUSION APPROACH OF TRANSFORMERS AND COMPUTATIONAL LINGUISTICS
  </a>
  <br />
Jordan J. Bird
  <br />
December 2024
  <br />
arXiv preprint 2411.17593, version 3
  <br />
</p>
</blockquote>

We are grateful to these authors for making the dataset available. 
# Classifying-Reading-Level-Difficulty_BoW
