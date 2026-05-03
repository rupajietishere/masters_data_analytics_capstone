# Accelerating Digital Banking Adoption Through Predictive Analytics

**Author:** Rupajiet Bhattacharjee  
**Institution:** Walsh College  
**Course:** QM640: Data Analytics Capstone  
**Term:** 3rd Term 2026  

---

## 📌 Project Overview
Digital financial inclusion is a critical cornerstone of global economic development. While billions of dollars are invested annually by FinTech startups, commercial banks, and NGOs into digital infrastructure, global digital banking adoption rates remain highly asymmetric. Expanding into markets that lack prerequisite socio-economic readiness results in elevated customer acquisition costs and substantial financial losses.

This capstone project utilizes descriptive statistics, inferential hypothesis testing, predictive classification, and unsupervised machine learning to identify the exact infrastructural, technological, and socio-economic factors required to successfully transition demographics from low to high digital banking usage.

## 🔬 Research Questions & Hypotheses

* **RQ1 (Exploratory):** What socio-economic and infrastructural variables currently drive the successful adoption of digital banking across different global regions?
  * **Null Hypothesis ($H_0$):** There is no statistically significant correlation between specific socio-economic/infrastructural variables (e.g., income, education, internet access) and the rate of digital banking adoption ($\rho = 0$).
  * **Alternative Hypothesis ($H_a$):** There is a statistically significant correlation between specific socio-economic/infrastructural variables and the rate of digital banking adoption ($\rho \neq 0$).

* **RQ2 (Inferential):** Is there a statistically significant association between national digital banking penetration levels and economic resilience indicators across countries over time?
  * **Null Hypothesis ($H_0$):** There is no statistically significant association between high digital banking penetration and national economic resilience indicators over time (the regression coefficient $\beta = 0$).
  * **Alternative Hypothesis ($H_a$):** There is a statistically significant association between high digital banking penetration and national economic resilience indicators over time (the regression coefficient $\beta \neq 0$).

* **RQ3 (Predictive):** What specific actionable factors and infrastructural thresholds are required to enable and transition a low-adoption demographic into a high digital banking usage category?
  * **Null Hypothesis ($H_0$):** Specific actionable factors (such as reaching a certain education level or mobile access threshold) do not significantly affect the odds of a demographic adopting digital banking (Odds Ratio $= 1$).
  * **Alternative Hypothesis ($H_a$):** Specific actionable factors significantly affect the odds of a demographic adopting digital banking (Odds Ratio $\neq 1$).

* **RQ4 (Unsupervised):** Do distinct geographic clusters exist within global digital banking infrastructure data, and if so, what investment strategies do these clusters imply for governments and development institutions?
  * **Null Hypothesis ($H_0$):** The global geographic data exhibits no meaningful cluster structure, as indicated by a Silhouette Score $\le 0$ and a high Davies-Bouldin Index.
  * **Alternative Hypothesis ($H_a$):** The global geographic data exhibits meaningful cluster structure, as indicated by a Silhouette Score $> 0$ and a low Davies-Bouldin Index, enabling identification of distinct geographic groupings based on technological readiness.

## 📊 Data Sources
The empirical analysis employs a dual-dataset approach sourced from the **World Bank Global Findex Database**:
1. **Primary Microdata (N = 144,091):** Individual-level survey responses used to evaluate socio-demographic readiness and calculate Odds Ratios via Logistic Regression. Included as `findex_microdata_2025_labelled_update112425.csv`.
2. **Macro Indicators (N = 381,791):** Country-level aggregated percentages of financial inclusion metrics over time. Utilized for geospatial unsupervised clustering (K-Means/DBSCAN) and panel data regression. Included as `WB_FINDEX.zip`.

**Data Availability Note:** To comply with GitHub's strict 100 MB file size limits, the microdata dataset (~49 MB) is uploaded directly in its raw format. The larger macro indicators dataset (~153 MB) has been compressed into a `.zip` archive. The accompanying code/notebooks are configured using `pandas` to read directly from the `.zip` file, requiring no manual extraction.

## 🗂️ Repository Structure

masters_data_analytics_capstone/
│
├── data/
│   ├── raw/
│   │   ├── findex_microdata_2025_labelled_update112425.csv  # Primary Microdata dataset
│   │   └── WB_FINDEX.zip                                    # Macro Indicators dataset (Compressed)
│   │
│   └── processed/
│       └── .gitkeep                                         # Placeholder for cleaned data outputs
│
├── notebooks/
│   └── 01_EDA_and_Data_Cleaning.ipynb  # RQ1 & RQ3: Data Cleaning, EDA, Logistic Regression
│
├── reports/                  # PDF/Word drafts of the Synopsis and Interim Reports
├── .gitignore                # Configured to track datasets while ignoring cache/venvs
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation

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
