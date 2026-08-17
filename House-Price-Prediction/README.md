<div align="center">

![Header](https://capsule-render.vercel.app/api?type=venom&color=gradient&customColorList=2,6,12,20&height=220&section=header&text=House%20Price%20Prediction&fontSize=48&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=🏡%20XGBoost-Powered%20Regression%20on%20the%20Boston%20Housing%20Dataset&descAlignY=55&descSize=16)

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=800&color=7F5AF0&center=true&vCenter=true&width=650&lines=Predicting+house+prices+with+XGBoost+%F0%9F%9A%80;R%C2%B2+Score%3A+0.87+on+unseen+data+%F0%9F%93%88;From+raw+CSV+to+trained+model+in+one+notebook+%F0%9F%93%92" alt="Typing SVG" />

<br>

[![Made with Python](https://img.shields.io/badge/Made%20with-Python-7F5AF0?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Powered by XGBoost](https://img.shields.io/badge/Powered%20by-XGBoost-2CB67D?style=flat-square&logo=xgboost&logoColor=white)](https://xgboost.readthedocs.io/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML%20Toolkit-FF8906?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F25F5C?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![MIT License](https://img.shields.io/badge/License-MIT-94A1B2?style=flat-square)](#-license)

</div>

<br>

<img align="right" width="320" src="https://raw.githubusercontent.com/github/explore/main/topics/machine-learning/machine-learning.png" alt="ML illustration" />

## 🧭 What is this?

A clean, end-to-end **regression project** that predicts median house prices in the Boston area using 13 real-world features — crime rate, room count, tax rate, pollution levels, and more.

The notebook walks through:

```
📥 Load  →  🧹 Clean  →  🔎 Explore  →  ✂️ Split  →  🤖 Train  →  📐 Evaluate  →  🎨 Visualize
```

Built as a compact reference for the **classic supervised regression workflow**, using `XGBRegressor` as the model of choice for its strength on structured/tabular data.

<br clear="right"/>

---

## 🚦 Quick Stats

<div align="center">

| 📦 Rows | 🧬 Features | 🎯 Target | 🧠 Model | 📈 Test R² | 📉 Test MAE |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **506** | **13** | `medv` | XGBoost | **0.870** | **2.36** |

</div>

---

## 🎨 Color-Coded Pipeline

<table>
<tr>
<td width="50%" valign="top">

### 🔵 Phase 1 — Data Prep
- Load `Boston.csv` with Pandas
- Copy into a working DataFrame
- Confirm shape → `(506, 15)`
- Check for nulls → **none found**
- Generate `.describe()` statistics

</td>
<td width="50%" valign="top">

### 🟢 Phase 2 — Exploration
- Compute full correlation matrix
- Plot a `Blues` **Seaborn heatmap**
- Identify strong feature relationships
- Spot which variables drive `medv`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🟠 Phase 3 — Modeling
- Split features `X` / target `Y`
- 80/20 train-test split (`random_state=2`)
- Fit an `XGBRegressor`
- Generate predictions on both sets

</td>
<td width="50%" valign="top">

### 🔴 Phase 4 — Evaluation
- Score with **R²** and **MAE**
- Compare train vs. test performance
- Plot actual vs. predicted scatter chart
- Diagnose over/underfitting

</td>
</tr>
</table>

---

## 📚 Dataset at a Glance

<div align="center">

```
┌─────────────────────────────────────────────────────────┐
│  Boston Housing Dataset  ·  506 rows  ×  14 columns      │
├─────────────────────────────────────────────────────────┤
│  crim  zn  indus  chas  nox  rm  age  dis  rad  tax      │
│  ptratio  black  lstat  →  medv (🎯 target)               │
└─────────────────────────────────────────────────────────┘
```

</div>

<details>
<summary><b>🔍 Click to expand full feature glossary</b></summary>

<br>

| Feature | What it measures |
|:--|:--|
| `crim` | 🚨 Per-capita crime rate by town |
| `zn` | 🏞️ % of residential land zoned for large lots |
| `indus` | 🏭 % of non-retail business acreage |
| `chas` | 🌊 Borders the Charles River? (1 = yes, 0 = no) |
| `nox` | 💨 Nitric oxide concentration (air quality) |
| `rm` | 🛏️ Average rooms per dwelling |
| `age` | 🏚️ % of units built before 1940 |
| `dis` | 🚗 Distance to 5 Boston employment hubs |
| `rad` | 🛣️ Accessibility to radial highways |
| `tax` | 💵 Property tax rate per $10,000 |
| `ptratio` | 🏫 Pupil-teacher ratio |
| `black` | 👥 Proportion of Black residents by town |
| `lstat` | 📉 % of population classified "lower status" |
| `medv` | 🎯 **Median home value ($1000s) — the target** |

</details>

---

## 📈 Results Breakdown

<div align="center">

| | 🏋️ Training Set | 🧪 Test Set |
|:--|:---:|:---:|
| **R² Score** | 🟩 `0.9999` | 🟨 `0.8701` |
| **MAE** | 🟩 `0.0115` | 🟨 `2.3597` |

</div>

```
Train R² ████████████████████ 99.9%
Test  R² █████████████████░░░ 87.0%
```

> 🟡 **Reading the gap:** near-perfect training accuracy next to a lower test score is the textbook signature of **overfitting**. The model has learned the training data extremely well, but ~87% variance explained on fresh data is still a strong, usable result — with clear room to improve via regularization or cross-validation.

---

## 🛠️ Built With

<div align="center">

<img src="https://skillicons.dev/icons?i=python,jupyter" height="50"/>
&nbsp;&nbsp;
![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/-Matplotlib-11557C?style=flat-square&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/-Seaborn-4C72B0?style=flat-square)
![scikit-learn](https://img.shields.io/badge/-scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/-XGBoost-EC5F42?style=flat-square)

</div>

---

## 🚀 Run it Yourself

```bash
# 1. Clone the repo
git clone https://github.com/your-username/House-Price-Prediction.git
cd House-Price-Prediction

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn xgboost

# 3. Launch the notebook
jupyter notebook House_Price_Prediction.ipynb
```

Then run all cells top to bottom — the notebook is fully self-contained, from raw CSV to final scatter plot.

---

## 🧩 Repo Structure

```
House-Price-Prediction/
├── 📓 House_Price_Prediction.ipynb   ← main notebook
├── 📄 Boston.csv                     ← dataset
└── 📘 README.md                      ← you are here
```

---

## 🔮 Roadmap

- [ ] 🔧 Hyperparameter tuning with `GridSearchCV`
- [ ] 🧪 K-fold cross-validation for robustness
- [ ] ⚖️ Add regularization to reduce overfitting
- [ ] 🥊 Benchmark against Random Forest & Linear Regression
- [ ] 💾 Export trained model with `joblib`
- [ ] 🌐 Ship a Streamlit demo app for live predictions

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

```bash
# Fork → branch → commit → PR
git checkout -b feature/your-idea
git commit -m "Add: your idea"
git push origin feature/your-idea
```

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for details.

<div align="center">

![Footer](https://capsule-render.vercel.app/api?type=venom&color=gradient&customColorList=2,6,12,20&height=120&section=footer)

**⭐ Star this repo if it helped you learn something! ⭐**

</div>
