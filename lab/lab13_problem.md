---
layout: page
title: Lab 13 - Data Wrangling and Plots
nav_exclude: true
---

## Lab 13: Designing & Debugging Functions for Data Cleaning/Manipulation with Pandas & Simple Plots

**Core Idea:** This lab focuses on designing and debugging reusable functions for advanced data cleaning, manipulation, and basic visualization using Pandas and Matplotlib. These skills are critical for transforming raw data into insights and presenting them effectively.

**Dolphin Health and Habitat Data:** You have a combined dataset of dolphin health metrics and environmental parameters from their habitat, sourced from multiple reports. This data is messy: it has missing values, inconsistent formats, and needs further processing before analysis and visualization.

**Problem:** Design and implement reusable Python functions to:
1.  Load and perform initial cleaning on a CSV dataset (handle missing values, correct data types).
2.  Derive new, meaningful columns from existing ones.
3.  Generate simple exploratory plots (histograms, scatter plots) to visualize data distributions and relationships.
You will extensively debug these functions, paying attention to Pandas' data handling nuances and plotting library requirements.

### Worksheet:

1.  Import necessary modules: `import pandas as pd`, `import matplotlib.pyplot as plt`.
2.  Create a sample CSV file named `dolphin_health_habitat.csv`:
    ```csv
    DolphinID,HabitatSegment,CFU_Count,Toxin_Level,ObservationDate,Symptoms,WaterTemp_C
    SARD001,RS01,1200,2.5,2025-04-01,Lethargy,25.1
    SARD002,RS02,3500,NA,2025-04-02,Skin Lesions,24.5
    SARD003,RS01,900,1.9,2025-04-03,,26.0
    SARD004,RS02,4800,3.1,2025-04-04,Respiratory Distress,NA
    SARD005,RS03,NA,2.8,2025-04-05,Lethargy,23.8
    SARD006,RS01,2100,1.5,2025-04-06,None,25.5
    SARD007,RS02,3000,NA,2025-04-07,Lethargy,24.9
    SARD008,RS03,1500,2.2,2025-04-08,,23.5
    SARD009,RS01,4000,3.5,2025-04-09,Skin Lesions,26.2
    SARD010,RS02,NA,2.0,2025-04-10,Respiratory Distress,24.0
    ```
    *(Note: "NA" and blank for missing, mixed data types)*

3.  Design and Implement Reusable Functions:

    a.  `load_and_initial_clean_data(filepath, na_values=['NA', ''], date_columns=None)`:
        * Purpose: Takes a `filepath` to a CSV, a list of strings representing `na_values`, and an optional list of `date_columns`.
        * Loads the CSV into a Pandas DataFrame.
        * Replaces specified `na_values` with `np.nan`.
        * Converts specified `date_columns` to datetime objects.
        * Converts relevant numeric columns (e.g., 'CFU_Count', 'Toxin_Level', 'WaterTemp_C') to appropriate numeric types (e.g., `float`), coercing errors.
        * Returns the cleaned DataFrame.
        * Example Usage: `df = load_and_initial_clean_data("dolphin_health_habitat.csv", date_columns=['ObservationDate'])`

    b.  `impute_missing_numeric_column(dataframe, column_name, strategy='mean')`:
        * Purpose: Takes a `dataframe`, a `column_name`, and an `imputation strategy` ('mean', 'median', or a specific `value`).
        * Fills missing (NaN) values in the specified column using the chosen strategy.
        * Modifies the DataFrame in-place or returns a new DataFrame depending on your design choice (document clearly).
        * Example Usage: `impute_missing_numeric_column(df, 'CFU_Count', strategy='median')`

    c.  `derive_health_score(dataframe)`:
        * Purpose: Takes a `dataframe`.
        * Creates a new column, e.g., `'Health_Score'`, based on a simple formula involving existing columns (e.g., `(df['WaterTemp_C'] * df['Toxin_Level']) / df['CFU_Count']` - invent a plausible formula). Handle potential division by zero or NaN values.
        * Returns the DataFrame with the new column.
        * Example Usage: `df_with_score = derive_health_score(df)`

    d.  `plot_histogram(dataframe, column_name, title, bins=10)`:
        * Purpose: Takes a `dataframe`, `column_name`, `title`, and optional `bins`.
        * Generates and displays a histogram for the specified column using `matplotlib.pyplot.hist()`.
        * Includes labels and title.
        * Example Usage: `plot_histogram(df, 'Toxin_Level', 'Distribution of Toxin Levels')`

    e.  `plot_scatterplot(dataframe, x_column, y_column, title, xlabel, ylabel)`:
        * Purpose: Takes a `dataframe`, `x_column`, `y_column`, `title`, `xlabel`, `ylabel`.
        * Generates and displays a scatter plot using `matplotlib.pyplot.scatter()`.
        * Includes labels and title.
        * Example Usage: `plot_scatterplot(df, 'WaterTemp_C', 'CFU_Count', 'Temp vs CFU', 'Water Temperature (C)', 'CFU Count')`

5.  Integrate Functions for Workflow:
    * Call `load_and_initial_clean_data()` to load and get the initial cleaned DataFrame. Print `df.info()` and `df.head()`.
    * Call `impute_missing_numeric_column()` for 'CFU_Count' and 'Toxin_Level'. Print `df.info()` again to see changes.
    * Call `derive_health_score()` to add the new column. Print `df.head()` to verify.
    * Call `plot_histogram()` for 'CFU_Count'.
    * Call `plot_scatterplot()` for 'Toxin_Level' vs 'CFU_Count'.
    * Ensure `plt.show()` is called at the end to display all plots.

6.  Debugging Exercise:

    a.  Introduce a deliberate bug:
        * In `load_and_initial_clean_data`, forget to include a common missing value representation in `na_values`, or attempt to convert a column that still has non-numeric strings to `float`.
        * In `impute_missing_numeric_column`, try to impute a non-numeric column, or use an invalid `strategy` string.
        * In `derive_health_score`, forget to handle `np.inf` or `np.nan` that might result from division by zero, leading to plots failing.
        * In `plot_histogram` or `plot_scatterplot`, pass a column name that doesn't exist, or pass a non-numeric column to a plotting function.
        * Forget to call `plt.show()` at the end, leading to plots not appearing.
    b.  Identify the bug: Run your script and observe `ValueError`, `KeyError`, `TypeError` (e.g., trying to plot strings), or plots not rendering. Pay attention to `SettingWithCopyWarning` if it appears.
    c.  Use `print()` statements, `df.info()`, `df.describe()`, and `try-except` blocks:
        * After each cleaning/manipulation step, print `df.info()` and `df.head()` to inspect the DataFrame's state, data types, and missing values.
        * Use `try-except` around plotting calls to catch errors related to non-numeric data.
        * Check for `np.nan` and `np.inf` values in derived columns.
    d.  Fix the bug: Correct data loading parameters, ensure proper data types, handle edge cases in calculations, and use correct column names/plotting parameters.
    e.  Verify the fix: Rerun the script. Ensure all plots generate correctly, data is clean, and derived columns are accurate. Test with edge cases like all missing values in a column.
