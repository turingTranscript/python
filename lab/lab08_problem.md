---
layout: page
title: Lab 8 - Input/Output and File Handling
nav_exclude: true
---

## Lab 8: Designing & Debugging Functions for In-Silico Sequence Transformations and SeqRecord

**Core Idea:** This lab focuses on creating and debugging functions that perform common in-silico (computer-based) transformations on biological sequences, leveraging Biopython's `SeqRecord` object for richer data representation. Reusable functions make these operations efficient and less error-prone.  

**Gene Fragment Analysis:** You've identified specific gene fragments from South Asian River Dolphins that are hypothesized to play a role in their immune response. You need to simulate common lab procedures like transcription and translation, and store these sequences with associated metadata.  

**Problem:** Design and implement reusable Python functions to:  
1.  Create Biopython `SeqRecord` objects from sequence strings and associated metadata.  
2.  Perform in-silico transcription and translation on DNA `SeqRecord` objects.  
3.  Extract specific features or sub-sequences from `SeqRecord` objects.  
You will extensively debug these functions, especially focusing on correct Biopython usage and handling edge cases.  

### Worksheet:

1.  Import necessary modules: `from Bio.Seq import Seq`, `from Bio.SeqRecord import SeqRecord`, `from Bio.Alphabet import IUPAC` (though `IUPAC` is largely deprecated, it's good to mention for context in older Biopython code). For modern Biopython, often just `from Bio.Seq import Seq` is enough, and `SeqRecord` can infer alphabet.  

2.  Define sample DNA gene fragments with metadata:  
    ```python
    gene_data = [
        {"id": "Gene_Immune_001", "name": "Immune_Response_GeneA",
         "sequence": "ATGGCCAAGATGGCCGCATACTAGG"}, # Start codon, some amino acids, stop codon
        {"id": "Gene_Stress_002", "name": "Stress_Pathway_GeneB",
         "sequence": "ATGTCGTACGTAGCTAG"}, # Partial sequence, might not have stop
        {"id": "Gene_Repair_003", "name": "DNA_Repair_EnzymeC",
         "sequence": "CTAGGATGCCAGTAGCCGA"} # Not starting with ATG
    ]
    ```

3.  Design and Implement Reusable Functions:  

    a.  `create_seq_record(seq_id, seq_name, dna_sequence)`:  
        - Purpose: Takes an `id`, `name`, and `dna_sequence` string. Creates and returns a `Bio.SeqRecord.SeqRecord` object with the given ID, name, and a `Seq` object for the DNA sequence.  
        - Example Usage: `record1 = create_seq_record("Gene_Immune_001", "Immune_Response_GeneA", "ATGGCCAAG...")`  

    b.  `transcribe_and_translate_record(seq_record)`:  
        - Purpose: Takes a `SeqRecord` object (containing DNA sequence).  
        - Performs transcription to get the RNA sequence.  
        - Performs translation to get the amino acid sequence. Handle cases where translation might be partial or result in an error (e.g., non-multiples of 3, stop codons in the middle, or not starting with ATG).  
        - Returns a dictionary containing the original `SeqRecord`, the RNA `Seq` object, and the Protein `Seq` object (or an error message if translation fails).  
        - Example Usage: `processed_gene = transcribe_and_translate_record(record1)`  

    c.  `extract_subsequence(seq_record, start, end)`:  
        - Purpose: Takes a `SeqRecord` object, a `start` index (0-based), and an `end` index.  
        - Extracts and returns a new `SeqRecord` representing the subsequence. Ensure robust error handling for invalid start/end indices.  
        - Example Usage: `sub_record = extract_subsequence(record1, 3, 15)`  

4.  Integrate Functions for Workflow:  
    - Loop through `gene_data`. For each entry, call `create_seq_record()` to get a `SeqRecord`.  
    - For each created `SeqRecord`, call `transcribe_and_translate_record()` and print the original DNA, RNA, and protein sequences. Comment on any partial translations or issues.  
    - Demonstrate `extract_subsequence()` on one of your `SeqRecord` objects and print the extracted subsequence.  

5.  Debugging Exercise:
    a.  Introduce deliberate bugs:
        - In `create_seq_record`, misassign the `id` or `name` or pass an invalid sequence type.  
        - In `transcribe_and_translate_record`, forget to handle sequences not starting with 'ATG' for translation, or try to translate a sequence that's not a multiple of three without `Bio.Seq.translate(..., to_stop=True)`.  
        - In `extract_subsequence`, use incorrect slicing, or don't validate `start` and `end` indices against the sequence length, leading to `IndexError`.  
    b.  Identify the bug: Run your script and observe the Biopython-specific errors (`TranslationError`, `AlphabetMismatchError`, `IndexError`) or incorrect outputs.  
    c.  Use `print()` statements and Biopython's error messages: Biopython often provides very descriptive error messages. Use these, along with `print()` statements, to pinpoint the issue.  
    d.  Fix the bug: Correct the logic or Biopython function calls.  
    e.  Verify the fix: Rerun the script to ensure all operations are correct and robust.  


