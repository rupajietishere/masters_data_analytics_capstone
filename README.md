# Accelerating Digital Banking Adoption Through Predictive Analytics

**Author:** Rupajiet Bhattacharjee  
**Institution:** Walsh College  
**Course:** QM640: Data Analytics Capstone  
**Term:** 3rd Term 2026  

---

## 📌 Project Overview
Digital financial inclusion is a critical cornerstone of global economic development. While billions of dollars are invested annually by FinTech startups, commercial banks, and NGOs into digital infrastructure, global digital banking adoption rates remain highly asymmetric. Expanding into markets that lack prerequisite socio-economic readiness results in elevated customer acquisition costs and substantial financial losses.

This capstone project utilizes descriptive statistics, inferential hypothesis testing, predictive classification, and unsupervised machine learning to identify the exact infrastructural, technological, and socio-economic factors required to successfully transition demographics from low to high digital banking usage.

## 🔬 Research Questions
* **RQ1 (Exploratory):** What socio-economic and infrastructural variables currently drive the successful adoption of digital banking across different global regions?
* **RQ2 (Inferential):** Is there a statistically significant association between national digital banking penetration levels and economic resilience indicators across countries over time?
* **RQ3 (Predictive):** What specific actionable factors and infrastructural thresholds are required to enable and transition a low-adoption demographic into a high digital banking usage category?
* **RQ4 (Unsupervised):** Do distinct geographic clusters exist within global digital banking infrastructure data, and if so, what investment strategies do these clusters imply?

## 📊 Data Sources
The empirical analysis employs a dual-dataset approach sourced from the **World Bank Global Findex Database**:
1. **Primary Microdata (N = 144,091):** Individual-level survey responses used to classify socio-demographic readiness and calculate Odds Ratios (Logistic Regression).
2. **Macro Indicators (N = 381,791):** Country-level aggregated percentages of financial inclusion used for geospatial unsupervised clustering (K-Means/DBSCAN) and panel data regression.

*(Note: Due to file size constraints, the raw `.csv` data files are not hosted in this repository. They can be downloaded directly from the[World Bank Microdata Library](https://microdata.worldbank.org/index.php/catalog/global-findex).)*

## 🗂️ Repository Structure
```text
masters_data_analytics_capstone/
│
├── data/
│   ├── raw/                  # Ignored via .gitignore (Raw World Bank CSVs)
│   └── processed/            # Ignored via .gitignore (Cleaned datasets)
│
├── notebooks/
│   └── 01_EDA_and_Data_Cleaning.ipynb  # RQ1 & RQ3: Data Cleaning, EDA, Logistic Regression
│
├── reports/                  # PDF/Word drafts of the Synopsis and Interim Reports
├── .gitignore                # Prevents large data files & virtual environments from pushing
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```
## 🛠️ Methodology & Tech Stack
* **Language:** Python 3.x
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
* **Modeling Techniques:** 
  * Pearson/Spearman Correlation (EDA)
  * Multivariate Logistic Regression (Odds Ratio Extraction)
  * Panel Data Regression *(In Progress)*
  * K-Means & DBSCAN Clustering *(In Progress)*

## 🚀 Current Progress (Interim Phase)
- [x] Defined Research Methodology & Capstone Synopsis.
- [x] Environment configuration and Git repository setup.
- [x] Cleaned and pre-processed the Global Findex Microdata.
- [x] Completed Exploratory Data Analysis (Correlation matrices, cross-tabulations).
- [x] Deployed baseline Logistic Regression model (**Accuracy:** 67.57%, **Recall:** 70.43%).
- [x] Extracted Odds Ratios confirming internet access and education as primary adoption drivers.
- [ ] *Next Phase: Clean and merge Macroeconomic dataset.*
- [ ] *Next Phase: Execute K-Means & DBSCAN geospatial clustering (RQ4).*

## 💻 How to Run This Project Locally

1. Clone this repository:
    ```bash
    git clone https://github.com/rupajietishere/masters_data_analytics_capstone.git
    ```

2. Navigate to the project directory:
    ```bash
    cd masters_data_analytics_capstone
    ```

3. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use: .\venv\Scripts\activate
    ```

4. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

5. Download the raw data from the World Bank and place it in the `data/raw/` folder.

6. Open Jupyter via VS Code and execute the notebooks in the `notebooks/` directory.
