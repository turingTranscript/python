---
layout: page
title: Lab 6 - Numeric and Date Functions
nav_exclude: true
---

## Lab 6: Analyzing Temporal Data - Numeric and Date Functions

**Environmental Monitoring:** You have collected water quality data from a specific river segment inhabited by South Asian River Dolphins over several days, including measurements for a key toxin (analyzed in Lab 3) and turbidity, recorded with timestamps.

**Problem:** Write a Python script to store this data, including timestamps as strings. Use Python’s `datetime` module to convert these timestamps into `datetime` objects. Calculate the time difference between the first and last readings. Identify the date with the highest recorded toxin level and the date with the highest turbidity.

### Worksheet:

1.  Import the `datetime` module.
2.  Create a list of tuples, where each tuple contains a timestamp string ("YYYY-MM-DD HH:MM:SS"), toxin level (float), and turbidity (float):
    ```python
    water_data = [
    ("2025-04-05 08:00:00", 2.5, 150.2),
    ("2025-04-05 12:00:00", 3.1, 165.8),
    ("2025-04-06 09:30:00", 1.9, 140.5),
    ("2025-04-06 15:00:00", 3.5, 170.1)
    ]
    ```
3.  Convert the timestamp string in each tuple to a `datetime` object using `datetime.strptime()`.
4.  Calculate and print the total time duration between the first and the last recorded data point.
5.  Find and print the date and time when the toxin level was highest.
6.  Find and print the date and time when the turbidity was highest.