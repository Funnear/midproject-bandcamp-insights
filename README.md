# 🎶 Midproject: Fan Behavior & Pricing Insights on Bandcamp

## Overview

This project explores independent music sales on **Bandcamp**, focusing on how pricing, formats, and geography influence fan behavior. Using a dataset of over 1 million transactions, we aim to draw actionable insights through Exploratory Data Analysis (EDA), inferential statistics, and machine learning.

This project was developed as part of my data science bootcamp, with the goal of building a reusable analytics framework for long-term music tech research.

---

## 🧩 Objectives

- Understand **fan generosity**: What factors influence listeners to pay more than the listed price?
- Identify **sales trends** across formats (digital, physical, merch).
- Explore **geographic patterns** in item pricing and buyer behavior.
- Train and evaluate a predictive model to estimate fan generosity.
- Create reusable code modules and data workflows for future music tech projects.

---

## 📁 Repository Structure
midproject-bandcamp-insights/
│
├── data/                         # Raw and processed data
├── docs/                         # Markdown files with documentation
├── notebooks/                    # Jupyter notebooks for each step
├── src/                          # Python modules
│   └── data_ravers_utils/       # Shared utility library (submodule)
├── visuals/                      # Saved plots and figures
├── presentation/                 # Final presentation slides
├── requirements.txt
├── LICENSE
└── README.md

---

## 🧪 Datasets

### 🎧 [Bandcamp Sales Dataset (2020)](https://www.kaggle.com/datasets/mathurinache/1000000-bandcamp-sales)
- Over 1 million purchases between September and October 2020
- Includes:
  - Artist & album names
  - Buyer country & region
  - Format types (digital, physical, merch)
  - Listed price, actual paid, and overpayment

> Data source: Kaggle, by [Mathurin Ache](https://www.kaggle.com/mathurinache)

---

## 🛠️ Tools & Technologies

- **Python** (Pandas, Seaborn, Scikit-learn, PyMySQL)
- **Jupyter Notebooks**
- **MySQL** (for optional SQL operations)
- **Streamlit** (optional interactive demo)
- **Git + GitHub**
- **Kaggle API** for dataset access

---

## 🧠 Methodology

1. **Data Cleaning**
   - Handling missing values
   - Currency normalization
   - Derived binary target: `paid_more_than_price`
   
2. **EDA**
   - Price distributions by format
   - Country-wise average payments
   - Buyer generosity across genres & product types

3. **Inferential Stats**
   - Correlation between base price and overpayment
   - Group differences across formats and regions

4. **Modeling**
   - Binary classification: Predict if buyer pays more than price
   - Algorithms: Logistic Regression, Random Forest, XG Boost
   - Evaluation: Accuracy, ROC AUC, Precision/Recall

5. **Presentation**
   - Visual storytelling of findings and model insights
   - Prepared for 5–7 minute delivery in bootcamp setting

---

## 💡 Key Insights

- [Placeholder for 2–3 insights you will extract during EDA/modeling phase]

---

## 🔁 Reusability & Long-Term Vision

This project is the first step in a broader data science roadmap to:
- Build a **genre taxonomy** for electronic music
- Analyze global music distribution and fan economics
- Develop a **modular analytics library**: [`data_ravers_utils`](https://github.com/Funnear/data_ravers_utils)
- Contribute to music tech platforms like [Luminate](https://luminatedata.com/) or [Viberate](https://viberate.com/)

---

## 📜 Author & Acknowledgments

Created by **[Your Name]** during the [Your Bootcamp Name] Data Science Bootcamp.

Special thanks to:
- My bootcamp peers for inspiration
- Dataset contributors on Kaggle
- Open source libraries and APIs supporting music data

---

## 📌 Future Work

- Add audio features using Beatport/Spotify APIs
- Extend modeling to multiclass genre prediction
- Train deeper models (XGBoost, LSTM, etc.)
- Explore fan lifetime value and artist revenue patterns

---

## 🖇️ License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.
