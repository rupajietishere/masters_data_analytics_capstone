# Accelerating Digital Banking Adoption Through Predictive Analytics

**Author:** Rupajiet Bhattacharjee  
**Institution:** Walsh College  
**Course:** QM640: Data Analytics Capstone  
**Term:** 3rd Term 2026  

---

## 📌 Project Overview
Digital financial inclusion is a critical cornerstone of global economic development. While billions of dollars are invested annually by FinTech startups, commercial banks, and NGOs into digital infrastructure, global digital banking adoption rates remain highly asymmetric. 

This capstone project transitions financial inclusion research from descriptive reporting to predictive analytics. Using a dual-dataset approach, the study identifies the exact infrastructural and socio-economic thresholds required to successfully transition demographics from low to high digital banking usage.

## 🔬 Research Questions & Hypotheses

🔹 **Research Question 1 (RQ1): Drivers of Adoption**
> What socio-economic and infrastructural variables currently drive the successful adoption of digital banking across different global regions?
> *   🔸 **Null Hypothesis ($H_0$):** There is no statistically significant correlation between specific variables and digital banking adoption ($\rho = 0$).
> *   🔸 **Alternative Hypothesis ($H_a$):** There is a statistically significant correlation between specific variables and digital banking adoption ($\rho \neq 0$).

🔹 **Research Question 2 (RQ2): Economic Resilience**
> Is there a statistically significant association between national digital penetration levels and economic resilience indicators over time?
> *   🔸 **Null Hypothesis ($H_0$):** There is no statistically significant association over time between penetration and resilience (the regression coefficient $\beta = 0$).
> *   🔸 **Alternative Hypothesis ($H_a$):** There is a statistically significant association over time between penetration and resilience (the regression coefficient $\beta \neq 0$).

🔹 **Research Question 3 (RQ3): Actionable Thresholds**
> What specific actionable factors and infrastructural thresholds are required to enable a demographic transition to high digital banking usage?
> *   🔸 **Null Hypothesis ($H_0$):** Specific actionable factors do not significantly affect the odds of a demographic adopting digital banking (Odds Ratio = 1).
> *   🔸 **Alternative Hypothesis ($H_a$):** Specific actionable factors significantly affect the odds of a demographic adopting digital banking (Odds Ratio $\neq 1$).

🔹 **Research Question 4 (RQ4): Geographic Clustering**
> Do distinct geographic clusters exist within global digital banking infrastructure data, and if so, what investment strategies do they imply?
> *   🔸 **Null Hypothesis ($H_0$):** The global geographic data exhibits no meaningful cluster structure (Silhouette Score $\le 0$).
> *   🔸 **Alternative Hypothesis ($H_a$):** The global geographic data exhibits meaningful cluster structure (Silhouette Score $> 0$).

## 📊 Data Sources
The analysis employs a dual-dataset approach sourced from the **World Bank Global Findex Database**:
1. **Primary Microdata (N = 144,091):** Individual survey responses (2021) for demographic classification.
2. **Macro Indicators (N = 381,791):** Country-level aggregates (2011–2022) for clustering and regression.

**Data Availability Note:** The macro indicators dataset (`WB_FINDEX.zip`) is compressed to comply with GitHub's file size limits. The notebooks are configured to read directly from the `.zip` archive.

## 🗂️ Repository Structure
```text
masters_data_analytics_capstone/
│
├── data/
│   ├── raw/
│   │   ├── findex_microdata_2025_labelled_update112425.csv  # Microdata dataset
│   │   └── WB_FINDEX.zip                                    # Macro Indicators (Compressed)
│   └── processed/                                           # Reserved for future data exports
│
├── notebooks/
│   ├── 01_Microdata_EDA_and_Predictive_Modeling.ipynb   # RQ1 & RQ3: EDA, LogReg, & Deployment Sim
│   └── 02_Macrodata_Econometrics_and_Clustering.ipynb   # RQ2 & RQ4: Panel Regression & Clustering
│
├── reports/                  # Project Documentation (Synopsis, Interim, & Final Reports)
├── .gitignore                # Project ignore rules
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## 🛠️ Tech Stack & Methodology
* **Language:** Python 3.13.9
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `linearmodels`, `statsmodels`
* **Methodologies:** 
  * **Supervised Learning:** Multivariate Logistic Regression.
  * **Unsupervised Learning:** K-Means (Elbow Method) and DBSCAN.
  * **Econometrics:** Pooled OLS Regression with Clustered Standard Errors.

## 🏆 Final Results Summary
*   **Socio-Economic Drivers (RQ1):** Correlation analysis identified **education ($r = 0.33$)** and **consistent internet access ($r = 0.31$)** as the most significant individual-level predictors of adoption. Cross-tabulations revealed a massive systemic disparity, with a **31% adoption gap** between the highest and lowest income quintiles.
*   **Predictive Power (RQ3):** The Multivariate Logistic Regression model achieved a **Recall of 70.43%**, revealing that holding all other factors constant, internet access increases the odds of digital banking adoption by **2.61 times**.
*   **Econometric Significance (RQ2):** The Pooled OLS model explained **66.7% of the variance** ($R^2 = 0.667$) in national digital penetration, confirming that at a macro level, internet infrastructure is the primary engine of financial inclusion.
*   **Geospatial Segmentation (RQ4):** K-Means successfully identified **3 distinct global infrastructural tiers** (Silhouette Score: 0.58), while DBSCAN isolated developmental outliers, providing a roadmap for targeted investment.
*   **Deployment Simulation:** A functional inference API demonstrated the model's practical utility, correctly identifying high-readiness profiles (84.4% probability) versus low-readiness profiles (13.9% probability).

## 💻 How to Run This Project Locally

1. **Clone the repository:**
    ```bash
    git clone https://github.com/rupajietishere/masters_data_analytics_capstone.git
    cd masters_data_analytics_capstone
    ```

2. **Set up Virtual Environment:**
    ```bash
    python -m venv venv
    .\venv\Scripts\activate  # Windows
    # source venv/bin/activate  # Mac/Linux
    ```

3. **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Execute Notebooks:**
    Run the notebooks in the `notebooks/` directory sequentially.