---
layout: page
title: Lab 14 - Database Access with Biopython
nav_exclude: true
---

## Lab 14: Exploring Online Databases - Database Access with Biopython

**Gene Annotation:** You need to retrieve annotation information for the candidate gene (GeneX) from an online database like NCBI’s Entrez to understand its potential function and involvement in disease processes.

**Problem:** Write a Python script using Biopython’s `Entrez` module to search for and retrieve information (e.g., gene name, description, associated pathways) for the candidate gene based on a search term related to South Asian River Dolphins and the gene name. Print the retrieved annotation details.

### Worksheet:

1.  Import the `Entrez` module from Biopython.
2.  Set your email address for Entrez queries: `Entrez.email = "your_email@example.com"`.
3.  Use `Entrez.esearch()` to search for the gene with the term "South Asian River Dolphin GeneX". Specify the database as "gene" and the number of results to 1.
4.  Parse the search results using `Entrez.read()` to get the Gene ID.
5.  Use `Entrez.esummary()` with the retrieved Gene ID to fetch summary information. Parse the summary using `Entrez.read()`.
6.  Extract and print the gene name (`Item['Name']`), the gene description (`Item['Description']`), and potentially other relevant information like associated keywords or pathways if available in the summary.