---
layout: page
title: Lab 5 - Working with Strings
nav_exclude: true
---

## Lab 5: Unraveling Sequence Fragments - Working with Strings

**Initial Genetic Clues:** You’ve obtained short, potentially significant DNA sequence fragments from both healthy and diseased South Asian River Dolphins. These fragments might contain genetic markers associated with disease susceptibility or resistance.

**Problem:** Write a Python script that stores a list of these DNA sequence fragments as strings. For each fragment, calculate its length, count the occurrences of specific nucleotides (e.g., ’A’, ’G’), and check if it contains a specific short motif (e.g., ”CTA”) potentially linked to an immune response gene. Print a basic analysis of each fragment.

### Worksheet:

1.  Create a list of DNA sequence fragments from South Asian River Dolphins: `["ATGCGTAGC", "CGTAATGC", "GCTAGCTA", "TACGATCG"]`.
2.  Use a `for` loop to iterate through the list. For each fragment:
    * Print the fragment.
    * Calculate and print the length of the fragment.
    * Count and print the number of 'T' nucleotides in the fragment.
    * Check if the fragment contains the motif "CTA". Print "Motif found" or "Motif not found".