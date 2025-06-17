---
layout: page
title: Lab 11 - Statistical Concepts (Descriptive Statistics)
nav_exclude: true
---

## Lab 11: Describing the Affected Population - Statistical Concepts (Descriptive Statistics)

**Bacterial Load Analysis:** You have collected CFU counts from a larger sample of infected South Asian River Dolphins. You need to understand the distribution of the bacterial load in this population.

**Problem:** Write a Python script to calculate descriptive statistics (mean, median, standard deviation) for a list of CFU counts obtained from infected dolphins (excluding any ’None’ values). Use Python’s `statistics` module. Print these statistics with appropriate labels.

### Worksheet:

1.  Import the `statistics` module.
2.  Create a list of CFU counts from infected South Asian River Dolphins (some might be `None` if no sample was taken): `[1200, 3500, 900, 4800, None, 2100, 3000, None, 1500]`.
3.  Create a new list containing only the numerical CFU values (remove the `None` values).
4.  Calculate and print the mean CFU count using `statistics.mean()` on the filtered list.
5.  Calculate and print the median CFU count using `statistics.median()` on the filtered list.
6.  Calculate and print the standard deviation of the CFU counts using `statistics.stdev()` on the filtered list.