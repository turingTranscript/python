---
layout: page
title: Lab 16 - Building Evolutionary Relationships
nav_exclude: true
---

## Lab 16: Building Evolutionary Relationships

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