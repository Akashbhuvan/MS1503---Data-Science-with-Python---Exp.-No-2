# Experiment 2 (`exp3.pdf`): Customer Data Exploration Using Pandas

## 🎯 Aim
To create a sample customer dataset and perform data exploration, filtering, sorting, grouping, and basic statistical analytics using Pandas functions in Python.

## 📊 Dataset
The dataset consists of **8 customer records** across **7 attributes** (`Customer_ID`, `Customer_Name`, `Region`, `Age`, `Annual_Income`, `Spending_Score`, and `Loyalty_Years`):

| Customer_ID | Customer_Name | Region | Age | Annual_Income | Spending_Score | Loyalty_Years |
| :---: | :--- | :--- | :---: | :---: | :---: | :---: |
| 101 | Anita | North | 25 | 55000 | 78 | 2 |
| 102 | Rajesh | South | 32 | 72000 | 62 | 5 |
| 103 | Priya | East | 41 | 61000 | 45 | 4 |
| 104 | Vikram | West | 29 | 48000 | 88 | 3 |
| 105 | Divya | North | 35 | 85000 | 92 | 6 |
| 106 | Manoj | South | 45 | 90000 | 55 | 7 |
| 107 | Sita | East | 28 | 64000 | 70 | 3 |
| 108 | Amit | West | 40 | 58000 | 60 | 4 |

## ⚙️ Algorithm

1. **Start** the program.
2. **Import Library**: Import the `pandas` library as `pd` for tabular data manipulation and analysis.
3. **Initialize Dataset**: Create a Python dictionary `data` containing customer attributes (`Customer_ID`, `Customer_Name`, `Region`, `Age`, `Annual_Income`, `Spending_Score`, `Loyalty_Years`).
4. **Construct DataFrame**: Convert the dictionary into a structured Pandas DataFrame `df` using `pd.DataFrame(data)` and print the dataset.
5. **Inspect Structure & Summary**:
   * Display dataset dimensions (`df.shape`), column names (`df.columns`), data types and null counts (`df.info()`), and descriptive statistics (`df.describe()`).
   * Display the first 3 records (`df.head(3)`) and last 3 records (`df.tail(3)`).
6. **Sort & Filter Records**:
   * Sort customers in descending order of `Annual_Income` using `df.sort_values()`.
   * Filter high-income customers where `Annual_Income > 70000`.
7. **Perform Group-Wise & Frequency Analysis**:
   * Group customers by `Region` and calculate regional averages for `Annual_Income` and `Spending_Score` using `df.groupby().mean()`.
   * Count customer distribution across each region using `df["Region"].value_counts()`.
8. **Compute Overall Metrics & Top Performer**:
   * Identify the customer record with the highest `Spending_Score` using `df["Spending_Score"].idxmax()` and `df.loc[]`.
   * Calculate overall mean `Annual_Income` and mean `Spending_Score`.
9. **Stop** the program.

### 📝 Pseudocode

```text
BEGIN
    IMPORT pandas AS pd

    INITIALIZE data ← DICTIONARY OF customer records
    df ← DataFrame(data)

    PRINT df
    PRINT df.shape, df.columns
    CALL df.info()
    PRINT df.describe()
    PRINT df.head(3), df.tail(3)

    sorted_df ← SORT df BY "Annual_Income" DESCENDING
    high_income ← FILTER df WHERE Annual_Income > 70000

    region_avg ← GROUP df BY "Region" COMPUTE MEAN("Annual_Income", "Spending_Score")
    region_counts ← COUNT VALUES IN df["Region"]

    max_spender ← df.loc[INDEX_OF_MAX(df["Spending_Score"])]
    avg_income ← MEAN(df["Annual_Income"])
    avg_spending ← MEAN(df["Spending_Score"])

    PRINT sorted_df, high_income, region_avg, region_counts, max_spender, avg_income, avg_spending
END
```

## 🛠️ Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Data Creation** | `pd.DataFrame()` | Converts a Python dictionary into a 2D labeled tabular DataFrame |
| **Structural Inspection** | `df.shape`, `df.columns` | Retrieves dimensions `(rows, columns)` and column labels |
| | `df.info()`, `df.describe()` | Summarizes column data types, memory usage, and descriptive statistics |
| | `df.head(n)`, `df.tail(n)` | Views the first `n` and last `n` rows of the dataset |
| **Sorting & Filtering** | `df.sort_values()` | Orders records by `Annual_Income` in descending order |
| | Boolean Indexing (`df[...]`) | Filters customers with `Annual_Income > 70000` |
| **Grouping & Aggregation** | `df.groupby().mean()` | Aggregates mean income and spending score per `Region` |
| | `df["Region"].value_counts()` | Counts occurrences of customers in each region |
| | `idxmax()`, `df.loc[]`, `.mean()` | Locates the top spender row and computes dataset-wide averages |

## 💻 Program / Code

```python
# Customer Data Exploration using Pandas
import pandas as pd

# Step 1: Create a sample customer dataset
data = {
    "Customer_ID": [101, 102, 103, 104, 105, 106, 107, 108],
    "Customer_Name": ["Anita", "Rajesh", "Priya", "Vikram", "Divya", "Manoj", "Sita", "Amit"],
    "Region": ["North", "South", "East", "West", "North", "South", "East", "West"],
    "Age": [25, 32, 41, 29, 35, 45, 28, 40],
    "Annual_Income": [55000, 72000, 61000, 48000, 85000, 90000, 64000, 58000],
    "Spending_Score": [78, 62, 45, 88, 92, 55, 70, 60],
    "Loyalty_Years": [2, 5, 4, 3, 6, 7, 3, 4]
}

# Step 2: Convert to a Pandas DataFrame
df = pd.DataFrame(data)
print("---- CUSTOMER DATASET ----")
print(df)

# Step 3: Basic exploration
print("\nShape of Dataset:", df.shape)
print("Columns:", df.columns.tolist())

print("\n---- Dataset Info ----")
df.info()

print("\n---- Summary Statistics ----")
print(df.describe())

# Step 4: Display first and last few records
print("\nFirst 3 Records:\n", df.head(3))
print("\nLast 3 Records:\n", df.tail(3))

# Step 5: Sort customers by Annual Income (descending)
print("\nCustomers Sorted by Annual Income:\n", df.sort_values(by="Annual_Income", ascending=False))

# Step 6: Filter high-income customers (Income > 70000)
print("\nHigh Income Customers (Income > 70000):\n", df[df["Annual_Income"] > 70000][["Customer_Name", "Annual_Income"]])

# Step 7: Group customers by Region and find average Income and Spending Score
print("\nRegion-wise Average Income and Spending Score:")
print(df.groupby("Region")[["Annual_Income", "Spending_Score"]].mean())

# Step 8: Count number of customers in each Region
print("\nCustomer Count per Region:")
print(df["Region"].value_counts())

# Step 9: Identify customer with maximum Spending Score
max_spender = df.loc[df["Spending_Score"].idxmax()]
print("\nTop Spender Details:\n", max_spender)

# Step 10: Compute overall averages
print("\nAverage Annual Income:", df["Annual_Income"].mean())
print("Average Spending Score:", df["Spending_Score"].mean())
```

## 📈 Key Insights from Output
* **Overall Averages:** Average Annual Income is **$66,625.00** and Average Spending Score is **$68.75**.
* **Highest Earner:** Manoj (`Customer_ID: 106`, South) has the highest annual income at **$90,000**.
* **Top Spender:** Divya (`Customer_ID: 105`, North) achieves the highest spending score of **92** with an income of **$85,000**.
* **Regional Performance:** The **South** region leads in average annual income (**$81,000.00**), while the **North** region leads in average spending score (**85.0**).

## ✅ Result
The program successfully creates a customer dataset using Pandas and performs exploratory analysis, sorting, filtering, regional grouping, and summary statistics.

## 🚀 How to Run
1. Install Pandas (if not already installed):
   ```bash
   pip install pandas
   ```
2. Run the script:
   ```bash
   python exp3_customer_exploration.py
   ```