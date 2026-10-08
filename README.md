#  Product Reviews Sentiment Analysis

## 1.  Project Introduction

This project focuses on analyzing customer product reviews and identifying their sentiment as **Positive, Neutral, or Negative**. The project combines **Natural Language Processing, Sentence Transformers, and Machine Learning** to automatically understand customer feedback.

---

## 2.  Data Overview

The dataset contains customer product reviews along with their sentiment labels.

**Main columns:**

* **Product ID** – Identifies the product.
* **Product Review** – Contains the customer's written review.
* **Sentiment** – Represents the sentiment of the review.

The dataset initially contains **1007 records and 3 columns**.

---

## 3.  Data Cleaning

The dataset was checked for missing values and duplicate records.

* Missing values were checked.
* No missing values were found.
* **2 duplicate records** were identified.
* Duplicate records were removed.
* The final dataset contains **1005 records**.

This step ensures that clean and consistent data is used for further analysis.

---

## 4.  Exploratory Data Analysis (EDA)

EDA was performed to understand the distribution of sentiment classes in the dataset.

A sentiment distribution chart was created to identify the number of Positive, Neutral, and Negative reviews.

**Key observation:**
The dataset contains a large number of **Positive reviews**, while Neutral and Negative reviews are comparatively fewer.

---

## 5. Sentence Transformer

The project uses the pre-trained:

`all-MiniLM-L6-v2`

Sentence Transformer model.

It converts customer review text into a numerical representation while preserving the semantic meaning of the sentences.

---

## 6.  Sentence Embeddings

Each customer review is converted into a **384-dimensional numerical embedding**.

For example:

```text
Customer Review
       ↓
Sentence Transformer
       ↓
384 Numerical Values
       ↓
Machine Learning Model
```

These embeddings are used as the input features for the machine learning models.

---

## 7.  Train-Test Split

The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

`random_state=42` is used to make the result reproducible, and `stratify=y` helps maintain the sentiment distribution in both training and testing data.

---

## 8.  Random Forest Classifier

Random Forest is used as one of the classification models.

It combines multiple decision trees and uses their combined predictions to classify the sentiment.

The model learns from the sentence embeddings and predicts:

**Positive / Neutral / Negative**

Random Forest achieved approximately **86.5% test accuracy** and **81.8% weighted F1 score**.

---

## 9.   Gradient Boosting Classifier

Gradient Boosting is the second machine learning model used in the project.

It builds decision trees sequentially, where each new tree attempts to improve the errors made by previous trees.

The model achieved approximately **84.1% test accuracy** and **80.3% weighted F1 score**.

---

## 10.  Model Evaluation

Both models are evaluated using:

* **Accuracy**
* **Weighted F1 Score**
* **Confusion Matrix**

### Model Comparison

| Model                           | Test Accuracy | Test F1 Score |
| ------------------------------- | ------------: | ------------: |
| Random Forest + Transformer     |     **86.5%** |     **81.8%** |
| Gradient Boosting + Transformer |     **84.1%** |     **80.3%** |

The evaluation focuses mainly on test performance because it shows how well the models perform on unseen reviews.

---

## 11.  Confusion Matrix

A confusion matrix is used to compare the **actual sentiment** with the **predicted sentiment**.

It shows:

* Correct Positive predictions
* Correct Neutral predictions
* Correct Negative predictions
* Incorrect classifications between sentiment classes

The diagonal values represent correctly classified reviews.

---

## 12.  Final Model Selection

After comparing both models, **Random Forest Classifier** was selected as the final model because it achieved better test accuracy and F1 score than Gradient Boosting.

### Selected Model:

**Sentence Transformer + Random Forest Classifier**

```text
Product Review
      ↓
Sentence Transformer
      ↓
384-Dimensional Embedding
      ↓
Random Forest Classifier
      ↓
Sentiment Prediction
```

---

## 13. 💭 Sentiment Prediction

The final model can classify a customer review into one of three categories:

```text
😊 Positive
😐 Neutral
😞 Negative
```

This allows customer feedback to be automatically categorized instead of manually analyzing every review.

---

## 14.  Business Insights

The sentiment results can help businesses:

* Understand customer satisfaction.
* Identify positive customer experiences.
* Detect negative feedback.
* Understand areas that may require improvement.
* Support product and customer-service decisions.
* Convert large amounts of customer feedback into useful information.

---

## 15.  Future Improvements

The project can be further improved by experimenting with:

* XGBoost
* SVM
* Neural Networks
* Fine-tuned Transformer models
* Larger and more balanced datasets
* Continuous analysis of newly received customer reviews

---

## 16. 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Sentence Transformers
* Google Colab

---

## 17.  Complete Workflow

```text
Product Reviews
       ↓
Data Cleaning
       ↓
Exploratory Data Analysis
       ↓
Sentence Transformer
       ↓
384-Dimensional Embeddings
       ↓
Random Forest vs Gradient Boosting
       ↓
Model Evaluation
       ↓
Random Forest Selected
       ↓
Sentiment Prediction
       ↓
Positive / Neutral / Negative
       ↓
Business Insights
```

---

##  Project Takeaway

The project demonstrates how **customer review text can be transformed into meaningful numerical representations using a Sentence Transformer and then classified using machine learning models**.

The final **Random Forest + Transformer** approach provided the better performance among the tested models.

> **“From customer reviews to actionable insights — turning words into meaningful business intelligence.”**
