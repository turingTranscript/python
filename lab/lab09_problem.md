---
layout: page
title: Lab 9 - Exploratory Data Analysis (EDA) Basics
nav_exclude: true
---


## Lab 9: Designing & Debugging Functions for Biological Sequence File Handling with SeqIO and Entrez

**Core Idea:** This lab focuses on developing and debugging functions for efficient handling of standard biological sequence file formats (like FASTA) using Biopython's `SeqIO` module and making basic queries to NCBI databases using `Entrez`. Functions are essential for scalable bioinformatics workflows.  

**Public Sequence Data:** You need to retrieve known gene sequences from public databases (NCBI) for comparative analysis with your dolphin samples. You also need to manage large collections of sequences from local files.  

**Problem:** Design and implement reusable Python functions to:  
1.  Read and parse sequences from a FASTA file into `SeqRecord` objects using `SeqIO`.  
2.  Write `SeqRecord` objects to a new FASTA file.  
3.  Perform a basic query to the NCBI Nucleotide database using `Entrez` to retrieve sequence data.  
You will debug these functions, paying close attention to file format issues and network communication with `Entrez`.  

### Worksheet:

1.  Install Biopython: Ensure `pip install biopython` is done.  
2.  Import necessary modules: `from Bio import SeqIO`, `from Bio import Entrez`.  
3.  Create a sample FASTA file named `dolphin_genes.fasta`:  
    ```fasta
    >GeneA_SARD_ImmuneSeq | South Asian River Dolphin Immune Gene Fragment
    ATGCGTAGCTAGCTAGCTACGTAGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCTACGTAGCTAGCTAGC
    >GeneB_SARD_StressResp | South Asian River Dolphin Stress Response Gene
    GCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGCATGC
    >GeneC_SARD_Unknwn | Uncharacterized Fragment
    TACGTACGTAGCTAGCTAGCTAGCTACGTAGCTAGCTACGTAGCTACGTAGCTAGCTAGCTAGCTAGC
    ```
4.  Set your Entrez email: This is crucial for NCBI access. Replace with your actual email.  
    ```python
    Entrez.email = "your.email@example.com"
    ```

5.  Design and Implement Reusable Functions:  

    a.  `read_fasta_file(filepath)`:  
        - Purpose: Takes a `filepath` string. Reads the FASTA file using `SeqIO.parse()` and returns a list of `SeqRecord` objects. Handle `FileNotFoundError`.  
        - Example Usage: `records = read_fasta_file("dolphin_genes.fasta")`  

    b.  `write_records_to_fasta(filepath, records)`:  
        - Purpose: Takes a `filepath` string and a list of `SeqRecord` objects. Writes these records to a new FASTA file using `SeqIO.write()`. Overwrites if the file exists.  
        - Example Usage: `write_records_to_fasta("filtered_genes.fasta", some_records)`  

    c.  `query_ncbi_nucleotide(term, retmax=10)`:  
        - Purpose: Takes a `search_term` (string) and optional `retmax` (integer) for the number of results.  
        - Uses `Entrez.esearch()` to find IDs and `Entrez.efetch()` to retrieve full `SeqRecord` objects from the NCBI Nucleotide database.  
        - Returns a list of `SeqRecord` objects retrieved from NCBI. Handle potential network errors or no results found.
        - Example Usage: `ncbi_records = query_ncbi_nucleotide("Hox gene human", retmax=3)`  

6.  Integrate Functions for Workflow:
    - Call `read_fasta_file()` to load your local `dolphin_genes.fasta`. Print a summary (ID, description, length) of each loaded record.  
    - Demonstrate writing: Select a subset of records (e.g., the first two) and call `write_records_to_fasta()` to save them to a new file (e.g., `selected_dolphin_genes.fasta`). Verify the file creation.  
    - Perform an Entrez query: Call `query_ncbi_nucleotide()` with a relevant term (e.g., "dolphinus orcinus cytochrome b" or "Cetacea mitochondrial DNA"). Loop through the returned `SeqRecord` objects and print their IDs, descriptions, and lengths.  

7.  Debugging Exercise:  
    a.  Introduce deliberate bugs:  
        - In `read_fasta_file`, provide an incorrect file path or a malformed FASTA entry (e.g., missing `>`).  
        - In `write_records_to_fasta`, provide a list that contains non-`SeqRecord` objects.  
        - In `query_ncbi_nucleotide`, forget to set `Entrez.email`, use an invalid search term, or try to access an attribute on `handle` before `Entrez.read()` or `SeqIO.read()/parse()`.  
        - Simulate a network issue (harder to do deliberately, but consider what `try-except` for network errors like `URLError` would look like).  
    b.  Identify the bug: Run your script and observe `FileNotFoundError`, `ValueError` (from `SeqIO`), `urllib.error.URLError` (for network issues), or `AttributeError`.  
    c.  Use `print()` statements and `try-except` blocks: Trace file operations, check the type of objects being processed, and wrap network calls in `try-except` for robustness.  
    d.  Fix the bug: Correct file paths, data types, or Entrez/SeqIO usage.  
    e.  Verify the fix: Rerun the script to confirm successful file operations and NCBI queries.  
