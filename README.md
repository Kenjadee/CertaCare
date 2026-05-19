# CertaCare - Clinical Triage Decision Support System

## What is CertaCare?

Certa care is an ml- based clinical triage decision making system that support  Ngo field workers in making decisions . It also puts in place measures to ensure medical security by adding confidence scores meaning it states clearly how confident it is of the answer it’s giving .

## Problem it Solves

In a classic NGO field work space there is often a large number of patients to attend to with limited number of health care professionals . Certa care helps assist the decision making process on which case should be escalated. Making work flow faster and easier .


## Dataset

The dataset contains emergency department triage records with physiological measurements and patient demographics. Features include vital signs (blood pressure, heart rate, respiratory rate, temperature, oxygen saturation), pain scores, mental status, and arrival conditions. The target variable is the expert-assigned KTAS triage level, which was mapped into three simplified classes: GREEN, YELLOW, and RED.
( https://www.kaggle.com/datasets/ilkeryildiz/emergency-service-triage-application )

## Project Structure

The project is organized into 7 phases:

**Phase 1 - Data Understanding & Exploration**

Explored the dataset structure, feature distributions, and class imbalance between GREEN, YELLOW, and RED triage categories.

**Phase 2 - Data Cleaning**

Handled missing values, corrected data types, and standardized inconsistent formats (e.g., numeric conversions and string formatting).

**Phase 3 - Feature Engineering**

Created model-ready features such as Saturation_missing and simplified clinical labels for better interpretability.

**Phase 4 - Model Training**

Trained multiple machine learning models including Logistic Regression, Decision Tree, and Random Forest.

**Phase 5 - Model Evaluation**

Evaluated models using accuracy, precision, recall, F1-score, confusion matrix, and ROC-AUC.

**Phase 6 - Class Imbalance Handling**

Applied SMOTE and class weighting to improve performance on underrepresented RED class cases.

**Phase 7 - CertaCare Prediction System**

Built an interactive triage prediction system with real-time patient input, probability outputs, and confidence scoring.


## Model Performance

Final model comparison:

 **Logistic Regression (Balanced)**

  * Accuracy: 0.56
  * RED recall: moderate
  * Best interpretability

  **Random Forest (Balanced)**

  * Accuracy: 0.58
  * Better overall balance across classes
  * Improved robustness on nonlinear patterns

 **Best ROC-AUC:** 0.740 (macro average)



## Key Engineering Decisions

* **SMOTE Oversampling**
  Used to handle severe class imbalance and improve RED class learning.

* **Class Weights (Balanced Models)**
  Helped models pay more attention to minority classes without losing overall stability.

* **Probability Threshold Adjustment**
  Introduced RED probability thresholding to improve safety in borderline cases.

* **Feature Engineering (Saturation_missing)**
  Added missing-data indicator to preserve information about incomplete oxygen readings.

* **Data Leakage Prevention**
  Ensured train-test split was performed before scaling and resampling steps.


## How to Run

1. Open the project in Google Colab or Jupyter Notebook
2. Run all cells from top to bottom
3. Ensure required libraries are installed:

   ```
   pip install pandas numpy scikit-learn imbalanced-learn matplotlib ipywidgets
   ```
4. Interact with the widget-based patient triage system
5. Enter patient vitals and click **Assess Patient**


## Limitations

* Dataset size is relatively small, which may affect generalization
* RED class performance is still limited (recall ~0.61 in best model)
* Model is not clinically validated and should not be used for real medical decisions
* Some features may reflect dataset bias rather than real-world medical causality
* Performance may degrade in different hospital or population settings


## Author
Obi Ebubechukwu
