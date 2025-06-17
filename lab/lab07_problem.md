---
layout: page
title: Lab 7 - Working with Data (Lists and Dictionaries)
nav_exclude: true
---

## Lab 7: Designing & Debugging Functions for Parsing Files and Initial Biopython Seq

**Core Idea:** This lab focuses on developing and debugging functions for parsing structured data from CSV/TSV files and introducing basic biological sequence manipulation using Biopython's `Seq` object. Modular functions are key for handling external data and specialized libraries.

**Biological Sequence Data:** You have received a file containing metadata about South Asian River Dolphin genetic samples, along with a separate list of very short DNA fragments (not from the file) that you need to represent and manipulate using Biopython.

**Problem:** Design and implement reusable Python functions to:  
1.  Parse data from a CSV/TSV file into a list of dictionaries.  
2.  Create and manipulate Biopython `Seq` objects for given DNA sequences.  
You will practice debugging these functions, paying attention to file parsing logic and Biopython object behavior.  

### Worksheet:

1.  Install Biopython: If you haven't already, run `pip install biopython` in your terminal.  
2.  Import necessary modules: `import csv` (or `import tsv` if you prefer TSV parsing) and `from Bio.Seq import Seq`.  
3.  Create a sample data file named `dolphin_samples.csv`:  
    ```csv
    SampleID,RiverSegment,CollectionDate,DNA_Quality,Notes
    SARD_DNA_001,RS01,2025-05-10,High,Healthy individual
    SARD_DNA_002,RS02,2025-05-11,Medium,Mild symptoms
    SARD_DNA_003,RS01,2025-05-12,Low,Suspected infection
    SARD_DNA_004,RS03,2025-05-10,High,Healthy individual
    ```

4.  Define a list of DNA fragments (for Biopython practice):  
    ```python
    dna_fragments_raw = ["ATGCATGC", "GCTAGCTA", "TTAACCGG"]
    ```

5.  Design and Implement Reusable Functions:  

    a.  `parse_sample_csv(filepath)`:  
        - Purpose: Takes a `filepath` string. Reads the CSV file, skips the header, and parses each row into a dictionary.  Converts numeric data (if any, e.g., 'DNA_Quality' if it were numerical) to appropriate types. Returns a list of dictionaries.  
        - Example Usage: `sample_data = parse_sample_csv("dolphin_samples.csv")`  

    b.  `create_biopython_seq_objects(dna_sequences)`:  
        - Purpose: Takes a list of raw DNA string sequences. For each string, creates a `Bio.Seq.Seq` object. Returns a list of these `Seq` objects.  
        - Example Usage: `seq_objects = create_biopython_seq_objects(dna_fragments_raw)`  

    c.  `analyze_seq_object(seq_obj)`:  
        - Purpose: Takes a single `Bio.Seq.Seq` object. Calculates and returns its length, its complement sequence, and its reverse complement sequence. Returns a dictionary of these results.  
        - Example Usage: `analysis = analyze_seq_object(seq_objects[0])`  

6.  Integrate Functions for Workflow:  
    - Call `parse_sample_csv()` to load your sample metadata. Print the parsed data.  
    - Call `create_biopython_seq_objects()` to get Biopython `Seq` objects.  
    - Loop through the `seq_objects`. For each object, call `analyze_seq_object()` and print the detailed analysis (length, complement, reverse complement).  

7.  Debugging Exercise:  
    a.  Introduce deliberate bugs:  
        - In `parse_sample_csv`, misspell a dictionary key, or forget to handle a blank line/malformed row.  
        - In `create_biopython_seq_objects`, try to pass a non-string or non-DNA character (e.g., "ATGCX") to `Seq()`.  
        - In `analyze_seq_object`, try to call a method that doesn't exist or incorrectly apply a `Seq` method.  
    b.  Identify the bug: Run your script and observe the errors (e.g., `KeyError`, `ValueError` from Biopython, `AttributeError`).  
    c.  Use `print()` statements and `try-except` blocks: Trace the data as it's parsed and when `Seq` objects are created/manipulated. Wrap potentially problematic Biopython calls in `try-except` blocks.  
    d.  Fix the bug: Correct the errors in your functions.  
    e.  Verify the fix: Rerun the script to confirm correct execution and output.  