# EDA Assessment 1 – Exploratory Data Analysis

## 1. Project Title

**Exploratory Data Analysis (EDA) on Superstore Dataset**

## 2. Introduction

This project performs Exploratory Data Analysis (EDA) on the Superstore dataset. The main purpose of EDA is to understand the structure, characteristics, and important patterns present in the dataset.

Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn** are used for data loading, data inspection, statistical analysis, data preprocessing, and visualization.

## 3. Objective

The objectives of this EDA task are:

* To load the Superstore dataset.
* To inspect the dataset.
* To understand the rows and columns.
* To check the data types and structure.
* To obtain descriptive statistics.
* To convert date columns into proper date format.
* To analyze sales based on product categories.
* To visualize category-wise sales using a bar chart.

## 4. Technologies and Libraries Used

* **Python**
* **Jupyter Notebook / Google Colab**
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical data visualization

## 5. Dataset

The analysis is performed using the **Superstore dataset**.

The dataset contains information related to:

* Orders
* Customers
* Shipping
* Products
* Categories
* Sales
* Quantity
* Discount
* Profit
* Regions

The dataset contains **10,194 rows and 21 columns**.

## 6. EDA Operations Performed

### 6.1 Importing Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

These libraries are imported for data analysis and visualization.

### 6.2 Loading the Dataset

```python
df=pd.read_csv("/content/samplesuperstore.csv")
```

The Superstore CSV file is loaded into a Pandas DataFrame named `df`.

### 6.3 Displaying First Five Records

```python
df.head()
```

This operation displays the first five rows of the dataset.

**Output:**

The first five records contain information such as:

* Row ID
* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Country/Region
* City
* Category
* Sub-Category
* Product Name
* Sales
* Quantity
* Discount
* Profit

### 6.4 Displaying Last Five Records

```python
df.tail()
```

This operation displays the last five records of the dataset.

The last records belong to orders from **2026**, including customer, product, sales, quantity, discount, and profit information.

### 6.5 Checking Dataset Information

```python
df.info()
```

The dataset contains:

* **10,194 entries**
* **21 columns**
* 2 integer columns
* 3 floating-point columns
* 16 object/string columns

Important numerical columns include:

* Sales
* Quantity
* Discount
* Profit

### 6.6 Checking Dataset Shape

```python
df.shape
```

**Output:**

```text
(10194, 21)
```

This means the dataset contains **10,194 rows and 21 columns**.

### 6.7 Descriptive Statistics

```python
df.describe()
```

The `describe()` function provides statistical information for numerical columns.

Important results include:

| Column   |   Mean |   Minimum |  Maximum |
| -------- | -----: | --------: | -------: |
| Sales    | 228.23 |     0.444 | 22638.48 |
| Quantity |   3.79 |         1 |       14 |
| Discount |  0.155 |         0 |      0.8 |
| Profit   |  28.67 | -6599.978 | 8399.976 |

The statistics help to understand the distribution and range of numerical values.

### 6.8 Converting Date Columns

```python
df['Order Date']=pd.to_datetime(df['Order Date'],format='mixed')
df['Ship Date']=pd.to_datetime(df['Ship Date'],format='mixed')
```

The `Order Date` and `Ship Date` columns are converted from object/string data types into proper datetime format.

After conversion, both columns have the following data type:

```text
datetime64[ns]
```

### 6.9 Checking Data Types After Conversion

```python
df.info()
```

After preprocessing, the `Order Date` and `Ship Date` columns are correctly identified as datetime columns.

This makes the dataset suitable for future time-based analysis.

## 7. Category-wise Sales Analysis

The total sales for each product category are calculated using:

```python
category_sales = (df.groupby('Category')['Sales'].sum())
category_sales
```

### Output

```text
Category
Furniture          754747.7613
Office Supplies    731893.3140
Technology         839893.2790
Name: Sales, dtype: float64
```

The total sales values are:

| Category        |  Total Sales |
| --------------- | -----------: |
| Furniture       | 754,747.7613 |
| Office Supplies | 731,893.3140 |
| Technology      | 839,893.2790 |

## 8. Data Visualization

A bar chart is created to visualize total sales by category.

```python
category_sales.plot(kind='bar',figsize=(8,5))
plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

### Visualization Output

<img width="721" height="560" alt="image" src="https://github.com/user-attachments/assets/5c381d1d-e547-4355-9547-e9105ee70adb" />


The bar chart represents the total sales of:

* Furniture
* Office Supplies
* Technology

The chart makes it easier to compare the sales values of the three categories visually.

## 9. Key Findings

From the analysis:

1. The dataset contains **10,194 records and 21 columns**.
2. The dataset contains customer, order, product, sales, discount, and profit information.
3. `Order Date` and `Ship Date` were converted into datetime format.
4. The average sales value is approximately **228.23**.
5. The average quantity is approximately **3.79**.
6. The average profit is approximately **28.67**.
7. Category-wise sales were calculated using the `groupby()` function.
8. The three categories analyzed are **Furniture, Office Supplies, and Technology**.
9. Category-wise sales were visualized using a bar chart.

## 10. Conclusion

The EDA process helped in understanding the structure and characteristics of the Superstore dataset. Basic data inspection, statistical analysis, preprocessing, grouping, and visualization were performed using Python.

The analysis provides a basic understanding of sales performance across different product categories and prepares the dataset for further analysis and visualization.

## 11. Files Included

```text
EDA_ASSESMENT_1.ipynb
README.md
samplesuperstore.csv
```

## 12. How to Run

1. Open the `EDA_ASSESMENT_1.ipynb` file in Jupyter Notebook or Google Colab.
2. Upload the `samplesuperstore.csv` dataset.
3. Run the cells in order.
4. View the generated outputs and visualization.

---

**Submitted as:** EDA Assessment 1
**Topic:** Exploratory Data Analysis on Superstore Dataset
