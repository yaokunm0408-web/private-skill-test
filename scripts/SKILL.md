---

name: data-analysis-helper
description: Use this skill whenever the user wants to analyze data, work with CSV/Excel files, perform statistical analysis, create data visualizations, or generate data reports. This includes tasks like: "analyze this dataset", "create a chart from this data", "calculate statistics", "explore my data", "find patterns in the data", "generate a data report", or any request involving data analysis, statistical operations, or data visualization even if the user doesn't explicitly use the word "analysis".

---

# Data Analysis Helper

A skill for helping users analyze data files and perform statistical operations.

## When to Use This Skill

Use this skill when the user wants to:
- Analyze CSV, Excel, or other tabular data files
- Perform statistical calculations (mean, median, std, correlations, etc.)
- Create data visualizations (charts, graphs, plots)
- Generate data analysis reports
- Explore and understand datasets
- Find patterns or insights in data

## Workflow

### 1. Load the Data
First, identify the data file the user wants to analyze. Ask for the file path if not provided.

Use Python to load the data:
```python
import pandas as pd

# For CSV files
df = pd.read_csv('path/to/file.csv')

# For Excel files
df = pd.read_excel('path/to/file.xlsx')
```

### 2. Explore the Data
Provide a quick overview of the dataset:
- Show basic info: `df.info()`
- Display first few rows: `df.head()`
- Show summary statistics: `df.describe()`
- Check for missing values: `df.isnull().sum()`

### 3. Perform Analysis
Based on the user's request, perform appropriate analysis:

**Common operations:**
- Statistical summaries: mean, median, standard deviation
- Correlations: `df.corr()`
- Grouping and aggregation: `df.groupby()`
- Filtering and sorting

### 4. Create Visualizations
Use matplotlib or seaborn for visualizations. Always set Chinese font support:

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Set Chinese font
plt.rcParams['font.family'] = 'SimHei'

# Create plots
plt.figure(figsize=(10, 6))
# ... your plotting code ...
plt.show()
```

**Common plot types:**
- Histograms: `plt.hist()` or `sns.histplot()`
- Bar charts: `plt.bar()` or `sns.barplot()`
- Line plots: `plt.plot()` or `sns.lineplot()`
- Scatter plots: `plt.scatter()` or `sns.scatterplot()`
- Box plots: `sns.boxplot()`
- Heatmaps: `sns.heatmap()`

### 5. Generate Report
Provide a clear, structured analysis report with:
- Executive summary
- Key findings
- Visualizations
- Recommendations if applicable

## Best Practices

1. **Always check data quality**: Look for missing values, outliers, and data types
2. **Use appropriate visualizations**: Choose chart types that best represent the data
3. **Explain your findings**: Don't just show numbers - interpret what they mean
4. **Be thorough but concise**: Focus on the most important insights
5. **Handle errors gracefully**: If data loading fails, provide helpful error messages

## Example Workflow

For a request like "Analyze my sales data":

1. Load the sales data file
2. Show dataset overview (rows, columns, data types)
3. Calculate key metrics (total sales, average order value, etc.)
4. Create visualizations (sales over time, top products, etc.)
5. Identify patterns and trends
6. Provide actionable insights

## Notes

- Always ask for clarification if the user's request is ambiguous
- For large datasets, consider sampling to improve performance
- If the user wants specific analysis, focus on that rather than doing everything
- Save visualizations to files when appropriate so the user can access them
