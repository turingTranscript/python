---
layout: page
title: Lab 8 - Input/Output and File Handling
nav_exclude: true
---

## Lab 8: Handling External Reports - Input/Output and File Handling

**Water Quality Reports:** You receive water quality reports for different river segments inhabited by South Asian River Dolphins stored in a CSV (Comma Separated Values) file. Each line of the file contains information separated by commas (e.g., SegmentID,Date,Ammonia_Level,Nitrite_Level,Pesticides_Level).

**Problem:** Write a Python script to read data from this CSV file. Parse each line to extract the SegmentID, Date, and the levels of Ammonia, Nitrite and Pesticides. Store this information in a list of dictionaries. Print the extracted information in a structured format.

### Worksheet:

1.  Create a text file named `water_reports.csv` with the following content:
    ```csv
    SegmentID,Date,Ammonia Level (ppm),Nitrite Level (ppm),Pesticides Level (ppm)
    RS01,2025-04-05,2.3,0.8,1.4
    RS02,2025-04-05,3.1,1.2,4.2
    RS01,2025-04-06,2.1,0.9,0.5
    RS03,2025-04-06,1.5,0.5,1.9
    ```
2.  Write a Python script to open and read the `water_reports.csv` file.
3.  Skip the header row.
4.  Iterate through each subsequent line of the file. Split each line by the comma delimiter to get the SegmentID, Date, Ammonia_Level, Nitrite_Level and Pesticides_Level.
5.  Store this information as a dictionary (keys: 'SegmentID', 'Date', 'Ammonia_Level', 'Nitrite_Level', 'Pesticides_Level') in a list. Ensure that the toxin levels are stored as floating-point numbers.
6.  Print the list of dictionaries in a readable format.