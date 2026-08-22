# 📰 Fake News Prediction using Machine Learning

A machine learning system that classifies news articles as **Real** or **Fake** using Natural Language Processing (NLP) and Logistic Regression. Built with TF-IDF vectorization and trained on a labeled news dataset, the model achieves **95.3% accuracy** on unseen test data.

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange.svg)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 📌 Overview

The spread of misinformation through online news platforms has made automated fake news detection an important application of machine learning. This project builds a text classification pipeline that cleans and prepares raw news text, converts it into numerical features, trains a classifier to tell fake news apart from real news, and evaluates how well that classifier performs.

---

## 📊 Results

| Metric | Score |
|---|---|
| Training Accuracy | **97.85%** |
| Test Accuracy | **95.26%** |

---

## 🧠 Project Workflow

### 1. Importing Dependencies
The project relies on a handful of core libraries: NumPy and Pandas for data handling, NLTK for text processing, and scikit-learn for feature extraction, model training, and evaluation.

### 2. Loading the Dataset
The news dataset is loaded and inspected — checking its shape, viewing the first few rows, and identifying which columns contain missing values.

### 3. Handling Missing Values
Missing entries in the `title`, `author`, and `text` columns are filled with empty strings so no data is lost during processing. The `author`, `title`, and `text` fields are then merged into a single combined `content` field, giving the model richer context for each article.

### 4. Text Cleaning — Stemming
Each article's combined content is cleaned and standardized in a few steps: non-alphabetic characters are stripped out, all text is lowercased, common stopwords (like "the," "is," "and") are removed, and every remaining word is reduced to its root form using the Porter Stemmer. For example, "playing," "played," and "plays" all reduce down to "play." This keeps the vocabulary compact and focused on meaningful words.

### 5. Separating Data and Labels
Once cleaned, the article content becomes the input data, and the fake/real labels become the target the model will learn to predict.

### 6. Converting Text into Numbers — TF-IDF
Since machine learning models can't work with raw text, the cleaned content is transformed into numerical vectors using TF-IDF (Term Frequency–Inverse Document Frequency). This technique scores each word by how important and distinctive it is across the entire dataset, rather than just how often it appears.

### 7. Splitting Into Training and Test Sets
The numerical data is split into an 80% training set and a 20% test set, keeping the same proportion of fake and real articles in both sets, so that the model is evaluated fairly on data it hasn't seen before.

### 8. Training the Model
A Logistic Regression classifier is trained on the training data, learning the relationship between word patterns and whether an article is fake or real.

### 9. Evaluating the Model
The trained model's predictions are compared against the true labels on both the training set and the test set, producing accuracy scores that show how well it generalizes to new articles.

### 10. Making a Prediction
Finally, the model is used to classify a single unseen article from the test set, demonstrating the end-to-end system in action — from raw text to a Fake/Real verdict.

---

## 🗂️ Dataset

The project uses a labeled news dataset (`train.csv`) consisting of **20,800 rows** and **6 columns**:

| Column | Description |
|---|---|
| `id` | Unique article identifier |
| `title` | Headline of the article |
| `author` | Author of the article |
| `text` | Full article body |
| `label` | `1` = Fake, `0` = Real |
| `content` | Combined `author` + `title` + `text`, created during preprocessing |

> 📌 **Note:** The dataset (`train.csv`) is not included in this repository due to size/licensing.

### 📥 Where to Get the Dataset

This project is built to work with the **Fake News dataset** hosted on Kaggle:

🔗 **[Kaggle — Fake News Dataset](https://www.kaggle.com/c/fake-news/data)**

To set it up:

1. Visit the Kaggle link above and sign in (a free Kaggle account is required).
2. Download `train.csv` from the **Data** tab of the competition page.
3. Place the downloaded `train.csv` file in the root directory of this project — the same folder as `Fake_News_Prediction.ipynb`.
4. You're all set — the notebook will load the file directly from there.

> ⚠️ If Kaggle's dataset structure changes, you can substitute any dataset with the same five columns (`id`, `title`, `author`, `text`, `label`) — the preprocessing pipeline is built around that schema.

---

## ⚙️ Tech Stack

- **Python 3**
- **NumPy** & **Pandas** — data handling
- **NLTK** — stopword removal & stemming
- **scikit-learn** — TF-IDF vectorization, Logistic Regression, model evaluation

---

## 📥 How to Clone the Project

To get a copy of this project on your local machine:

1. Go to the repository page on GitHub.
2. Click the green **Code** button and copy the repository URL (HTTPS or SSH).
3. Open a terminal on your machine and navigate to the folder where you want the project saved.
4. Run the `git clone` command followed by the copied URL to download the repository.
5. Move into the newly created project folder using `cd` followed by the folder name.

Once cloned, the notebook and all supporting files will be available locally, and you're ready to move on to the setup steps below.

---

## 🚀 Getting Started

1. Clone this repository to your local machine (see above).
2. Install the required libraries: NumPy, Pandas, NLTK, and scikit-learn.
3. Make sure NLTK's stopwords package is downloaded — the notebook handles this automatically on first run.
4. Place your `train.csv` dataset in the project root folder.
5. Open and run `Fake_News_Prediction.ipynb` in Jupyter Notebook, executing the cells from top to bottom.

---

## 📁 Project Structure

- **Fake_News_Prediction.ipynb** — Main notebook covering preprocessing, training, and evaluation
- **train.csv** — Dataset (not included — see Dataset section above)
- **README.md** — Project documentation

---

## 🔧 Future Improvements

- [ ] Experiment with other models (Naive Bayes, SVM, Random Forest, LSTM/BERT)
- [ ] Add cross-validation and hyperparameter tuning
- [ ] Build a simple web interface (Streamlit/Flask) for live predictions
- [ ] Add confusion matrix and precision/recall/F1 metrics
- [ ] Handle class imbalance if present in larger datasets

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](../../issues) if you want to contribute.

---

⭐ If you found this project helpful, consider giving it a star!
