# 🏠 Real Estate Price Analytics

### Exploratory Data Analysis of King County House Sales Using Python

> **Project scope:** This repository presents descriptive analysis and exploratory visualizations. Although the notebook discusses factors useful for estimating prices, it **does not implement or evaluate a house-price prediction model**.

## 📌 Project Overview

| Item | Details |
| --- | --- |
| Domain | Real Estate / Housing Market Analytics |
| Dataset | King County House Sales (version with missing values) |
| Original records | 21,613 |
| Original columns | 22 (including an `Unnamed: 0` column removed during cleaning) |
| Variable of interest | `price` |
| Environment | Jupyter Notebook |
| Libraries | Python, NumPy, Pandas, Matplotlib, Seaborn |

## 🎯 Objectives

- Explore the distribution of house sale prices and common property characteristics.
- Identify missing data and prepare the dataset for analysis.
- Investigate relationships between prices and living area, bathrooms, waterfront status, construction year, and construction grade.
- Present findings with interpretable charts and written observations.
- Support data-informed discussions about real estate pricing.


```

> The CSV must be available locally beside the notebook when running it. If you also export the notebook to HTML, you can add `Real_Estate_Analytics.html` to the repository as a static report.

## 🧰 Tools and Techniques

| Tool / Technique | How it is used |
| --- | --- |
| Python | Overall analysis workflow |
| Pandas | Loading data, examining columns, handling missing values, and correlations |
| NumPy | Numerical analysis library imported in the notebook |
| Matplotlib | Histograms and chart formatting |
| Seaborn | Count plots, scatter plots, box plots, and correlation heatmaps |
| Jupyter Notebook | Combining executable code, outputs, explanations, and conclusions |

## 🔎 Project Workflow

### 1. Data Loading and Understanding

The notebook reads `kc_house_data_NaN.csv` and explores its structure using:

- Loaded dataset using Pandas
- Checked shape, data types, and summary statistics
- Identified irrelevant and missing data

**Initial findings:** The source dataset contains **21,613 records and 22 columns**. The sale price is recorded in the `price` column.

### 2. Data Cleaning and Preprocessing

The notebook performs these operations:

1. Removes the unnecessary `Unnamed: 0` column.
2. Checks for missing values and identifies **23 missing entries**:
   - `bedrooms`: **13**
   - `bathrooms`: **10**
3. Replaces missing bedroom and bathroom values with their respective **column means**.
4. Checks for exact duplicate rows using `duplicated().sum()`.
5. Converts the `date` column to a datetime type using `pd.to_datetime()`.

**Why mean imputation?** It retains records rather than deleting houses with missing bedroom or bathroom values. Note that the imputed bedroom counts can be fractional; the notebook uses these values for exploration rather than treating them as observed counts.

### 3. Exploratory Data Analysis (EDA)

The notebook investigates seven main questions:

| # | Analysis question | Visualization | Main insight |
| --- | --- | --- | --- |
| 1 | How are house prices distributed? | Histogram | Prices are right-skewed, with fewer very expensive homes. |
| 2 | Which bedroom counts are most common? | Count plot | Three- and four-bedroom homes are common. |
| 3 | How are bathroom counts distributed? | Histogram | Bathroom counts describe the mix of housing configurations. |
| 4 | How does living area relate to price? | Scatter plot | Larger living areas generally correspond to higher prices. |
| 5 | Do waterfront homes command higher prices? | Box plot | Waterfront properties generally have higher prices. |
| 6 | How does construction year relate to price? | Scatter plot | Year built alone has a relatively weak relationship with price. |
| 7 | How are housing features correlated? | Correlation heatmap | Living area, bathrooms, and construction grade show positive relationships with price. |

## 📊 Key Results

- **Average house price:** approximately **$540,088**.
- **Median house price:** approximately **$450,000**.
- **Living area–price correlation:** approximately **0.702**, a strong positive relationship.
- **Bedrooms:** Three- and four-bedroom houses are especially common.
- **Bathrooms:** Bathroom count is moderately positively associated with price.
- **Waterfront:** Waterfront homes generally sell at higher prices.
- **Year built:** Construction year by itself is not a strong indicator of sale price.

These findings describe **associations, not proven causal effects**. For example, waterfront homes may also differ from other homes in size, location, and quality.

## 💡 Business Insights

**For buyers:** Compare properties on living area and quality as well as price; a newer construction year alone does not guarantee a higher market value.

**For sellers:** Living area and desirable features such as waterfront access can help explain price differences between properties.

**For real estate analysts:** Multiple property attributes should be considered together rather than relying on a single factor when assessing price patterns.

## 🧾 Final Conclusion

The analysis transforms a housing dataset with missing entries into a more usable form and explores the relationships between sale prices and property characteristics. **Living area is strongly associated with price**, while **waterfront access, bathrooms, and construction quality** are also relevant. The results show why housing prices should be examined through multiple factors instead of construction year alone.
