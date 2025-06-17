---
layout: page
title: Lab 13 - Introduction to Biopython (Sequences I/O)
nav_exclude: true
---

## Lab 13: Reading the Building Blocks - Introduction to Biopython (Sequences I/O)

**Genetic Analysis:** You’ve obtained DNA sequences of a candidate gene from both healthy and affected South Asian River Dolphins, stored in FASTA files. These sequences might reveal genetic variations associated with disease susceptibility or resistance.

**Problem:** Write a Python script using Biopython’s `SeqIO` module to read the DNA sequences from the FASTA files. Extract the sequence identifiers (Dolphin IDs) and the sequences themselves. Print the identifier and the first 30 nucleotides of each sequence for initial comparison.

### Worksheet:

1.  Install Biopython if you haven't already (`pip install biopython`).
2.  Create two FASTA files named `healthy_dolphin.fasta` and `affected_dolphin.fasta` with the following content:
    ```
    >SARD_Healthy01_GeneX
    ATGCGTAGCTAGCTAGCTAGCATCGATCGATCGGTCAGCTAGCT
    >SARD_Affected01_GeneX
    ATGCGTAGCTAGCTAGCTAGCGTCGATCGATCGGTCAGCTAGCT
    ```
3.  Write a Python script that imports the `SeqIO` module from Biopython.
4.  Use `SeqIO.parse()` to read the sequences from both FASTA files.
5.  Iterate through the records obtained from each file. For each record, print its `id` and the first 30 characters of its `seq`.