# 🌐 Hybrid Hadoop-Based Sentiment Analysis with Deep Learning and Fuzzy Logic

This project presents an end-to-end sentiment analysis system for large-scale Twitter data by combining **Big Data frameworks (Hadoop)** with **Deep Learning (CNN)** and **Fuzzy C4.5 Decision Trees** for intelligent classification. It addresses the need for accurate sentiment analysis at scale—especially useful in social media monitoring, public opinion mining, and crisis response systems.

---

## 🚀 What This Project Does

We perform sentiment analysis on COVID-19-related tweets using a **hybrid architecture**:

1. **Hadoop HDFS** for storing and distributing tweet data.
2. **CNN (Convolutional Neural Networks)** for deep feature extraction from tweets.
3. **Fuzzification** to handle ambiguity in language using Gaussian Membership Functions.
4. **Fuzzy C4.5 Decision Tree** for intelligent sentiment classification into **Positive**, **Negative**, or **Neutral**.

---

## 💡 Step-by-Step Explanation

### 🔹 1. Data Collection & Storage
- Collected thousands of tweets using the Twitter API or a pre-collected dataset (e.g., COVID-19 tweets).
- Stored the data in **HDFS (Hadoop Distributed File System)** to ensure fault tolerance and scalability.

### 🔹 2. Data Preprocessing
We performed the following preprocessing steps:
- Removal of noise: emojis, URLs, hashtags, mentions, punctuations.
- Lowercasing and normalization.
- Tokenization and lemmatization.
- Stopword removal (e.g., "is", "the", "a").

**Tools used**: `nltk`, `re`, `pandas`.

### 🔹 3. CNN-Based Feature Extraction
- Transformed tweets into numerical vectors using word embeddings (Word2Vec/Glove).
- Passed vectors through a **CNN** model with:
  - Convolutional layers for spatial feature extraction.
  - ReLU activation and max-pooling.
  - Fully connected layers to produce high-level features.

These extracted features represent sentiment-relevant patterns from the text.

### 🔹 4. Fuzzification using Gaussian Membership Functions
- Converted crisp CNN output values into **fuzzy values** using **Gaussian Membership Functions**.
- Each CNN feature was mapped to fuzzy linguistic terms like **Low**, **Medium**, **High** with associated degrees.
- This step helps **reduce uncertainty and ambiguity** in human language.

### 🔹 5. Classification using Fuzzy C4.5 Decision Tree
- Used **entropy and information gain** to build a decision tree from fuzzified features.
- Each rule in the tree represents a fuzzy decision boundary like:
