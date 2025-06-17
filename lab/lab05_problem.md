---
layout: page
title: Lab 5 - Working with Strings
nav_exclude: true
---

## Lab 5: Unraveling Sequence Fragments - Working with Strings

**Core Idea:** In this lab, you will learn to design, implement, and debug reusable functions to perform common operations on DNA sequence fragments. This approach promotes code modularity, readability, and reduces redundancy, making your scripts more efficient and easier to maintain.

**Initial Genetic Clues:** You’ve obtained short, potentially significant DNA sequence fragments from both healthy and diseased South Asian River Dolphins. These fragments might contain genetic markers associated with disease susceptibility or resistance.

**Problem:** Design and implement a set of reusable Python functions to analyze a list of DNA sequence fragments. For each fragment, you will use these functions to calculate its length, count the occurrences of specific nucleotides, and check for the presence of a specific short motif. You will then demonstrate how to debug these functions effectively.

### Worksheet:

1.  **Define a list of DNA sequence fragments:**
    `dna_fragments = ["ATGCGTAGC", "CGTAATGC", "GCTAGCTA", "TACGATCG"]`

2.  **Design and Implement Reusable Functions:**

    a.  **`get_sequence_length(sequence)`:**  
        - **Purpose:** Takes a DNA sequence (string) as input and returns its length.  
        - **Example Usage:** `length = get_sequence_length("ATGC")` should return `4`.  

    b.  **`count_nucleotide(sequence, nucleotide)`:**  
        - **Purpose:** Takes a DNA sequence (string) and a single nucleotide (string, e.g., 'A', 'T', 'G', 'C') as input. It returns the count of that specific nucleotide within the sequence.  
        - **Example Usage:** `t_count = count_nucleotide("ATGCAT", 'T')` should return `2`.  

    c.  **`check_motif_presence(sequence, motif)`:**  
        - **Purpose:** Takes a DNA sequence (string) and a motif (string, e.g., "CTA") as input. It returns `True` if the motif is found within the sequence, `False` otherwise.  
        - **Example Usage:** `cta_present = check_motif_presence("GCTAGCTA", "CTA")` should return `True`.  

3.  **Integrate Functions into a Loop for Analysis:**
    - Use a `for` loop to iterate through the `dna_fragments` list.  
    - Inside the loop, for each fragment:  
        - Print the fragment.  
        - Call `get_sequence_length()` to get and print the length of the fragment.  
        - Call `count_nucleotide()` to count and print the number of 'T' nucleotides in the fragment.  
        - Call `check_motif_presence()` to check if the fragment contains the motif "CTA". Print "Motif found" or "Motif not found" based on the function's return value.  

4.  **Debugging Exercise:**

    a.  **Introduce a deliberate bug:** Modify one of your functions (e.g., `count_nucleotide`) so it produces an incorrect result (e.g., off-by-one error, case sensitivity issue if not handled).  
    b.  **Identify the bug:** Run your script and observe the incorrect output.  
    c.  **Use `print()` statements for debugging:** Add `print()` statements within your function to inspect the values of variables at different stages of execution. For example, in `count_nucleotide`, you might print the `sequence`, `nucleotide`, and the `current_count` inside the loop.  
    d.  **Fix the bug:** Correct the error in your function.  
    e.  **Verify the fix:** Run the script again to confirm that the output is now correct.  