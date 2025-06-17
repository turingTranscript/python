---
layout: page
title: Lab 10 - Data Wrangling
nav_exclude: true
---

## Lab 10: Designing & Debugging Functions for NCBI Data Fetching & BLAST Analysis

**Core Idea:** This lab emphasizes developing and debugging reusable functions for advanced bioinformatics tasks: programmatically retrieving diverse biological data from NCBI databases using Biopython's `Entrez` module, and parsing/analyzing simulated BLAST output. Creating modular functions is essential for building robust and scalable bioinformatics workflows.

**Comparative Genomics:** You are investigating a set of candidate genes from the South Asian River Dolphin that are thought to be related to a specific immune pathway. To understand their function and evolutionary context, you need to:
1.  Fetch homologous protein sequences and their full annotations from NCBI for a related species.
2.  Analyze a local BLAST report to identify the most significant matches for your dolphin gene sequences against a reference database.

**Problem:** Design and implement reusable Python functions to:
1.  Retrieve protein sequences and detailed GenBank records from NCBI using a list of accession numbers or UIDs.
2.  Parse a simulated plain-text BLAST output file to extract key information about each hit.
3.  Filter and summarize the parsed BLAST results based on specific criteria (e.g., E-value, percent identity).
You will practice debugging these functions, paying close attention to network communication, data parsing, and handling diverse data structures.

### Worksheet:

1.  Install Biopython: If you haven't already, run `pip install biopython` in your terminal.  
2.  Import necessary modules: `from Bio import Entrez`, `from Bio import SeqIO`, `import os`.  
3.  Set your Entrez email:  
    ```python
    Entrez.email = "your.email@example.com" # Replace with your actual email
    ```
4.  Define a list of NCBI Protein Accession IDs (example IDs):  
    ```python
    protein_accessions = ["NP_000510.1", "NP_001153664.1", "NP_000042.1"]
    ```
5.  Create a simulated plain-text BLAST output file named `simulated_blast_output.txt`:
    *(This is a simplified, tab-separated format for easier parsing in this lab. Real BLAST outputs can be much more complex, often XML or custom delimited.)*  
    ```
    # Query ID  Subject ID  % Identity  Alignment Length    Mismatches  Gap Opens   Query Start Query End   Subject Start   Subject End E-value Bit Score
    SARD_GeneX_Q1   XP_0012345.1    98.5    150 2   0   1   150 10  159 1e-90   300
    SARD_GeneX_Q1   NP_987654.1 85.2    100 15  2   10  109 200 299 5e-10   150
    SARD_GeneY_Q2   NP_000510.1 99.0    200 1   0   1   200 1   200 1e-120  400
    SARD_GeneY_Q2   XP_0056789.1    70.1    80  20  5   50  129 500 579 0.01    50
    SARD_GeneZ_Q3   NP_000042.1 95.0    180 5   1   1   180 50  229 1e-80   250
    ```

6.  Design and Implement Reusable Functions:

    a.  `fetch_ncbi_records(id_list, db="protein", rettype="gb", retmode="text")`:
        * Purpose: Takes a list of NCBI `id_list` (accession numbers or UIDs), database name (`db`), return type (`rettype`), and return mode (`retmode`).
        * Uses `Entrez.efetch` to retrieve full records from NCBI.
        * Parses the handle using `SeqIO.parse` (if `db` is "nuccore" or "protein" and `rettype` is "fasta" or "gb") or `Entrez.read` for more complex XML data.
        * Returns a list of `SeqRecord` objects (for protein/nucleotide databases) or a list of parsed Python objects (for other databases/retmodes). Handle `IOError` or `URLError` for network issues.
        * Example Usage: `protein_records = fetch_ncbi_records(protein_accessions, db="protein", rettype="gb")`

    b.  `parse_simplified_blast_output(filepath)`:
        * Purpose: Takes the `filepath` to your `simulated_blast_output.txt`.
        * Reads the file, skips the header line (starting with `#`).
        * Parses each subsequent line, splitting by tab delimiter.
        * Extracts 'Query ID', 'Subject ID', '% Identity', 'E-value', and 'Bit Score'. Converts numerical values to floats.
        * Returns a list of dictionaries, where each dictionary represents one BLAST hit.
        * Example Usage: `blast_hits = parse_simplified_blast_output("simulated_blast_output.txt")`

    c.  `filter_blast_hits(blast_hits_list, e_value_threshold, identity_threshold)`:
        * Purpose: Takes a `blast_hits_list` (from `parse_simplified_blast_output`), an `e_value_threshold` (float), and an `identity_threshold` (float, percentage).
        * Filters the list to include only hits where E-value is less than or equal to the threshold AND % Identity is greater than or equal to the threshold.
        * Returns a new list of filtered hit dictionaries.
        * Example Usage: `significant_hits = filter_blast_hits(blast_hits, 1e-10, 90.0)`

    d.  `summarize_protein_records(protein_records)`:
        * Purpose: Takes a list of `SeqRecord` objects.
        * For each record, extracts and prints a summary including `ID`, `Description`, `Length`, and potentially a few features (if present in `record.features`).
        * Example Usage: `summarize_protein_records(protein_records)`

4.  Integrate Functions for Workflow:
    * Call `fetch_ncbi_records()` with `protein_accessions`.
    * Call `summarize_protein_records()` to print details of the fetched proteins.
    * Call `parse_simplified_blast_output()` with your `simulated_blast_output.txt`.
    * Call `filter_blast_hits()` on the parsed results with chosen thresholds (e.g., E-value $1e-5$, Identity $80.0$).
    * Print the filtered BLAST hits in a readable format.

5.  Debugging Exercise:

    a.  Introduce a deliberate bug:
        * In `fetch_ncbi_records`, use a wrong database name (e.g., "proteinX") or provide an invalid `rettype` or `retmode` combination that causes `SeqIO.parse` to fail or `Entrez.read` to return unexpected structure.
        * In `simulated_blast_output.txt`, introduce a line with missing columns or a non-numerical value where a number is expected (e.g., "NaN" for E-value).
        * In `parse_simplified_blast_output`, make an error in splitting the line or converting a string to a float, leading to a `ValueError` or `IndexError`.
        * In `filter_blast_hits`, reverse the comparison logic for E-value (e.g., `>` instead of `<=`).
        * Forget to handle potential `URLError` from `Entrez` if there's no internet connection.
    b.  Identify the bug: Run your script and observe `ValueError`, `IndexError`, `URLError`, or incorrect filtered results. Biopython's `SeqIO` and `Entrez` often provide informative error messages.
    c.  Use `print()` statements and `try-except` blocks for debugging:
        * For `Entrez` calls: Wrap `Entrez.efetch` in a `try-except URLError` to catch network issues. `print()` the raw `handle.read()` content before parsing if you suspect parsing issues.
        * For file parsing: `print()` each `line` before splitting it in `parse_simplified_blast_output`. `print()` the `parts` list after splitting. Use `try-except ValueError` around `float()` conversions.
        * For filtering: `print()` the values of E-value and % Identity for each hit before applying the filter to confirm your filtering logic is correct.
    d.  Fix the bug: Correct database/return type parameters, ensure robust parsing (e.g., `try-except` for type conversion), fix comparison logic, and add appropriate error handling for network requests.
    e.  Verify the fix: Rerun the script. Test with problematic inputs (e.g., a non-existent protein ID in `fetch_ncbi_records`, a malformed line in BLAST output) to ensure functions handle them gracefully or provide clear error messages.