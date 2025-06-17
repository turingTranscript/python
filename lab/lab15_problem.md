---
layout: page
title: Lab 15 - Sequence Analysis (Alignment & Searching)
nav_exclude: true
---

## Lab 15: Comparing Genetic Variations - Sequence Analysis (Alignment & Searching)

**Identifying Mutations:** You need to compare the DNA sequences of the candidate gene from a healthy and an affected South Asian River Dolphin to pinpoint potential genetic variations (mutations) that might contribute to the disease.

**Problem:** Write a Python script using Biopython’s `pairwise2` module to perform a global alignment of the two sequences (from the FASTA files created in Lab 13). Visualize the alignment and identify any mismatches (potential single nucleotide polymorphisms - SNPs or other mutations).

### Worksheet:

1.  Import the `pairwise2` module from Biopython and the `Seq` object from `Bio.Seq`. Also import `SeqIO`.
2.  Write code to read the sequences from `healthy_dolphin.fasta` and `affected_dolphin.fasta` using `SeqIO.parse()` and extract the `Seq` objects.
3.  Use `pairwise2.align.globalms()` with appropriate scoring parameters (match score, mismatch score, gap open penalty, gap extend penalty) to perform a global alignment of the two sequences. Experiment with different scoring parameters to see their effect on the alignment.
4.  Iterate through the list of alignments returned by `pairwise2.align.globalms()` and print the aligned sequences (index 0 and 1 of each alignment).
5.  Visually inspect the alignments to identify any positions where the nucleotides differ between the healthy and affected dolphin sequences. Note the position and the specific nucleotide change(s). Discuss the potential significance of these variations in the context of the disease.## Lab 16: Building Evolutionary Relationships

**Phylogenetic Context:** To understand the evolutionary history of the candidate gene in South Asian River Dolphins and related cetacean species, you want to explore a phylogenetic tree that includes these species. This can provide insights into the conservation significance of the South Asian River Dolphin and the potential origins of the disease-related gene.

**Problem:** Write a Python script using Biopython’s `Phylo` module to read a phylogenetic tree (provided in Newick format) that includes the South Asian River Dolphin and visualize it. Identify the position of the South Asian River Dolphin within the tree and discuss its evolutionary relationships with other cetaceans.

### Worksheet:

1.  Install the `matplotlib` library for tree visualization (`pip install matplotlib`).
2.  Import the `Phylo` module from Biopython and `matplotlib.pyplot` as `plt`.
3.  Define a Newick format string representing a simple phylogenetic tree of relevant cetaceans:
    ```python
    tree_string = "((((Balaenoptera_musculus:0.1,Megaptera_novaeangliae:0.2):0.3,Physeter_macrocephalus:0.4):0.5,(Platanista_gangetica:0.6,Inia_geoffrensis:0.7):0.8):0.9);"
    ```
4.  Use `Phylo.read()` with the string as input and the format as "newick" to parse the tree.
5.  Use `Phylo.draw()` with the parsed tree to display it. Use `plt.show()` to show the plot.
6.  Analyze the resulting phylogenetic tree. Identify the South Asian River Dolphin (`Platanista_gangetica`) and its closest relatives within the tree. Discuss the implications of its phylogenetic position for understanding its unique biology and conservation status.
7.  (Optional, for a more advanced exercise) If time permits, explore how to read a phylogenetic tree from a file (e.g., in Newick format) instead of directly from a string.