# Exploratory Data Analysis & Valuation of Indian Real Estate Property Listings (CEP-58)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Vectorized%20Computing-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visual%20Analytics-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4c72b0)
![CBIT](https://img.shields.io/badge/Institution-CBIT%20Hyderabad-darkred)

---

## Project Metadata

| Attribute | Details |
| :--- | :--- |
| **Project Title** | Analyze Real Estate Prices and Property Listings to Identify Investment Hotspots |
| **Project ID** | `CBIT/IT-1/EDAV/2026/CEP-58` |
| **Course Name & Code** | Exploratory Data Analysis and Visualization (`22ADC31N`) |
| **Academic Program** | B.E. Information Technology (IT-1), III-Semester, A.Y. 2026–27 |
| **Institution** | Chaitanya Bharathi Institute of Technology (CBIT), Hyderabad |
| **Course Instructor** | Dr. Ramakrishna Kolikipogu, Professor, Dept. of Information Technology |
| **Student 1** | **Mohammed Fasi Ur Rahman** (Roll No: `160125737034`) |
| **Student 2** | **Mohammed Ismail** (Roll No: `160125737035`) |
| **Dataset Source** | [Indian Real Estate Property Listings Dataset — Kaggle](https://www.kaggle.com/datasets/lamskdna/real-estate-data) |

---

## 1. Problem Overview & Objective

The Indian real estate market experiences strong regional price variation and rapid multi-year appreciation across major metropolitan and IT corridors. Real estate investors and homebuyers frequently struggle to evaluate fair market valuations due to noisy, fragmented, and incomplete listing data.

This project implements a complete **Exploratory Data Analysis and Visualization (EDAV)** pipeline in Python. By combining vectorized **NumPy** array calculations, **Pandas** hierarchical data cleaning and grouping, and **Matplotlib / Seaborn** visual analytics, the study processes raw Indian residential and commercial property records to uncover micro-market pricing trends and identify high-yield investment hotspots across **Hyderabad, Bengaluru, Mumbai, Pune, Delhi NCR, and Chennai**.

---

## 2. Analytical Questions & Bloom's Taxonomy Mapping

This repository systematically solves the five core analytical problems defined for **CEP-58**:

* **Q1 (Bloom’s Level 3 — Apply | CO1, CO2):** *Calculate average property price with NumPy.*  
  Converts listing price and area columns into 1D NumPy `ndarray` vectors to compute `nanmean`, `nanmedian`, `nanstd`, interquartile ranges (`nanpercentile`), and vectorized unit valuations (`Price_Per_SqFt`) without explicit Python loops.
* **Q2 (Bloom’s Level 3 — Apply | CO2, CO3):** *Filter properties by city and type in Pandas.*  
  Applies boolean indexing, `.isin()`, `.query()`, and cross-tabulation matrices (`pd.crosstab`) to segment residential inventory across tech corridors and budget tiers (e.g., 3 BHK Apartments and Villas under ₹250 Lakhs).
* **Q3 (Bloom’s Level 4 — Analyze | CO2, CO3, CO4):** *Handle missing property attribute data.*  
  Audits missing values, removes exact duplicate records, and implements hierarchical group-wise median imputation (`groupby(['City', 'Property_Type']).transform(...)`) and mode imputation so local city price distributions are preserved without cross-city distortion.
* **Q4 (Bloom’s Level 4 — Analyze | CO3, CO4):** *Group properties by city and locality.*  
  Performs multi-level aggregation across `['City', 'Locality']` to rank micro-markets by listing liquidity (`Listing_Count`), mean/median price in Lakhs, unit valuation (`Avg_Price_Per_SqFt`), and standard deviation volatility.
* **Q5 (Bloom’s Level 5 — Evaluate | CO4, CO5):** *Plot price trends for top cities using Matplotlib.*  
  Constructs a 4-panel visual evaluation dashboard featuring multi-year price-per-sq.-ft. trajectories (2021–2026), property-type valuation comparisons, interquartile box plots with outlier detection, and a ranked horizontal bar chart of the top 10 micro-market localities.

---

## 3. Repository Structure

```text
CBIT-EDAV-CEP58-Real-Estate-Analysis/
│
├── 160125737034_160125737035_CEP58_RealEstateHotspots.ipynb   # Main Executed Jupyter Notebook
├── 160125737034_160125737035_CEP58_RealEstateHotspots.pdf     # PDF Export of Executed Notebook
├── property_listings.csv                                      # Indian Real Estate Listings Dataset
├── CEP58_RealEstate_Price_Trends.png                          # High-Res 300 DPI Visual Dashboard
└── README.md                                                  # Project Documentation
