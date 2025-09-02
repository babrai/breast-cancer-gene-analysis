# 🧬 Gene Expression Analysis: Cancer vs Normal

A simple exploratory data analysis (EDA) project using real-world gene expression data  
to identify features (probes) that differ significantly between **cancer** and **normal** tissue samples.

---

## 🔍 Project Goal

To answer the question:

> **"Which probe sets (features) are most differentially expressed between `cancer` and `normal` samples?"**

Using basic statistical and visualization tools, I aim to:

- Compare mean expression between groups
- Identify the **top 10 most distinct probes**
- Visualize the results using **boxplots** and **PCA**

---

## 📦 Dataset

- **Source**: [Kaggle – Breast Cancer Gene Expression (CUMIDA)](https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida)
- **File**: `Breast_GSE45827.csv`
- **Samples**: 151
- **Features**: ~54,000 probes (e.g., `1007_s_at`, `1053_at`)
- **Target column**: `type` → contains sample type such as `normal`, `basal`, `luminal_A`, etc.

Сreated a simplified binary column:  
📁 `group = "normal"` or `"cancer"` (any other type considered cancer)

---

## 🛠 Tools & Libraries

- Python 🐍
- `pandas`, `numpy` – data manipulation
- `scipy.stats` – t-test
- `matplotlib`, `seaborn` – plotting
- `scikit-learn` – PCA

---

## 🧪 Analysis Steps

1. **Data Cleaning & Grouping**
   - Create binary column `group` (`normal` vs `cancer`)
   - Check class balance

2. **Descriptive Statistics**
   - Compute group-wise means for each probe
   - Calculate log2 Fold Change (log2FC)

3. **Statistical Testing**
   - Run independent t-tests for all probes
   - Adjust p-values using Benjamini–Hochberg FDR

4. **Feature Ranking**
   - Select top-10 most significantly different probes
   - Export summary table with `log2FC`, p-values, and group means

5. **Visualization**
   - Boxplots for top-5 probes
   - PCA plot (2D) showing separation between groups

---

## 📊 Results

| Probe ID   | log2FC | p-value | Adj. p-value | mean_normal | mean_cancer |
|------------|--------|---------|---------------|--------------|--------------|
| ...        | ...    | ...     | ...           | ...          | ...          |

📌 These top probes show consistent and statistically significant differences  
between normal and cancer samples, making them useful indicators for classification or diagnostics.

---

## 📁 Project Structure

breast-cancer-gene-expression/
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 01-eda.ipynb
│ └── 02-differential-analysis.ipynb
├── images/
├── README.md
└── requirements.txt
