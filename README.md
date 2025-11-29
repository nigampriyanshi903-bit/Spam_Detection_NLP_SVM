#  Spam Detection / Email Filtering using SVM and NLP

This project focuses on building a highly accurate and reliable model to classify text messages as 'ham' (legitimate) or 'spam' using Natural Language Processing (NLP) techniques and advanced classification algorithms.

##  Project Goals
1.  Apply robust NLP techniques (Cleaning, Stemming, Stopword Removal) to the raw text data.
2.  Convert text into a numerical format using **TF-IDF Vectorization**.
3.  Compare **Multinomial Naive Bayes (MNB)** and **Support Vector Machine (SVM)** to select the model with the best performance on the critical **Spam (Class 1)** class.
4.  Prioritize high **Precision** (to minimize legitimate emails going to spam) and high **Recall** (to minimize spam leaking into the inbox).

##  Methodology and Data Pipeline

### 1. Data Preprocessing & Vectorization
* **Preprocessing:** Messages were cleaned, lowercased, and stemmed, and common English stopwords were removed.
* **Vectorization:** **TF-IDF Vectorizer** was fitted on the training data to create a matrix of 3000 features, representing the weighted importance of each word.
* **Imbalance:** The dataset was highly imbalanced (Ham: 4825 vs. Spam: 747), necessitating the focus on Precision and Recall over simple Accuracy.

### 2. Final Model Comparison

Two classification models were evaluated using the vectorized test set:

| Metric | MNB Score | **SVM Score** | Conclusion |
| :--- | :--- | :--- | :--- |
| **Overall Accuracy** | $0.9740$ | **$0.9857$** | SVM showed a higher overall correct rate. |
| **Precision (Spam)** | $0.99$ | $0.99$ | Both models are excellent at avoiding False Positives (legitimate emails mislabeled as spam). |
| **Recall (Spam)** | $0.81$ | **$0.90$** | **SVM is superior,** correctly identifying $90\%$ of all actual spam messages. |
| **False Negatives (Spam Leaks)** | 28 | **15** | SVM reduced the number of missed spam messages significantly. |

##  Conclusion: The Superior SVM Model

The **Support Vector Machine (SVM)** model, using a linear kernel, was selected as the **Best Model** for this Spam Detection task.

It successfully utilized the high-dimensional TF-IDF features to achieve a high **Accuracy of $98.57\%$** while demonstrating a crucial balance of metrics:

* **Reliability:** Maintaining near-perfect **Precision ($0.99$)**, meaning users rarely see important emails in the spam folder.
* **Effectiveness:** Improving **Recall to $0.90$**, meaning the filter is highly effective at catching spam and keeping the inbox clean.
