import pandas as pd
import matplotlib.pyplot as plt

# Load data
df = pd.read_csv("sales.csv")

# Summary statistics
print(df.describe())

# Total sales by category
category_sales = df.groupby("Category")["Sales"].sum()

# Plot chart
category_sales.plot(kind="bar")

plt.title("Total Sales by Category")
plt.xlabel("Category")
plt.ylabel("Sales")
plt.savefig("sales_chart.png")

print("\nHighest selling category:")
print(category_sales.idxmax())