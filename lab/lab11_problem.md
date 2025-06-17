---
layout: page
title: Lab 11 - Statistical Concepts (Descriptive Statistics)
nav_exclude: true
---

## Lab 11: Designing & Debugging Functions for Sequence Alignments & Pattern Matching with Regex

**Core Idea:** This lab focuses on developing and debugging reusable functions that perform fundamental bioinformatics tasks: sequence alignment using Biopython's `pairwise2` module and pattern matching with Python's regular expressions (`re` module). Modular functions are essential for building complex sequence analysis pipelines.

**Genetic Variations and Motifs:** You have obtained several short DNA sequences from South Asian River Dolphins, some potentially representing gene fragments or regulatory regions. You need to identify specific sequence motifs and quantify similarities between sequences.

**Problem:** Design and implement reusable Python functions to:
1.  Find all occurrences of a specific DNA motif within a sequence using regular expressions.
2.  Perform global and local sequence alignments between pairs of DNA sequences using Biopython.
You will practice debugging these functions, paying close attention to regex syntax, alignment parameters, and interpreting results.

### Worksheet:

1.  Import necessary modules: `import re`, `from Bio import pairwise2`, `from Bio.Seq import Seq`.
2.  Define sample DNA sequences:
    ```python
    sequence_A = "ATGCGTACGTACGTAGCTAGCTAGC"
    sequence_B = "ATACGTACGTAGTCTAGCTAG"
    sequence_C = "GCGTACGTACGTAGCTAGCAGCGTAGCT"
    ```
3.  Define a target motif: `target_motif = "GTACGT"`

4.  Design and Implement Reusable Functions:

    a.  `find_motif_occurrences(dna_sequence, motif_pattern)`:
        * Purpose: Takes a `dna_sequence` string and a `motif_pattern` string (which can be a regex).
        * Uses `re.findall()` to find all non-overlapping occurrences of the `motif_pattern` in the `dna_sequence`.
        * Returns a list of all found matches. If no matches, returns an empty list.
        * Example Usage: `matches = find_motif_occurrences(sequence_A, "G(T|C)ACGT")`

    b.  `perform_global_alignment(seq1_str, seq2_str, match=1, mismatch=-1, gap_open=-2, gap_extend=-0.5)`:
        * Purpose: Takes two DNA sequence strings (`seq1_str`, `seq2_str`) and optional scoring parameters.
        * Converts strings to `Bio.Seq.Seq` objects.
        * Performs a global alignment using `pairwise2.align.globalxx` (or `globalms` for custom scoring).
        * Returns the list of alignment tuples from `pairwise2.align`.
        * Example Usage: `global_aligns = perform_global_alignment(sequence_A, sequence_B)`

    c.  `perform_local_alignment(seq1_str, seq2_str, match=1, mismatch=-1, gap_open=-2, gap_extend=-0.5)`:
        * Purpose: Takes two DNA sequence strings and optional scoring parameters.
        * Converts strings to `Bio.Seq.Seq` objects.
        * Performs a local alignment using `pairwise2.align.localxx` (or `localms`).
        * Returns the list of alignment tuples.
        * Example Usage: `local_aligns = perform_local_alignment(sequence_A, sequence_C)`

    d.  `print_formatted_alignments(alignments)`:
        * Purpose: Takes the list of alignment tuples returned by `pairwise2.align`.
        * Iterates through them and uses `pairwise2.format_alignment` to print each alignment in a human-readable format.
        * Example Usage: `print_formatted_alignments(global_aligns)`

5.  Integrate Functions for Workflow:
    * Use `find_motif_occurrences()` to search for `target_motif` in `sequence_A` and `sequence_C`. Print the results.
    * Perform a global alignment between `sequence_A` and `sequence_B` using `perform_global_alignment()`. Print the result using `print_formatted_alignments()`.
    * Perform a local alignment between `sequence_A` and `sequence_C` using `perform_local_alignment()`. Print the result using `print_formatted_alignments()`.

6.  Debugging Exercise:

    a.  Introduce a deliberate bug:
        * In `find_motif_occurrences`, use a regex pattern that has a syntax error (e.g., `"[A-Z` without closing bracket) or an unintended match (e.g., using `.` where `\w` is needed).
        * In `perform_global_alignment` or `perform_local_alignment`, pass non-string arguments for sequences or incorrect numerical types for scoring parameters.
        * Assume `pairwise2.align` always returns a single alignment and try to index `alignments[0]` without checking if the list is empty.
    b.  Identify the bug: Run your script and observe `re.error` for regex syntax issues, `TypeError` for incorrect argument types, or `IndexError` if trying to access an empty alignment list.
    c.  Use `print()` statements and `try-except` blocks for debugging:
        * `print()` the `motif_pattern` being used in `re.findall`.
        * `print()` the sequences and parameters passed to `pairwise2` functions.
        * Use `try-except re.error as e:` for regex compilation.
        * Check `if alignments:` before attempting to format them.
    d.  Fix the bug: Correct regex patterns, ensure proper argument types, and handle cases where no alignments are found.
    e.  Verify the fix: Run the script again with varied inputs (e.g., sequences with no motif matches, identical sequences, very different sequences) to confirm correct behavior.



