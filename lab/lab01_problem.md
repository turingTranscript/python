---
layout: page
title: Lab 1 – Introduction to Python
nav_exclude: true
---

## Lab 1: Cracking the Code - Introduction to Python

**The Sample Tag:** A batch of potentially infected/contaminated River Dolphin tissue samples has been received, and each vial has a specific tag embedded within the processing notes. This tag, containing the sample's unique identifier, is formatted in a consistent way as shown in the image.

**Problem:** Write a Python script that:
1. Prints a welcome message to the user, introducing the "Secrets in the Sequence" challenge.
2. Stores the following encoded sample note as a string variable:

```python
encoded_note = 
"""
---BEGIN_SAMPLE_NOTE---
Contamination Assessment Batch #7
Key Sample Identifier:  [CTT_TISSUE_A3]
Proceed with caution during analysis.
---END_SAMPLE_NOTE---
"""
```

3. Prints the entire encoded message to the console.
4. Prints only the line containing the "Key Sample Identifier", extracting it by finding the relevant substring.
5. Prints a formatted output stating: "The crucial River Dolphin tissue sample ID is: [CTT_TISSUE_A3]".

**Biological Relevance:** Tracking potentially infected tissue samples with unique identifiers is crucial for preventing cross-contamination and ensuring accurate analysis.

**Goal:** You will learn to write and run basic Python scripts, understand syntax, use the `print()` function, store strings in variables, and perform simple string manipulation for output.

**Problem:** Write a Python script to print a welcome message, store the fragmented message as multiple string variables, concatenate specific fragments to form a coherent sentence about the disease, and print key information with clear formatting.

### Worksheet:
1. Write a Python script that starts by printing: `"Welcome to the Secrets in the Sequence Challenge!"`.
2. Store the following fragments as separate string variables: `"Initial report:"`, `"Disease outbreak"`, `"River Dolphins"`, `"alarming rate."`.
3. Concatenate the variables to form the sentence: `"Initial report: Disease outbreak in River Dolphins at an alarming rate."`. Print this sentence.
4. Extract the phrase `"River Dolphins"` from one of your variables and print it along with the message: `"The affected species are:"` followed by the extracted phrase.
```