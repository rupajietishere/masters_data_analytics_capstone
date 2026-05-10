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

### Research Question 1 (RQ1): Drivers of Adoption
*   **Question:** What socio-economic and infrastructural variables currently drive the successful adoption of digital banking across different global regions?
*   **Null Hypothesis ($H_0$):** There is no statistically significant correlation between specific socio-economic/infrastructural variables and the rate of digital banking adoption ($\rho = 0$).
*   **Alternative Hypothesis ($H_a$):** There is a statistically significant correlation between specific socio-economic/infrastructural variables and the rate of digital banking adoption ($\rho \neq 0$).

### Research Question 2 (RQ2): Economic Resilience
*   **Question:** Is there a statistically significant association between national digital banking penetration levels and economic resilience indicators across countries over time?
*   **Null Hypothesis ($H_0$):** There is no statistically significant association over time between high digital banking penetration and national economic resilience indicators (the regression coefficient $\beta = 0$).
*   **Alternative Hypothesis ($H_a$):** There is a statistically significant association over time between high digital banking penetration and national economic resilience indicators (the regression coefficient $\beta \neq 0$).

### Research Question 3 (RQ3): Actionable Thresholds
*   **Question:** What specific actionable factors and infrastructural thresholds are required to enable and transition a low-adoption demographic into a high digital banking usage category?
*   **Null Hypothesis ($H_0$):** Specific actionable factors do not significantly affect the odds of a demographic adopting digital banking (Odds Ratio = 1).
*   **Alternative Hypothesis ($H_a$):** Specific actionable factors significantly affect the odds of a demographic adopting digital banking (Odds Ratio $\neq 1$).

### Research Question 4 (RQ4): Geographic Clustering
*   **Question:** Do distinct geographic clusters exist within global digital banking infrastructure data, and if so, what investment strategies do these clusters imply?
*   **Null Hypothesis ($H_0$):** The global geographic data exhibits no meaningful cluster structure (Silhouette Score $\le 0$).
*   **Alternative Hypothesis ($H_a$):** The global geographic data exhibits meaningful cluster structure (Silhouette Score $> 0$).

## 📊 Data Sources
The analysis employs a dual-dataset approach sourced from the **World Bank Global Findex Database**:
1. **Primary Microdata (N = 144,091):** Individual-level survey responses (2021) used for demographic classification and Odds Ratio extraction.
2. **Macro Indicators (N = 381,791):** Country-level aggregates (2011–2022) used for geospatial clustering and panel regression.

**Data Availability Note:** To comply with GitHub's file size limits, the macro indicators dataset (`WB_FINDEX.zip`) is compressed. The notebooks are configured to read directly from the `.zip` archive using `pandas`.

## 🗂️ Repository Structure
```text
masters_data_analytics_capstone/
│
├── data/
│   ├── raw/
│   │   ├── findex_microdata_2025_labelled_update112425.csv  # Microdata dataset
│   │   └── WB_FINDEX.zip                                    # Macro Indicators (Compressed)
│   └── processed/                                           # Placeholder for cleaned outputs
│
├── notebooks/
│   ├── 01_EDA_and_Data_Cleaning.ipynb          # RQ1 & RQ3: EDA, LogReg, & Deployment Sim
│   └── 02_Macro_Modeling_and_Clustering.ipynb  # RQ2 & RQ4: Panel Regression & Clustering
│
├── reports/                  # Final visual assets (ROC, Confusion Matrix, Clusters)
├── .gitignore                # Project ignore rules
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## 🛠️ Tech Stack & Methodology
* **Language:** Python 3.10
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `linearmodels`, `statsmodels`
* **Methodologies:** 
  * **Supervised Learning:** Multivariate Logistic Regression (RQ3).
  * **Unsupervised Learning:** K-Means (Elbow Method) and DBSCAN (Outlier Detection) (RQ4).
  * **Econometrics:** Pooled OLS Regression with Clustered Standard Errors (RQ2).
  * **Inference:** Extracting Odds Ratios ($e^\beta$) for actionable business thresholds.

## 🏆 Final Results Summary
*   **Predictive Power (RQ3):** The Logistic Regression model achieved a **Recall of 70.43%**, revealing that consistent internet access increases the odds of digital banking adoption by **2.61 times**.
*   **Econometric Significance (RQ2):** The Pooled OLS model explained **66.7% of the variance** ($R^2 = 0.667$) in national digital penetration, confirming internet infrastructure as the primary macro-driver.
*   **Geospatial Segmentation (RQ4):** K-Means successfully identified **3 distinct global infrastructural tiers** (Silhouette Score: 0.58), providing a roadmap for targeted investment.
*   **Deployment:** The project includes a deployment simulation function that predicts adoption probability (e.g., High-readiness: 84.4% vs. Low-readiness: 13.9%).

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
    Run the notebooks in the `notebooks/` directory sequentially. The code handles the compressed data automatically.