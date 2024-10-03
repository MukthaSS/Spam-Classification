# Spam-Classification

### About the dataset

Text (Text): This column contains the text content of the email messages. It includes the body of the emails along with any associated subject lines or headers.

Spam_or_not (Binary):This column contains binary labels to indicate whether an email is spam or not. "1" represents spam, while "0" represents not spam.

### About the model

SVC (Support Vector Classification) is a specific implementation of the Support Vector Machine (SVM) algorithm used for classification tasks. It works by finding a decision boundary (hyperplane) that best separates different classes in the data.

#### Feature extraction:
TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. It’s commonly used in text mining and information retrieval, such as in spam classification tasks, to convert text into numerical features for machine learning algorithms.
a) Term Frequency (TF):
Definition: It measures how frequently a term appears in a document. The more frequently a term appears, the higher its TF value.
##### TF(t,d)= Total number of terms in document d/Number of times term t appears in document d
b)Inverse Document Frequency (IDF):
Definition: It measures how important a term is across all documents in the corpus. If a term appears in many documents, its IDF value decreases, as it is less informative.
##### IDF(t,D)=log( Number of documents containing term t / Total number of documents)
* High IDF values indicate that the word is rare and potentially more important to the specific document. Words that appear in almost all documents, like "the" or "and", will have a low IDF.

##### TF-IDF Calculation:
TF-IDF is the product of the term frequency and the inverse document frequency

​###### TFIDF(t,d,D)=TF(t,d)×IDF(t,D)
* This product highlights terms that are frequent in a specific document but infrequent across the entire corpus, making them more significant. 


#### Reducing overfitting: C Parameter (Regularization Parameter):
Trade-off Between Misclassification and Margin: The C parameter controls the trade-off between achieving a wide margin and correctly classifying training points.
A high C value makes the model focus more on correctly classifying every point in the training set, potentially leading to overfitting.
A low C value allows for more misclassifications in the training set but helps the model generalize better to new data, reducing overfitting.
For instance, in your project, using C=0.1 introduces stronger regularization, helping the model generalize better by allowing some misclassification in favor of a larger margin.
