# 🎵 Decoding Music: Genre Classification from Lyrics

This project explores the relationship between song lyrics and musical genres using **Natural Language Processing (NLP)** and **Machine Learning** techniques.  
I focus on building and evaluating models that can classify a song's genre based solely on its lyrics.

---

## 📂 Repository Contents

- **`Genre_classification.ipynb`** — Main Jupyter Notebook containing data preprocessing, feature extraction, model training, and evaluation.
- **`DF_3Genres_Lyrics_En.csv`** — Dataset of songs with lyrics and genre labels.

---

## 📊 Dataset
- **Size:** ~ 89,000 rows,  columns
- **Genres:** 3 genres
- **Main columns:**
  - `lyrics` — Song lyrics text
  - `genre` — Target label for classification

---

## 🧠 Approach

1. **Data Preprocessing**
   - Removed missing/duplicate lyrics
   - Lowercased text
   - No stemming or lemmatization (to preserve stylistic choices in lyrics)

2. **Feature Extraction (Vectorizers Tried)**
   - Count Vectorizer (word n-grams)
   - TF-IDF (word n-grams)
   - TF-IDF (character n-grams)
   - Sentence-BERT embeddings (optional)

3. **Classifiers Tested**
   - Logistic Regression
   - Linear SVM
   - Ridge Classifier
   - Naive Bayes
   - Passive Aggressive Classifier
   - SGD Classifier

4. **Evaluation Metrics**
   - **Macro F1-Score** (primary)
   - Accuracy (secondary)

---

## 🏆 Best Model

- **Vectorizer:** `TfidfVectorizer(analyzer="char", ngram_range=(3,5), min_df=2)`
- **Classifier:** Logistic Regression (L2 Regularization, C=2.0)
- **Performance:**
  - Macro F1 ≈ **0.736**
  - Accuracy ≈ **0.756**
- **Why it works well:**  
  Character n-grams capture stylistic patterns, rhymes, and subword structures common in lyrics, and handle spelling variations effectively.

---

## 📈 Results Summary

| Step | Description |
|------|-------------|
| 1 | Tested multiple vectorizer–classifier combinations via cross-validation |
| 2 | Identified TF-IDF (char 3–5) + Logistic Regression as best performer |
| 3 | Fine-tuned parameters for optimal regularization |

---

## ⚠️ Limitations

- Uses **lyrics only** — ignores audio features and metadata
- Character n-grams may not capture deep semantic meaning
- Performance may drop on rare or unseen genres

---

## 🚀 Next Steps

- Integrate **word embeddings** (SBERT, FastText) for richer semantic features
- Explore **ensemble** approaches combining multiple feature sets
- Add **audio & metadata features** for multimodal classification
- Train on **larger, more diverse datasets** for better generalization

---

## 📜 License

This project is for educational purposes (Data 607 course).  
Dataset usage subject to original source terms.



