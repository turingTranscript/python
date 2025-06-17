---
layout: page
title: Lab 7 - Working with Data (Lists and Dictionaries)
nav_exclude: true
---


## Lab 7: Organizing Research Notes - Working with Data (Lists and Dictionaries)

**Dolphin Health Assessment:** Researchers have recorded observations about individual South Asian River Dolphins from different river segments, including their ID, observed symptoms, and the estimated bacterial load (CFU) if a sample was collected. This data is currently unstructured.

**Problem:** Write a Python script to represent this data using a list of dictionaries, where each dictionary corresponds to a dolphin and contains keys like ’DolphinID’, ’Symptoms’, ’SegmentID’, and ’CFU’. Write code to access and print specific information for a given DolphinID. Calculate and print the average CFU count for dolphins from a specific river segment (if CFU data is available for multiple dolphins in that segment).

### Worksheet:

1.  Create a list of dictionaries representing South Asian River Dolphin health data:
    ```python
    dolphin_data = [
    {'DolphinID': 'SARD001', 'Symptoms': ['lethargy'], 'SegmentID': 'RS01', 'CFU': 1200},
    {'DolphinID': 'SARD002', 'Symptoms': ['skin lesions', 'lethargy'], 'SegmentID': 'RS02', 'CFU': 3500},
    {'DolphinID': 'SARD003', 'Symptoms': [], 'SegmentID': 'RS01', 'CFU': 900},
    {'DolphinID': 'SARD004', 'Symptoms': ['respiratory distress'], 'SegmentID': 'RS02', 'CFU': 4800},
    {'DolphinID': 'SARD005', 'Symptoms': ['lethargy'], 'SegmentID': 'RS03', 'CFU': None}
    ]
    ```
2.  Prompt the user to enter a DolphinID. Search the list for the dictionary with that ID and print its 'Symptoms' and 'SegmentID'.
3.  Prompt the user to enter a SegmentID. Iterate through the `dolphin_data` list and calculate the average CFU count for all dolphins from that segment where 'CFU' is not `None`. Print the average CFU for the specified segment.