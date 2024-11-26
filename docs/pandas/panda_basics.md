[Home](../) 
# Introduction to Pandas: A Beginner's Guide

Pandas is one of the most popular and powerful libraries for data manipulation and analysis in Python. Whether you're working with small datasets or large volumes of structured data, Pandas provides the tools you need to efficiently analyze and clean your data. In this blog, we will explore the basics of Pandas, including its core data structures, installation, and common operations.

---

## What is Pandas?

Pandas is an open-source Python library designed for data manipulation and analysis. It offers two primary data structures:

- **Series**: A one-dimensional labeled array capable of holding any data type.
- **DataFrame**: A two-dimensional labeled data structure with columns of potentially different types.

These structures allow you to perform a variety of tasks, from cleaning data and transforming it to conducting statistical analysis and creating visualizations.

---

## Installing Pandas

If you are using a tool like **Anaconda** or **Jupyter Notebook (Anaconda installation)**, you can skip this step because Pandas is pre-installed.

Otherwise, you can install Pandas using `pip`, the Python package manager.

### Installation Command:

```bash
pip install pandas
```

Once installed, you can import Pandas into your Python code using the following:

```python
import pandas as pd
```

Here, `pd` is the commonly used alias for Pandas, making it easier to reference.

---

## Core Pandas Data Structures

### 1. Series

A **Series** is a one-dimensional array-like object with labeled indices. It's similar to a column in a spreadsheet or a database.

#### Creating a Series:

```python
import pandas as pd

# Create a simple Series
data = [10, 20, 30, 40]
series = pd.Series(data)
print(series)
```

Output:

```
0    10
1    20
2    30
3    40
dtype: int64
```

#### Customizing the Index:

```python
custom_index = ['a', 'b', 'c', 'd']
series_with_custom_index = pd.Series(data, index=custom_index)
print(series_with_custom_index)
```

Output:

```
a    10
b    20
c    30
d    40
dtype: int64
```

---

## Operations on Series

### Accessing Elements:

You can access elements in a Series in multiple ways:

| **Method**              | **Example**                          | **Output**   |
|--------------------------|--------------------------------------|--------------|
| Access by index          | `series[0]`                         | `10`         |
| Access by custom index   | `series_with_custom_index['a']`      | `10`         |
| Using `.iloc[]`          | `series.iloc[0]`                    | `10`         |
| Using `.loc[]`           | `series_with_custom_index.loc['a']` | `10`         |
| Slicing                  | `series[1:3]`                       | Values 20, 30|

### Basic Operations:

| **Operation**              | **Example**                  | **Output**                |
|----------------------------|------------------------------|---------------------------|
| Addition                   | `series + 10`               | Adds 10 to each element   |
| Multiplication             | `series * 2`                | Multiplies each element   |
| Comparison                 | `series > 20`               | Boolean mask for > 20     |
| Apply a function           | `series.apply(lambda x: x**2)` | Squares each element    |
| Summation                 | `series.sum()`               | Sum of all elements       |

---

### 2. DataFrame

A **DataFrame** is a two-dimensional labeled data structure. Think of it as an in-memory table with labeled rows and columns.

#### Creating a DataFrame:

```python
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [24, 27, 22],
        'City': ['New York', 'Los Angeles', 'Chicago']}

df = pd.DataFrame(data)
print(df)
```

Output:

```
       Name  Age         City
0     Alice   24     New York
1       Bob   27  Los Angeles
2  Charlie   22      Chicago
```

---

## Operations on DataFrame

### Accessing Columns

| **Method**               | **Example**          | **Output**                      |
|---------------------------|----------------------|----------------------------------|
| Access by column name     | `df['Name']`        | Series of 'Name' values         |
| Using dot notation        | `df.Name`          | Series of 'Name' values         |
| Access multiple columns   | `df[['Name', 'City']]` | DataFrame with selected columns|

### Operations on Rows

| **Method**               | **Example**             | **Output**                     |
|---------------------------|-------------------------|---------------------------------|
| Access row by index       | `df.iloc[0]`           | Row as a Series                |
| Access specific cell      | `df.iloc[0, 1]`        | Value at (0, 1)                |
| Boolean filtering         | `df[df['Age'] > 23]`   | Filtered rows                  |

---

## Summary Statistics

| **Method**        | **Example**       | **Output**                                   |
|--------------------|-------------------|---------------------------------------------|
| Summary statistics | `df.describe()`  | Statistics for numeric columns              |
| Column statistics  | `df['Age'].mean()` | Mean of the 'Age' column                    |
| Count values       | `df['City'].value_counts()` | Counts of unique values in 'City' column|

---

## Exercises

### Series Exercises

1. Create a Pandas Series with the following data: `[5, 15, 25, 35, 45]`. Perform the following operations:
   - Access the third element.
   - Add 10 to each element.
   - Multiply all elements by 3.
   - Check which elements are greater than 20.

2. Create a custom Series with the following data:
   - Data: `[100, 200, 300, 400, 500]`
   - Indices: `['a', 'b', 'c', 'd', 'e']`
   - Access the element with index `'c'`.

### DataFrame Exercises

3. Create a DataFrame with the following data:
   ```
   Name     Age    Salary
   Alice    24     50000
   Bob      27     60000
   Charlie  22     55000
   ```
   - Access the `Salary` column.
   - Filter rows where `Age > 23`.
   - Calculate the mean salary.

4. Create a DataFrame with columns `Product`, `Price`, and `Quantity`. Add at least 4 rows of data and perform the following:
   - Add a new column `Total` as `Price * Quantity`.
   - Find the product with the highest `Total`.

5. Load a sample dataset (e.g., using `pd.read_csv()` or any available dataset). Perform the following:
   - Get basic statistics using `.describe()`.
   - Find the unique values in a specific column.
   - Group the data by one column and find the mean of another column.

---

By practicing these exercises, you'll gain hands-on experience with Pandas and develop a better understanding of its core functionalities.
