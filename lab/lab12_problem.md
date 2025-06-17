---
layout: page
title: Lab 12 - Statistical Concepts (Hypothesis Testing Basics)
nav_exclude: true
---


## Lab 12: Designing & Debugging Functions for Basic Data Analysis with NumPy & Pandas

**Core Idea:** This lab focuses on developing and debugging reusable functions for fundamental data analysis using NumPy arrays and Pandas DataFrames. Mastering these allows for efficient handling and summary of large, structured datasets.

**Environmental Measurement Data:** You have collected extensive environmental data from various river segments, including measurements for temperature, pH, and oxygen levels. This data needs to be loaded, structured, and summarized efficiently.

**Problem:** Design and implement reusable Python functions to:
1.  Load numerical data into NumPy arrays for efficient array-based operations.
2.  Create Pandas DataFrames from structured data, allowing for column-based analysis.
3.  Calculate basic descriptive statistics (mean, median, standard deviation, min, max) for specific columns within DataFrames.
4.  Filter and select data based on specific criteria using Pandas.
You will practice debugging these functions, paying attention to data types, dimensions, and Pandas indexing.

### Worksheet:

1.  Import necessary modules: `import numpy as np`, `import pandas as pd`.
2.  Define sample data (as a list of lists, simulating rows from a CSV):
    ```python
    environmental_data_raw = [
        ['Segment_A', 25.1, 7.2, 8.5],
        ['Segment_B', 24.5, 7.8, 9.1],
        ['Segment_A', 26.0, 7.1, 8.2],
        ['Segment_C', 23.8, 7.5, 9.5],
        ['Segment_B', 25.5, 7.9, 8.8],
        ['Segment_A', 24.9, 7.3, 8.7]
    ]
    column_names = ['SegmentID', 'Temperature_C', 'pH', 'Oxygen_mg_L']
    ```

3.  Design and Implement Reusable Functions:

    a.  `create_numeric_numpy_array(data_list_of_lists, numeric_cols_indices)`:  
        * Purpose: Takes a `data_list_of_lists` (raw data) and a list of `numeric_cols_indices` (e.g., `[1, 2, 3]` for Temperature, pH, Oxygen).  
        * Extracts only the specified numerical columns and converts them to a NumPy array of appropriate `dtype` (e.g., `float`).  
        * Returns the NumPy array.  
        * Example Usage: `np_data = create_numeric_numpy_array(environmental_data_raw, [1, 2, 3])`

    b.  `create_pandas_dataframe(data_list_of_lists, columns)`:  
        * Purpose: Takes a `data_list_of_lists` and a list of `columns` for the DataFrame header.  
        * Creates and returns a Pandas DataFrame.  
        * Example Usage: `df = create_pandas_dataframe(environmental_data_raw, column_names)`

    c.  `get_column_descriptive_stats(dataframe, column_name)`:  
        * Purpose: Takes a `dataframe` and a `column_name` string.  
        * Calculates the mean, median, standard deviation, minimum, and maximum for that column.  
        * Returns a dictionary of these statistics. Handle `KeyError` if column not found.  
        * Example Usage: `temp_stats = get_column_descriptive_stats(df, 'Temperature_C')`

    d.  `filter_dataframe_by_condition(dataframe, column_name, operator_str, value)`:  
        * Purpose: Takes a `dataframe`, a `column_name`, a string `operator_str` (e.g., '>', '<', '=='), and a `value`.  
        * Filters the DataFrame rows based on the condition (e.g., `df['pH'] > 7.5`).  
        * Returns a new DataFrame containing only the filtered rows. Handle invalid operator strings.  
        * Example Usage: `high_pH_df = filter_dataframe_by_condition(df, 'pH', '>', 7.5)`

5.  Integrate Functions for Workflow:  
    * Create a NumPy array for the numerical data. Print its shape and mean of the 'Temperature_C' column (index 1).  
    * Create a Pandas DataFrame from the raw data.  
    * Use `get_column_descriptive_stats()` to get and print statistics for 'Oxygen_mg_L'.  
    * Use `filter_dataframe_by_condition()` to find all readings from 'Segment_A'. Print the filtered DataFrame.  

6.  Debugging Exercise:

    a.  Introduce a deliberate bug:  
        * In `create_numeric_numpy_array`, try to include a non-numeric column in `numeric_cols_indices` or forget to specify `dtype=float`.  
        * In `create_pandas_dataframe`, provide a `data_list_of_lists` where inner lists have inconsistent lengths, or provide incorrect `column_names`.  
        * In `get_column_descriptive_stats`, misspell a `column_name` or try to calculate statistics on a non-numeric column.  
        * In `filter_dataframe_by_condition`, make an error in the operator string comparison logic.
    b.  Identify the bug: Run your script and observe `ValueError` (from NumPy type conversion), `KeyError` (from Pandas column access), `IndexError`, or unexpected filtering results.
    c.  Use `print()` statements and Pandas/NumPy error messages:  
        * `print()` the `dtype` of your NumPy array.  
        * `print(dataframe.info())` after creating your DataFrame to check column dtypes and non-null counts.  
        * `print(dataframe.head())` to inspect the first few rows.  
        * `print()` the intermediate boolean series in `filter_dataframe_by_condition`.  
    d.  Fix the bug: Correct data selection, ensure consistent data structures, use appropriate Pandas/NumPy methods, and validate input to functions.  
    e.  Verify the fix: Rerun the script. Test with edge cases, such as an empty input list for data or a column containing missing values (even if the problem doesn't explicitly state missing values for this lab, it's good to consider how Pandas handles them by default).
