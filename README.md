# 🧹 Data Cleaning of Ask A Manager Salary Survey

This project demonstrates the full workflow of **cleaning a real-world messy dataset** (the [Ask A Manager Salary Survey](https://oscarbaruffa.com/messy/)) and preparing it for analysis and Machine Learning.  

Most real data is messy, inconsistent, and full of missing values. This notebook showcases professional data cleaning techniques to transform raw survey data into a **clean, structured, ML-ready dataset**.

---

## 🔍 Project Overview

The dataset contains thousands of survey responses with:
- Free-text job titles and locations  
- Inconsistent country and currency names  
- Salaries written in different formats (`$100k`, `120,000`, `USD 95,000`)  
- Ranges for experience instead of single values (`5–7 years`)  
- Duplicate and prank responses  

Our goal was to **clean, normalize, and structure the dataset** so it can be used confidently for:
- Exploratory Data Analysis (EDA)  
- Salary prediction models  
- Statistical insights (experience vs. pay, gender pay gap, geographic patterns)  

---

## 🛠️ Cleaning Steps

1. **Load & Inspect Raw Data**  
   - Checked data types, missing values, and irregularities.

2. **Deduplication & Filtering**  
   - Removed exact duplicates.  
   - Dropped prank/unrealistic entries (e.g., “dinosaur wrangler”).  

3. **Merge “Other” Columns**  
   - Unified responses where participants wrote custom answers (e.g., `currency_other`).  

4. **Normalize Text Fields**  
   - Standardized country names (`USA`, `U.S.A`, `United States` → `US`).  
   - Cleaned and standardized job titles using **fuzzy matching**.  

5. **Salary Cleaning**  
   - Removed symbols, commas, and text (`$`, `k`).  
   - Converted all salaries into clean numeric values.  

6. **Experience Parsing**  
   - Converted ranges like `5-7 years` into numeric (mean or midpoint).  

7. **Missing Values**  
   - Numeric: filled with **median**.  
   - Categorical: filled with **Unknown**.  

8. **Final Output**  
   - Exported clean dataset: `askamanager_cleaned.csv`.  
   - Now ready for ML/analysis.  

---

## 📊 Example Before & After

**Raw Salary Column**  
```

\$100k
120,000
95K
USD 85,500

```

**Cleaned Salary Column**  
```

100000
120000
95000
85500

```

---

## 🚀 Tech Stack

- Python  
- Pandas  
- NumPy  
- rapidfuzz (text normalization)  
- Jupyter Notebook  

---

## 📂 Project Structure

```

├── data/
│   └── AskAManager_Survey_2021.csv
├── notebooks/
│   └── cleaning\_pipeline.ipynb
├── output/
│   └── askamanager\_cleaned.csv
├── README.md

```

---

## 🌟 Key Learnings

- Real-world data is never clean.  
- Smart text normalization is as important as numeric cleaning.  
- Thoughtful imputation strategies improve downstream analysis.  
- Clean data = more reliable ML models.  

---

## 📜 License
This project is for educational purposes. Dataset credit: [Ask A Manager Salary Survey](https://oscarbaruffa.com/messy/).  
```
