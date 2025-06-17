---
layout: page
title: Lab 6 - Numeric and Date Functions
nav_exclude: true
---

## Lab 6: Designing & Debugging Functions for Data Mapping and File I/O

**Core Idea**: This lab emphasizes creating and debugging reusable functions for common data manipulation tasks, specifically mapping data with dictionaries and handling text files. This is a foundational skill for managing and processing biological data.

**Environmental Monitoring**: You have collected water quality data from a specific river segment inhabited by South Asian River Dolphins. This data includes measurements of key parameters recorded with timestamps. You also have information linking specific sensor IDs to their locations.

**Problem**: Design and implement reusable Python functions to:  
1.  Read and process structured environmental data (timestamps, toxin levels, turbidity) into a usable format.  
2.  Map sensor IDs to their geographical locations using dictionaries.  
3.  Write processed data or summary findings to a text file.  
You will also practice debugging these functions to ensure their reliability.  

### Worksheet:

1.  Import the `datetime` module.  

2.  Define the water quality data (initial raw data as provided):  
    ```python
    raw_water_data = [
        ("2025-04-05 08:00:00", 2.5, 150.2, "SENS001"),
        ("2025-04-05 12:00:00", 3.1, 165.8, "SENS002"),
        ("2025-04-06 09:30:00", 1.9, 140.5, "SENS001"),
        ("2025-04-06 15:00:00", 3.5, 170.1, "SENS003"),
        ("2025-04-07 10:00:00", 2.8, 160.0, "SENS002")
    ]
    ```

3.  Define a dictionary for sensor locations:
    ```python
    sensor_locations = {
        "SENS001": "Upstream Delta",
        "SENS002": "Mid-river Bend",
        "SENS003": "Downstream Estuary"
    }
    ```

4.  Design and Implement Reusable Functions:  

    a.  `process_water_data(raw_data, location_map)`:  
        - Purpose: Takes `raw_data` (list of tuples) and `location_map` (dictionary) as input.  
        - For each entry in `raw_data`, convert the timestamp string to a `datetime` object.  
        - Look up the sensor's location using `location_map`.  
        - Returns a list of dictionaries, where each dictionary represents a processed data point, e.g., `{'Timestamp': datetime_obj, 'Toxin': float, 'Turbidity': float, 'SensorID': str, 'Location': str}`.  
        - Example Usage: `processed_data = process_water_data(raw_water_data, sensor_locations)`  

    b.  `analyze_water_data(processed_data)`:  
        - Purpose: Takes the `processed_data` (list of dictionaries) as input.  
        - Calculates the total time duration between the first and last readings.  
        - Identifies the timestamp and value for the highest toxin level.  
        - Identifies the timestamp and value for the highest turbidity.  
        - Returns a dictionary containing these analysis results (e.g., `{'Duration': timedelta, 'MaxToxin': {'Timestamp': datetime_obj, 'Value': float}, ...}`).  
        - Example Usage: `analysis_results = analyze_water_data(processed_data)`  

    c.  `write_analysis_to_file(filepath, analysis_results)`:  
        - Purpose: Takes a `filepath` string and `analysis_results` dictionary as input.  
        - Writes the analysis findings to a text file in a human-readable format.  
        - Example Usage: `write_analysis_to_file("water_analysis_summary.txt", analysis_results)`  

5.  Integrate Functions for Workflow:
    - Call `process_water_data()` to prepare your data.  
    - Call `analyze_water_data()` with the processed data.  
    - Call `write_analysis_to_file()` to save the summary.  
    - Also, print the analysis results to the console.  

6.  Debugging Exercise:
    a.  Introduce deliberate bugs:  
        - In `process_water_data`, make an error in the `datetime.strptime` format string or handle the location lookup incorrectly (e.g., assume sensor ID always exists).  
        - In `analyze_water_data`, introduce an off-by-one error when finding max values, or a type error in time calculation.  
        - In `write_analysis_to_file`, try to write a non-string object directly to the file, or misformat the output.  
    b.  Identify the bug: Run your script and observe the errors or incorrect output.  
    c.  Use `print()` statements and `try-except` blocks for debugging: Strategically place `print()` statements to inspect variables. Use `try-except` blocks to gracefully handle potential errors (like `ValueError` for `strptime` or `KeyError` for dictionary lookups) and provide informative error messages.  
    d.  Fix the bug: Correct the errors in your functions.  
    e.  Verify the fix: Rerun the script to ensure all outputs are correct and no errors occur.  
