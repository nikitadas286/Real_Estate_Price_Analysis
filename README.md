# 🏡 Real Estate Price Analytics

##  Project Overview

| Item | Details |
| --- | --- |
| Domain | Real Estate / Housing Market Analytics |
| Dataset | King County House Sales (version with missing values) |
| Original records | 21,613 |
| Original columns | 22 (including an `Unnamed: 0` column removed during cleaning) |
| Variable of interest | `price` |
| Environment | Jupyter Notebook |
| Libraries | Python, NumPy, Pandas, Matplotlib, Seaborn |

##  Objectives

- Explore the distribution of house sale prices and common property characteristics.
- Identify missing data and prepare the dataset for analysis.
- Investigate relationships between prices and living area, bathrooms, waterfront status, construction year, and construction grade.
- Present findings with interpretable charts and written observations.
- Support data-informed discussions about real estate pricing.

##  Tools and Techniques

| Tool / Technique | How it is used |
| --- | --- |
| Python | Overall analysis workflow |
| Pandas | Loading data, examining columns, handling missing values, and correlations |
| NumPy | Numerical analysis library imported in the notebook |
| Matplotlib | Histograms and chart formatting |
| Seaborn | Count plots, scatter plots, box plots, and correlation heatmaps |
| Jupyter Notebook | Combining executable code, outputs, explanations, and conclusions |

##  Project Workflow

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
### Q1. What is the distribution of house prices?

<img width="1331" height="628" alt="1 histogram" src="https://github.com/user-attachments/assets/da1c4de2-e016-4ade-aa5d-ee03a78c35fb" />


**Observation:** House prices are right-skewed. The mean price is approximately **$540,088**, while the median is **$450,000**.

**Conclusion:** Most homes fall in the lower-to-middle price ranges, with a relatively small number of high-priced properties pulling the average upward.

### Q2. What is the distribution of bedrooms?

<img width="1515" height="411" alt="2 bar chart" src="https://github.com/user-attachments/assets/2d4cad7f-36da-47f6-aa19-82ea195549d9" />


**Observation:** Houses with **3 or 4 bedrooms** are the most common in the dataset.

**Conclusion:** Three- and four-bedroom properties form a major segment of the King County housing market.

### Q3. What is the distribution of bathrooms?

<img width="1500" height="631" alt="3 hist" src="https://github.com/user-attachments/assets/d4c461e2-531b-4f59-b975-93a323e7c997" />


**Observation:** Bathroom count has a **moderate positive correlation** with house price.

**Conclusion:** Homes with more bathrooms generally command higher prices, although this is also related to overall house size.

### Q4. Does living area influence house price?

<img width="1162" height="627" alt="4 scatter" src="https://github.com/user-attachments/assets/234c528c-8d01-410f-9a6e-0d450f69c94f" />


**Observation:** The scatter plot shows a **strong positive relationship** between living area and selling price, with a correlation of **0.702**.

**Conclusion:** Larger homes generally sell for higher prices; living area is one of the strongest price-related factors examined.

### Q5. Does a waterfront location increase house price?

<img width="1208" height="620" alt="5 box plot" src="https://github.com/user-attachments/assets/886e5d56-3864-494b-b9dc-aefa38698349" />


**Observation:** The box plot indicates that waterfront properties generally have higher selling prices than non-waterfront properties.

**Conclusion:** Waterfront access is a premium property feature associated with higher market values.

### Q6. How does the year a house was built affect its selling price?

<img width="1297" height="640" alt="6 scatter" src="https://github.com/user-attachments/assets/50052b4f-77c5-456a-aab7-ebae22f00cfa" />


**Observation:** The relationship between construction year and selling price is relatively weak. Newer homes are not always more expensive than older ones.

**Conclusion:** Construction year alone is not a reliable indicator of house price.

### Q7. How are different housing features related to each other?

<img width="998" height="735" alt="7 heatmap" src="https://github.com/user-attachments/assets/6ffc89c6-f34f-4130-affb-6ac20e904184" />


**Observation:** The heatmap shows positive associations between **living area, bathrooms, construction grade, and price**.

**Conclusion:** Living area is particularly informative for understanding price differences, while multiple property features should be considered together.

##  Key Results

- **Average house price:** approximately **$540,088**.
- **Median house price:** approximately **$450,000**.
- **Living area–price correlation:** approximately **0.702**, a strong positive relationship.
- **Bedrooms:** Three- and four-bedroom houses are especially common.
- **Bathrooms:** Bathroom count is moderately positively associated with price.
- **Waterfront:** Waterfront homes generally sell at higher prices.
- **Year built:** Construction year by itself is not a strong indicator of sale price.

These findings describe **associations, not proven causal effects**. For example, waterfront homes may also differ from other homes in size, location, and quality.

##  Business Insights

**For buyers:** Compare properties on living area and quality as well as price; a newer construction year alone does not guarantee a higher market value.

**For sellers:** Living area and desirable features such as waterfront access can help explain price differences between properties.

**For real estate analysts:** Multiple property attributes should be considered together rather than relying on a single factor when assessing price patterns.

##  Final Conclusion

The analysis transforms a housing dataset with missing entries into a more usable form and explores the relationships between sale prices and property characteristics. **Living area is strongly associated with price**, while **waterfront access, bathrooms, and construction quality** are also relevant. The results show why housing prices should be examined through multiple factors instead of construction year alone.

## Author

**Nikita Das**

- [GitHub](https://github.com/nikitadas286)
- [LinkedIn](https://www.linkedin.com/in/nikita-laki-das-91786b2b3/)
