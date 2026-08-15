<h1 align="center">🩺 Diabetes Prediction</h1>

<p align="center">
  <strong>Machine Learning Based Diabetes Prediction System</strong><br/>
  Data Analysis · Feature Standardization · SVM Classification · Diabetes Prediction
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.13+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-learn"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/768_Dataset_Records-blueviolet?style=flat-square" alt="dataset"/>
  <img src="https://img.shields.io/badge/8_Input_Features-blue?style=flat-square" alt="features"/>
  <img src="https://img.shields.io/badge/SVM_Classification-orange?style=flat-square" alt="model"/>
  <img src="https://img.shields.io/badge/77.27%25_Test_Accuracy-brightgreen?style=flat-square" alt="accuracy"/>
  <img src="https://img.shields.io/badge/Binary_Classification-red?style=flat-square" alt="classification"/>
</p>

---

> **Diabetes Prediction** is a supervised machine learning classification project that predicts whether a person is diabetic or non-diabetic using health-related measurements.
>
> The project follows a complete machine learning workflow — from dataset analysis and preprocessing to model training, evaluation, and prediction using a Support Vector Machine classifier.

---

## Table of Contents

- [What is Diabetes Prediction](#-what-is-diabetes-prediction)
- [Objective](#-objective)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Dataset](#-dataset)
- [Features Explained](#-features-explained)
- [Machine Learning Workflow](#-machine-learning-workflow)
- [Data Analysis](#-data-analysis)
- [Feature and Target Separation](#-feature-and-target-separation)
- [Data Standardization](#-data-standardization)
- [Train-Test Split](#-train-test-split)
- [Why SVM](#-why-svm)
- [Why Linear Kernel](#-why-linear-kernel)
- [Model Training](#-model-training)
- [Model Evaluation](#-model-evaluation)
- [Prediction](#-prediction)
- [Results](#-results)
- [Important Concepts](#-important-concepts)
- [Limitations](#-limitations)
- [Future Improvements](#-future-improvements)
- [Setup and Execution](#-setup-and-execution)
- [Learning Outcomes](#-learning-outcomes)

---

# 🩺 What is Diabetes Prediction?

Diabetes Prediction is a **supervised machine learning classification project** that predicts whether an individual is likely to be diabetic or non-diabetic based on health-related measurements.

The project uses the **PIMA Diabetes Dataset**, which contains:

- 768 patient records
- 8 input features
- 1 target variable

The target variable is:

| Value | Meaning |
|---|---|
| `0` | Non-Diabetic |
| `1` | Diabetic |

The complete project demonstrates how a machine learning model can be developed from raw dataset analysis to final prediction.

---

# 🎯 Objective

The primary objective of this project is to build a machine learning model capable of performing **binary classification** for diabetes prediction.

The project focuses on understanding the complete machine learning pipeline:

```text
Dataset
   ↓
Data Analysis
   ↓
Feature & Target Separation
   ↓
Data Standardization
   ↓
Train-Test Split
   ↓
SVM Model
   ↓
Model Training
   ↓
Model Evaluation
   ↓
New Data Prediction
```

The project also focuses on understanding **why each step is required**, rather than treating machine learning as simply training a model and obtaining an accuracy score.

---

# 🛠️ Tech Stack

| Technology | Why this technology is used |
|---|---|
| **Python** | Provides the programming environment for implementing the complete machine learning workflow. |
| **NumPy** | Used for numerical operations and preparing input data for prediction. |
| **Pandas** | Used for loading, inspecting, analysing, and manipulating the dataset. |
| **Scikit-learn** | Provides the preprocessing, dataset splitting, SVM classification, and evaluation functionality. |
| **StandardScaler** | Used to standardize features that have different numerical ranges. |
| **Support Vector Machine** | Used as the binary classification algorithm. |
| **Jupyter Notebook** | Provides an interactive environment for combining analysis, implementation, outputs, and documentation. |
| **Matplotlib** | Available for creating data visualizations during analysis. |
| **Seaborn** | Available for statistical and visual analysis. |

---

# 📁 Project Structure

```text
Diabetes-Prediction/
|
+-- diabetes_prediction.ipynb
|       Complete machine learning workflow,
|       analysis, model training, evaluation
|       and prediction
|
+-- diabetes.csv
|       PIMA Diabetes dataset
|
+-- requirements.txt
|       Python dependencies required
|       to execute the project
|
+-- README.md
        Project documentation
```

### Why this structure?

The project is intentionally kept simple.

The complete implementation is maintained inside the Jupyter Notebook, while the dataset and dependencies are kept separately.

This makes the repository easy to understand:

```text
Notebook     → Implementation
Dataset      → Input Data
Requirements → Dependencies
README       → Documentation
```

---

# 📊 Dataset

The project uses the **PIMA Diabetes Dataset**.

The dataset contains:

```text
Total Records     → 768
Input Features    → 8
Target Variables  → 1
Total Columns     → 9
```

The dataset contains medical and demographic measurements that are used to predict the diabetes outcome.

---

## Outcome Distribution

The target variable contains two classes:

| Outcome | Class | Records |
|---|---|---:|
| `0` | Non-Diabetic | 500 |
| `1` | Diabetic | 268 |

Therefore, the project is a **binary classification problem**.

---

# 📋 Features Explained

The model uses eight input features.

| Feature | Description |
|---|---|
| **Pregnancies** | Number of pregnancies |
| **Glucose** | Plasma glucose concentration |
| **BloodPressure** | Blood pressure measurement |
| **SkinThickness** | Triceps skin fold thickness |
| **Insulin** | Serum insulin measurement |
| **BMI** | Body Mass Index |
| **DiabetesPedigreeFunction** | Diabetes pedigree function |
| **Age** | Age of the individual |

### Target Variable

```text
Outcome
```

```text
0 → Non-Diabetic
1 → Diabetic
```

The target is what the model attempts to predict from the eight input features.

---

# 🔄 Machine Learning Workflow

The complete workflow is:

```text
                  PIMA Diabetes Dataset
                           │
                           ▼
                    Data Loading
                           │
                           ▼
                    Data Analysis
                           │
                           ▼
             Feature / Target Separation
                           │
                           ▼
                 Feature Standardization
                           │
                           ▼
                   Train-Test Split
                           │
                  ┌────────┴────────┐
                  │                 │
                  ▼                 ▼
             Training Data      Testing Data
                  │                 │
                  ▼                 │
              SVM Training          │
                  │                 │
                  └────────┬────────┘
                           ▼
                    Model Prediction
                           │
                           ▼
                    Model Evaluation
                           │
                           ▼
                   New Data Prediction
```

Each stage has a specific purpose and contributes to the final prediction.

---

# 🔍 Data Analysis

Before training the model, the dataset is analysed to understand its structure and contents.

The analysis includes:

- Viewing the first records
- Checking dataset dimensions
- Examining statistical information
- Understanding the feature values
- Analysing the target distribution

### Why is data analysis important?

A machine learning model should not be trained blindly.

Before selecting an algorithm, we need to understand:

```text
What data do we have?
        ↓
How many records?
        ↓
What features?
        ↓
What is the target?
        ↓
How are the values distributed?
```

This initial understanding helps identify potential preprocessing requirements and provides context for later modelling decisions.

---

# 🎯 Feature and Target Separation

The dataset contains both input variables and the expected output.

These are separated into:

```text
X → Input Features
Y → Target Variable
```

### Input

The eight health-related measurements are provided to the model.

### Output

The `Outcome` column represents whether the person is classified as diabetic or non-diabetic.

Conceptually:

```text
8 Health Features
       ↓
   ML Model
       ↓
Outcome
  0 or 1
```

### Why is this separation necessary?

A supervised learning algorithm learns a relationship between:

```text
Input → Output
```

The target should therefore be separated from the features before model training.

---

# 📏 Data Standardization

The project uses **StandardScaler** to standardize the input features.

The reason is that the eight features do not all have the same numerical range.

For example:

```text
Age
Glucose
Insulin
BMI
```

can have very different scales.

---

## Why Standardization?

SVM is sensitive to the scale of input features.

If one feature has much larger numerical values than another, it can influence the model disproportionately.

Standardization places the features on a comparable scale.

Conceptually:

```text
Before Standardization

Glucose     ████████████████████
Insulin     █████████████████████████████
BMI         ███████
Age         ████


After Standardization

Glucose     ████████
Insulin     ███████
BMI         ████████
Age         ███████
```

The objective is not to remove information, but to make the numerical scales more comparable.

---

# ✂️ Train-Test Split

The dataset is divided into training and testing data.

The project uses:

```text
80% → Training Data
20% → Testing Data
```

This results in:

```text
Training Samples → 614
Testing Samples  → 154
```

---

## Why Train-Test Split?

The model should not be evaluated only on the same data it learned from.

Instead:

```text
Training Data
     ↓
Model learns patterns
     ↓
Testing Data
     ↓
Model is evaluated on unseen data
```

This gives a better indication of how the model may perform on new observations.

---

## Why `stratify`?

The dataset contains two target classes with different frequencies.

Stratification helps maintain a similar class distribution in both training and testing datasets.

This makes the split more representative of the original dataset.

---

## Why `random_state`?

A fixed random state makes the dataset split reproducible.

This means the same experiment can be repeated with the same division of training and testing samples.

---

# 🤖 Why SVM?

The project uses a **Support Vector Machine (SVM)** classifier.

SVM is a supervised learning algorithm commonly used for classification.

The problem in this project is:

```text
Input:
8 Health Measurements

        ↓

Output:
0 or 1
```

Therefore, this is a **binary classification problem**.

SVM is suitable because it attempts to find a decision boundary that separates the two classes while maintaining an effective margin between them.

---

# 📐 Why Linear Kernel?

The SVM implementation uses a **linear kernel**.

A linear kernel attempts to separate the classes using a linear decision boundary.

Conceptually:

```text
Non-Diabetic          Diabetic

 ●  ●  ●
   ● ●          │          ▲ ▲ ▲
 ●   ●          │        ▲   ▲
   ●            │          ▲
                │
          Decision Boundary
```

### Why use a linear kernel?

A linear kernel provides:

- A relatively simple model
- A straightforward decision boundary
- Lower complexity than non-linear kernels
- A good starting point for a binary classification problem

---

# 🧠 SVM Concepts

## Decision Boundary

The **decision boundary** separates observations belonging to different classes.

```text
Class 0  |  Decision Boundary  |  Class 1
```

The model uses this learned boundary when classifying new observations.

---

## Support Vectors

Support vectors are the observations closest to the decision boundary.

They are particularly important because they influence the position of the SVM decision boundary.

---

## Margin

The margin represents the separation between the decision boundary and the closest support vectors.

SVM attempts to find an effective margin while separating the classes.

---

# 🏋️ Model Training

After preprocessing and splitting the dataset, the SVM classifier is trained using the training data.

The process is conceptually:

```text
Training Features
       +
Training Labels
       │
       ▼
   SVM Classifier
       │
       ▼
Learns Class Patterns
       │
       ▼
Classification Boundary
```

The trained model can then be used to classify both test observations and new patient data.

---

# 📈 Model Evaluation

The current project evaluates the model using **accuracy**.

Accuracy measures the proportion of correctly classified observations.

Conceptually:

```text
Accuracy =
Correct Predictions
-------------------
Total Predictions
```

Two accuracy measurements are considered:

```text
Training Accuracy
        ↓
How well the model performs on training data

Testing Accuracy
        ↓
How well the model performs on unseen test data
```

---

# 🏆 Results

The model achieved the following results:

| Evaluation | Accuracy |
|---|---:|
| **Training Accuracy** | **78.66%** |
| **Testing Accuracy** | **77.27%** |

The testing accuracy is particularly important because the testing samples were not used to train the model.

The relatively close training and testing scores indicate that there is not a large difference between the model's performance on the training and testing sets.

> **Note:** The current notebook evaluates the model primarily using accuracy. Additional evaluation metrics would provide a more complete performance analysis.

---

# 🔮 Prediction

After training the model, it can be used to make predictions for new observations.

The prediction workflow is:

```text
New Patient Information
          │
          ▼
8 Input Features
          │
          ▼
Data Preparation
          │
          ▼
Standardization
          │
          ▼
Trained SVM Model
          │
          ▼
Prediction
      ┌───┴───┐
      ▼       ▼
     0         1
      │       │
      ▼       ▼
Non-Diabetic Diabetic
```

The notebook includes a sample patient input and demonstrates a prediction corresponding to:

```text
1 → The person is diabetic
```

---

# 📊 Model Summary

```text
Project              → Diabetes Prediction
Problem Type         → Supervised Binary Classification
Dataset              → PIMA Diabetes Dataset
Records              → 768
Input Features       → 8
Target                → Outcome
Preprocessing         → Standardization
Train-Test Split      → 80/20
Classification Model  → Support Vector Machine
Kernel                → Linear
Training Accuracy     → 78.66%
Testing Accuracy      → 77.27%
```

---

# 🧩 Important Machine Learning Concepts

This project demonstrates:

| Concept | Covered |
|---|---|
| Supervised Learning | ✅ |
| Binary Classification | ✅ |
| Feature Selection | ✅ |
| Target Variable | ✅ |
| Data Analysis | ✅ |
| Data Standardization | ✅ |
| Train-Test Split | ✅ |
| Support Vector Machine | ✅ |
| Linear Kernel | ✅ |
| Decision Boundary | ✅ |
| Support Vectors | ✅ |
| Margin | ✅ |
| Model Training | ✅ |
| Model Prediction | ✅ |
| Accuracy Evaluation | ✅ |

---

# ⚠️ Limitations

The current implementation has several areas that can be improved.

| Limitation | Impact | Possible Improvement |
|---|---|---|
| **Accuracy is the primary metric** | Does not show all types of classification errors | Add Precision, Recall and F1-score |
| **No confusion matrix** | False positives and false negatives are not clearly visualized | Add a confusion matrix |
| **No cross-validation** | Results depend on one train-test split | Use Stratified K-Fold Cross Validation |
| **No hyperparameter tuning** | The selected SVM configuration may not be optimal | Use GridSearchCV |
| **No model comparison** | SVM is evaluated without comparison against other classifiers | Compare multiple ML algorithms |
| **Limited preprocessing** | Dataset-specific data quality issues are not extensively handled | Perform deeper preprocessing |
| **Notebook-based interface** | Users must interact with the notebook | Build a web-based prediction interface |

---

# ⚠️ Data Leakage Consideration

One important improvement for the current implementation is the order of feature standardization and dataset splitting.

For a more rigorous machine learning workflow, the scaler should learn its parameters only from the training data.

The preferred flow is:

```text
Original Dataset
       │
       ▼
Train-Test Split
       │
   ┌───┴────┐
   ▼        ▼
Training   Testing
   │        │
   ▼        │
Fit Scaler  │
   │        │
   ▼        ▼
Transform  Transform
Training   Testing
   │        │
   └───┬────┘
       ▼
   SVM Model
```

### Why is this important?

The testing dataset should remain unseen during the model-building process.

Using preprocessing parameters learned from the entire dataset can allow information from the test set to influence preprocessing.

Separating this process makes the evaluation more reliable.

---

# 🚀 Future Improvements

The project can be extended in several ways.

## 1. Better Data Preprocessing

Improve handling of:

- Missing values
- Invalid measurements
- Outliers
- Zero values that may represent missing measurements

---

## 2. Advanced Model Evaluation

Add:

```text
Precision
Recall
F1-Score
Confusion Matrix
ROC-AUC
```

This would provide a much more complete understanding of model performance.

---

## 3. Cross Validation

Use **Stratified K-Fold Cross Validation** to evaluate the model across multiple data splits.

This can provide a more reliable estimate of model performance.

---

## 4. Hyperparameter Tuning

Experiment with SVM parameters such as:

```text
C
Kernel
Gamma
```

using techniques such as Grid Search.

---

## 5. Model Comparison

Compare different classification algorithms:

```text
Logistic Regression
        ↓
SVM
        ↓
Decision Tree
        ↓
Random Forest
        ↓
K-Nearest Neighbors
```

This would help identify which model performs best on the dataset.

---

## 6. Interactive Web Application

A future version can provide a simple web interface where users enter the eight health measurements and receive the model prediction.

Possible technology:

```text
Streamlit
```

The application could provide:

```text
Patient Input
     ↓
Preprocessing
     ↓
Trained Model
     ↓
Prediction
     ↓
Result + Confidence / Explanation
```

---

## 7. Model Explainability

Future versions could include explainability techniques to help understand which features contribute most to a prediction.

Possible approaches include:

- Feature importance analysis
- SHAP
- LIME

---

# ⚙️ Setup and Execution

## Local Development

### 1. Clone the repository

```bash
git clone https://github.com/srigakollumounika/AI-ML-Projects.git
```

### 2. Navigate to the project

```bash
cd AI-ML-Projects/Diabetes-Prediction
```

### 3. Create a virtual environment

```bash
python -m venv .venv
```

### 4. Activate the virtual environment

**Windows:**

```bash
.venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Start Jupyter Notebook

```bash
jupyter notebook
```

### 7. Open the notebook

Open:

```text
diabetes_prediction.ipynb
```

Run the notebook cells from top to bottom.

---

# 📦 Requirements

The project requires:

```text
numpy
pandas
scikit-learn
matplotlib
seaborn
jupyter
ipykernel
```

All dependencies can be installed using:

```bash
pip install -r requirements.txt
```

---

# 🎓 Learning Outcomes

Through this project, I learned how to:

- Work with a real-world machine learning dataset
- Load and analyse CSV data
- Understand features and target variables
- Identify a supervised learning problem
- Understand binary classification
- Perform feature standardization
- Split data into training and testing sets
- Train an SVM classification model
- Understand linear kernels
- Understand decision boundaries
- Understand support vectors and margins
- Evaluate model performance using accuracy
- Make predictions using unseen input data
- Identify limitations in a machine learning workflow
- Understand how the project can be improved for production use

---

# 📌 Project Takeaway

This project demonstrates a complete **Machine Learning classification workflow** using Python and Scikit-learn.

The main learning is not only the final accuracy score, but understanding the reasoning behind every major step:

```text
Why analyse the data?
        ↓
Why separate features and target?
        ↓
Why standardize the features?
        ↓
Why split the dataset?
        ↓
Why SVM?
        ↓
Why a linear kernel?
        ↓
How do we evaluate the model?
        ↓
How can the model be improved?
```

This makes the project useful as both a practical machine learning implementation and a learning exercise in understanding the complete ML pipeline.

---

# 🚀 Future Projects

This project is part of my growing collection of **AI & Machine Learning projects**.

More projects covering:

- 🤖 Artificial Intelligence
- 🧠 Machine Learning
- 📊 Data Science
- 👁️ Computer Vision
- 💬 Natural Language Processing
- 📈 Predictive Analytics

will be added to this repository.

---

<p align="center">
  <strong>🩺 Diabetes Prediction</strong><br/>
  Built with Python, Pandas, NumPy and Scikit-learn
</p>

<p align="center">
  <strong>🚀 Learning • Building • Improving</strong>
</p>
