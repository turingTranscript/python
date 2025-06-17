---
layout: page
title: Lab 10 - Data Wrangling
nav_exclude: true
---

## Lab 10: Cleaning Environmental Readings - Data Wrangling

**Environmental Data Wrangling:** You have a larger dataset of water quality readings from various river segments. This data contains missing values (represented by ”NA”) and inconsistent units for a specific toxin (some in ppm, some in ppb).

**Problem:** Write a Python script to process a list of water quality readings (strings). Replace ”NA” values with a placeholder (e.g., ”0 ppm”). Convert all toxin readings to a consistent unit (parts per million - ppm, given that 1 ppm = 1000 ppb). Calculate the average level of that toxin across all valid readings.

### Worksheet:

1.  Create a list of water quality readings for a specific toxin: `['2.5 ppm', 'NA', '1500 ppb', '10 ppm', '500 ppb', 'NA']`.
2.  Create an empty list to store the cleaned and converted toxin levels (as floats in ppm).
3.  Iterate through the list of readings. For each reading:
    * If the reading is "NA", replace it with "0 ppm".
    * Check if the reading is in "ppm" or "ppb".
    * Convert the numerical value to ppm (if it's in ppb, divide by 1000).
    * Append the converted value (as a float) to the new list.
4.  Calculate and print the average toxin level from the cleaned list.