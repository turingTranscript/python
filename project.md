---
layout: page
title: Project
nav_order: 5
description: Specifications for the final project for Data 200.
---

# Project

### Group Project

| Project # | Project Title | Description |
| :-------- | :------------ | :---------- |
| 1 | **Genome Annotation and Feature Extraction** | Develop a Python script to parse a GenBank or GFF file, extract specific features (e.g., genes, CDS, regulatory elements), and generate a summary report or a simplified annotation file. Focus on parsing and information retrieval. |
| 2 | **Comparative Genomics of Related Species** | Select a gene or a set of homologous genes from several related species. Use Biopython to fetch sequences from NCBI (via `Bio.Entrez`), perform multiple sequence alignment, and analyze conserved regions or evolutionary divergence. |
| 3 | **Variant Calling and Basic SNP Analysis** | Process a VCF (Variant Call Format) file to extract single-nucleotide polymorphisms (SNPs). Filter SNPs based on simple criteria (e.g., presence/absence, basic allele frequency) and report basic counts or properties. |
| 4 | **Phylogenetic Tree Reconstruction & Visualization** | Given a set of homologous sequences, construct a simple phylogenetic tree using a chosen method (e.g., Neighbor-Joining via `Bio.Phylo`). Visualize the tree structure and interpret basic relationships. |
| 5 | **Protein Structure Analysis & Basic Metrics** | Fetch protein structures from the Protein Data Bank (PDB) using `Bio.PDB`. Analyze simple structural features like length, number of chains, or calculate distances between specific residues. |
| 6 | **Gene Expression Data Summary with Pandas** | Analyze a gene expression dataset (e.g., simple counts or normalized values). Use Pandas for data loading, basic cleaning, and manipulation (e.g., calculating average expression, identifying top expressed genes). |
| 7 | **Primer Design and Validation** | Develop a Python script that takes a target DNA sequence and designs PCR primers based on specified criteria (e.g., length, GC content, basic melting temperature calculation). |
| 8 | **Automated Sequence Download and Formatting** | Create a script that can query online biological databases (like NCBI) using `Bio.Entrez`, download specified sequences, and then reformat them into a desired local file format (e.g., from GenBank to FASTA). |
| 9 | **Codon Usage Analysis** | Analyze the codon usage of a specific gene or a set of genes from an organism. Develop a script to count the frequency of each codon and present it in a clear format (e.g., table or dictionary). Groups could compare codon usage between genes or organisms. |
| 10 | **Open Reading Frame (ORF) Finder** | Develop a Python script to identify potential Open Reading Frames (ORFs) within a given DNA sequence. This involves finding start codons, stop codons, and calculating the length of potential ORFs. |
| 11 | **Protein Domains and Motif Discovery** | Given a set of protein sequences, use string searching methods and regular expressions (`re` module) to identify occurrences of specific known protein domains or short motifs. |
| 12 | **Sequence Quality Control Simulation** | Simulate basic quality control steps for DNA sequencing reads. Develop a script that processes a file of short reads and performs tasks like trimming sequences to a fixed length, removing reads below a certain quality threshold (simplified based on character values), or removing adapter sequences. |