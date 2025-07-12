# Spam-Classification

# 📧 Spam Classification

A machine learning project to classify emails as **spam** or **not spam** using NLP techniques and SVMs.

## 🚀 Project Overview

- **Dataset**: `emails.csv`
  - `Text`: email body + subject lines.
  - `Spam_or_not`: Binary label – `1` = spam, `0` = not spam. :contentReference[oaicite:1]{index=1}
- **Notebook**: `Spam classification.ipynb` contains the entire pipeline, from exploration to model evaluation.

## 🧠 Machine Learning Pipeline

1. **Data Exploration & Cleaning**
   - Inspect class balance.
   - Clean text (lowercase, remove punctuation, stopwords).

2. **Feature Extraction**
   - TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. It’s commonly used in text mining and information retrieval, such as in spam classification tasks, to convert text into numerical features for machine learning algorithms.
   - a) Term Frequency (TF):
Definition: It measures how frequently a term appears in a document. The more frequently a term appears, the higher its TF value.

     ***TF(t,d)= Total number of terms in document d/Number of times term t appears in document d***
   - b)Inverse Document Frequency (IDF):
Definition: It measures how important a term is across all documents in the corpus. If a term appears in many documents, its IDF value decreases, as it is less informative.

     ***IDF(t,D)=log( Number of documents containing term t / Total number of documents)***
   -  High IDF values indicate that the word is rare and potentially more important to the specific document. Words that appear in almost all documents, like "the" or "and", will have a low IDF.
     
      ***TF-IDF Calculation:***
   -  TF-IDF is the product of the term frequency and the inverse document frequency

      ***TFIDF(t,d,D)=TF(t,d)×IDF(t,D)***
   - This product highlights terms that are frequent in a specific document but infrequent across the entire corpus, making them more significant. 
 

3. **Modeling**
   - Train a Support Vector Classifier (SVC).
   - Tune the regularization parameter `C` to balance margin and misclassification risk. :contentReference[oaicite:3]{index=3}

4. **Evaluation**
   - Assess model performance using accuracy, precision, recall, F1-score.
   - Analyze confusion matrix.

## 📊 Results

- **Best model**: SVC with tuned `C` (e.g., `C=0.1`), reduces overfitting while maintaining high performance.
- **Performance metrics**:
  - Accuracy: _update with final %.*
  - Precision / Recall / F1-score: _update with values._

## 🛠️ Dependencies

```bash
pip install -r requirements.txt
```









#### Reducing overfitting: C Parameter (Regularization Parameter):
Trade-off Between Misclassification and Margin: The C parameter controls the trade-off between achieving a wide margin and correctly classifying training points.
A high C value makes the model focus more on correctly classifying every point in the training set, potentially leading to overfitting.
A low C value allows for more misclassifications in the training set but helps the model generalize better to new data, reducing overfitting.
For instance, in your project, using C=0.1 introduces stronger regularization, helping the model generalize better by allowing some misclassification in favor of a larger margin.
