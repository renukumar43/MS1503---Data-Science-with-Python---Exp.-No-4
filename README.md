# Experiment 4 : Yearly Revenue Growth Visualization Using Matplotlib

## Aim

To visualize the yearly trend of company revenue and expenses from 2017 to 2023 using Matplotlib by plotting multi-line charts with customized markers, labels, legends, gridlines, and point annotations.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `matplotlib.pyplot` as `plt` for plotting and `numpy` as `np` for numeric array generation and index lookup.
3. **Initialize Dataset**:
   * Generate an array `years` spanning `2017` to `2023` using `np.arange(2017, 2024)`.
   * Define lists `revenue` and `expenses` representing annual amounts in Lakhs.
4. **Configure Figure & Plot Lines**:
   * Initialize a figure canvas of size $8 \times 5$ inches using `plt.figure(figsize=(8, 5))`.
   * Plot `revenue` against `years` as a solid green line with circular markers (`marker='o'`).
   * Plot `expenses` against `years` as a dashed red line (`linestyle='--'`) with square markers (`marker='s'`).
5. **Format Chart Aesthetics**:
   * Add a bold chart title (`plt.title()`) and axis labels (`plt.xlabel()`, `plt.ylabel()`).
   * Enable dashed semi-transparent gridlines (`plt.grid()`) and place the legend in the upper-left corner (`plt.legend(loc='upper left')`).
6. **Annotate Peak Values**:
   * Find the indices of maximum revenue and maximum expenses using `np.argmax()`.
   * Highlight both peak data points on the chart with directional arrows and text callouts using `plt.annotate()`.
7. **Adjust Layout & Display**:
   * Prevent label clipping via `plt.tight_layout()` and render the final plot with `plt.show()`.
8. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Numerical Operations** | `np.arange()` | Generates evenly spaced integer years (`2017` through `2023`) |
| | `np.argmax()` | Returns the array index of the maximum revenue and expense values |
| **Line Plotting** | `plt.figure()` | Initializes a new figure window with custom dimensions |
| | `plt.plot()` | Draws line plots with customized markers, colors, line styles, and widths |
| **Chart Formatting** | `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds descriptive title and axis labels with custom font sizes |
| | `plt.grid()`, `plt.legend()` | Adds background gridlines and displays series labels in the upper left |
| **Annotations & Display** | `plt.annotate()` | Places text labels with arrows pointing to peak revenue and expense points |
| | `plt.tight_layout()`, `plt.show()` | Optimizes spacing to avoid overlapping elements and renders the figure |

## Program / Code

#Company Revenue and Expense Visualization using Matplotlib
import matplotlib.pyplot as plt
import numpy as np


# Customer Data Exploration using Pandas

import pandas as pd

# Step 1: Create a sample customer dataset
data = {
    "Customer_ID": ["C001", "C002", "C003", "C004", "C005",
                    "C006", "C007", "C008", "C009", "C010"], 

  "Customer_Name": ["Arun", "Priya", "Kumar", "Divya", "Rahul",
                      "Sneha", "Vijay", "Anita", "Karthik", "Meena"],  

   "Region": ["North", "South", "East", "West", "North",
              "South", "East", "West", "North", "South"],

   "Age": [25, 32, 28, 40, 35, 29, 45, 31, 38, 26],

   "Annual_Income": [50000, 75000, 60000, 90000, 85000,
                      55000, 70000, 95000, 80000, 65000],

   "Spending_Score": [60, 85, 70, 90, 75, 65, 80, 95, 88, 72],

   "Loyalty_Years": [2, 5, 3, 8, 6, 2, 7, 9, 5, 4]
}

# Step 2: Convert dictionary into DataFrame
df = pd.DataFrame(data)  

print("CUSTOMER DATASET")  
print(df)

# Step 3: Basic exploration
print("\nDataset Shape:", df.shape)  
print("\nColumn Names:", df.columns)  
print("\nDataset Information:")
df.info()

print("\nDescriptive Statistics:")
print(df.describe())

# Step 4: Display first and last records
print("\nFirst 3 Records:")
print(df.head(3))

print("\nLast 3 Records:")
print(df.tail(3))

# Step 5: Sort customers by Annual Income
print("\nCustomers Sorted by Annual Income:")
print(df.sort_values(by="Annual_Income", ascending=False))

# Step 6: Filter high-income customers
print("\nHigh Income Customers (Income > 70000):")
print(df[df["Annual_Income"] > 70000])

# Step 7: Group customers by Region
print("\nRegional Average Analysis:")
print(df.groupby("Region")[["Annual_Income",
                            "Spending_Score"]].mean())

# Step 8: Count customers in each region
print("\nCustomer Count by Region:")
print(df["Region"].value_counts())

# Step 9: Identify customer with maximum Spending Score
top_customer = df.loc[df["Spending_Score"].idxmax()]

print("\nTop Spending Customer:")
print(top_customer)

# Step 10: Calculate overall averages
print("\nOverall Average Annual Income:",
      df["Annual_Income"].mean())

print("Overall Average Spending Score:", 
      df["Spending_Score"].mean()) 


## Output

<img width="928" height="697" alt="image" src="https://github.com/user-attachments/assets/78504369-b349-4ba4-b47b-d17fd78b0d53" />


CUSTOMER DATASET

Dataset Shape: (10, 7)

First 3 Records:
  Customer_ID Customer_Name Region  Age  Annual_Income
0        C001          Arun  North   25          50000
1        C002         Priya  South   32          75000
2        C003         Kumar   East   28          60000

High Income Customers (Income > 70000):

  Customer_ID Customer_Name  Annual_Income
1        C002         Priya          75000
3        C004         Divya          90000
4        C005         Rahul          85000
7        C008         Anita          95000
8        C009       Karthik          80000

Regional Average Analysis:
      Annual_Income  Spending_Score
East         65000.00           75.00
North        71666.67           74.33
South        65000.00           74.00
West         92500.00           92.50

Customer Count by Region:

North    3
South    3
East     2
West     2

Top Spending Customer:

Customer_ID       C008
Customer_Name    Anita
Region            West
Age                 31
Annual_Income    95000
Spending_Score      95
Loyalty_Years        9

Overall Average Annual Income: 72500.0
Overall Average Spending Score: 78.0




## Result

The program successfully creates datasets for yearly company revenue and expenses and renders an annotated multi-line comparison chart using Matplotlib.
