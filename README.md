# SMS Spam Classification Project  

## Overview  
This project applies supervised machine learning methods to classify SMS text messages as **spam** or **ham** (legitimate). Using the [SMS Spam Collection Dataset](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection), the goal is to evaluate preprocessing strategies, feature engineering, and multiple classification models to improve spam detection accuracy while handling class imbalance.  

## Research Question  
Can a supervised machine learning approach using the SMS Spam Collection dataset effectively detect spam messages and reduce misclassification compared to simpler filtering methods?  

## Dataset  
- **Source**: Tiago A. Almeida and José María Gómez Hidalgo (2011–2013)  
- **Size**: 5,572 SMS messages (4,825 ham, 747 spam)  
- **Format**: Plain text file with two columns:  
  - `label` → ham or spam  
  - `message` → SMS text  
- **License**: Free for research and educational use only (not for commercial purposes).  

## Methods  
The workflow consists of three main phases:  

### Preprocessing  
- Load and clean the dataset (remove duplicates, ensure consistent labels).  
- Handle class imbalance (~87% ham vs ~13% spam).  
- Tokenize and normalize text: lowercasing, stopword removal, lemmatization.  
- Feature engineering: message length, word count, punctuation ratio, keyword flags (e.g., “free,” “win,” “call now”).  

### Feature Representation  
- Bag-of-Words (BOW)  
- Term Frequency–Inverse Document Frequency (TF–IDF)  
- Binary features such as `contains_link`, `contains_number`, `uppercase_ratio`  

### Modeling  
- **Baseline Models**: Logistic Regression, Multinomial Naïve Bayes  
- **Advanced Models**: Decision Tree, Random Forest  
- Train-test split: 80/20 (stratified to preserve class balance).  

### Evaluation  
- Accuracy (baseline comparison)  
- Precision & Recall (with emphasis on recall for spam detection)  
- F1-score (balance between precision and recall)  
- Confusion matrix to visualize errors  
- ROC-AUC for overall model comparison  

## Dataset  

The SMS Spam Collection dataset contains 5,572 English SMS messages labeled as either:  
- **ham** – legitimate message  
- **spam** – unwanted message  

## Results (Planned)

Target performance: at least 75% accuracy

Expectation: Naïve Bayes and Logistic Regression will serve as strong baselines.

Anticipated improvements from Random Forest and optimized TF–IDF features.

Ethical Considerations

Dataset contains only SMS message text with no personal identifiers.

Messages were collected for academic research and may not represent SMS usage globally.

Dataset use is restricted to educational and non-commercial purposes.

## Executive Summary

This project applies machine learning techniques to classify SMS messages as either “ham” (legitimate) or “spam” (unwanted). Using the SMS Spam Collection dataset (Almeida & Gómez Hidalgo, 2011), we conducted exploratory data analysis, built multiple classification models, and evaluated their performance. Random Forest, both with and without SMOTE oversampling, achieved the highest performance, with F1 scores and accuracy exceeding 98%. This repository is organized so that any user can reproduce the workflow and replicate the results.

## Software and Platform

This project was developed and tested in Python 3.10 using Google Colab (Linux-based environment). The main libraries used are:

- pandas (data handling)

- numpy (numerical computing)

- matplotlib and seaborn (visualization)

- scikit-learn (modeling, evaluation, and hyperparameter tuning)

- imblearn (SMOTE oversampling for class imbalance)

## Repository Map

The repository is organized into the following components:

- README.md: Orientation and documentation for the project

- LICENSE.md: License file (MIT)

- DATA folder: Contains the dataset file SMSSpamCollection.csv

- SCRIPTS folder: Includes Jupyter notebooks for exploratory data analysis (EDA), model training, and hyperparameter tuning

- OUTPUT folder: Stores project outputs, including saved figures, charts, and tables of results

## Instructions for Reproducing Results

To reproduce the results of this project:

1. Clone or Download the Repository into your local environment or open it in Google Colab

2. Load the Dataset from the DATA folder (SMSSpamCollection.csv)

3. Run the EDA Notebook (eda.ipynb) to explore the dataset through class distribution plots, message length histograms, and other visualizations

4. Train Models using the models.ipynb notebook, which implements Logistic Regression, Linear SVM, and Random Forest on both the original dataset and the SMOTE-balanced dataset

5. Perform Hyperparameter Tuning with the tuning.ipynb notebook to optimize performance for each model

6. Review Results in the OUTPUT folder, which contains comparative metrics such as accuracy, precision, recall, and F1-scores, as well as visualizations to support the findings

## Reproducibility Statement

This repository is structured to ensure reproducibility and clarity. An unfamiliar user should be able to follow the provided instructions, replicate the analysis pipeline, and confirm the results.

## References

T. A. Almeida, J. M. Gómez Hidalgo, and A. Yamakami, “Contributions to the Study of SMS Spam Filtering: New Collection and Results,” Proc. ACM Symp. Document Eng. (DocEng ’11), 2011.

J. M. Gómez Hidalgo, T. A. Almeida, and A. Yamakami, “On the Validity of a New SMS Spam Collection,” Proc. IEEE ICMLA ’12, 2012.

T. A. Almeida, J. M. Gómez Hidalgo, and T. P. Silva, “Towards SMS Spam Filtering: Results under a New Dataset,” Int. J. Inf. Secur. Sci., vol. 2, no. 1, pp. 1–18, 2013.

*Chat GPT was used to aid in the development of the project goal document
