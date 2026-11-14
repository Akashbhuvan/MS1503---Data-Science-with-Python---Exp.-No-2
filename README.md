# Experiment 2 : Customer Data Exploration Using Pandas

## Aim
To create a sample customer dataset and perform data exploration, filtering, sorting, grouping, and basic statistical analytics using Pandas functions in Python.

## Algorithm

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

## Functions and Methods Used

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

## Program

#Customer Data Exploration using Pandas

#Step 1: Create a sample customer dataset

#Step 2: Convert to a Pandas DataFrame

#Step 3: Basic exploration

#Step 4: Display first and last few records

#Step 5: Sort customers by Annual Income (descending)

#Step 6: Filter high-income customers (Income > 70000)

#Step 7: Group customers by Region and find average Income and Spending Score

#Step 8: Count number of customers in each Region

#Step 9: Identify customer with maximum Spending Score

#Step 10: Compute overall averages


## Output

## Result
The program successfully creates a customer dataset using Pandas and performs exploratory analysis, sorting, filtering, regional grouping, and summary statistics.
