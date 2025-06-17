---
layout: page
title: Lab 12 - Statistical Concepts (Hypothesis Testing Basics)
nav_exclude: true
---

## Lab 12: Testing a Hypothesis - Statistical Concepts (Hypothesis Testing Basics)

**Environmental Toxin and Bacterial Load:** Researchers hypothesize that higher levels of a specific environmental toxin (analyzed in Lab 3 and cleaned in Lab 10) might be associated with a higher bacterial load (CFU) in infected South Asian River Dolphins. You have paired data for a subset of dolphins where both toxin levels in their habitat and their CFU counts were measured. You will now perform an independent samples t-test to assess if there is a statistically significant difference in the average CFU counts between dolphins in high and low toxin environments.

**Problem:** Write a Python script that performs an independent samples t-test to compare the mean CFU counts of dolphins in areas with high and low toxin levels. You will use the `scipy.stats` module for this test.

### Worksheet:

1.  Import the `scipy.stats` module.
2.  Create a list of tuples, where each tuple contains the toxin level (in ppm) in a dolphin’s habitat and their corresponding CFU count:
    ```python
    dolphin_data_toxin_cfu = [
        (0.8, 1500),
        (1.2, 3200),
        (0.5, 900),
        (2.5, 4500),
        (0.9, 1800),
        (3.1, 5100),
        (1.1, 2500),
        (2.8, 3900),
        (2.2, 4100),
        (0.7, 1100),
        (1.3, 2800),
        (2.9, 4800)
    ]
    ```
3.  Define a threshold for "high" toxin level (e.g., $\geq 2.0$ ppm) and "low" toxin level (e.g., $< 1.5$ ppm).
4.  Formulate a null hypothesis ($H_0$) and an alternative hypothesis ($H_A$) for this investigation:
    * $H_0$: There is no significant difference in the mean bacterial load (CFU) between South Asian River Dolphins inhabiting areas with high and low levels of the specific toxin.
    * $H_A$: The mean bacterial load (CFU) is significantly higher in South Asian River Dolphins inhabiting areas with high levels of the specific toxin compared to those in areas with low levels of the toxin (one-tailed test).
5.  Create two empty lists: one to store CFU counts for dolphins in "low toxin" areas and another for "high toxin" areas, based on the defined thresholds.
6.  Iterate through the `dolphin_data_toxin_cfu` list. For each dolphin, based on their toxin level, append their CFU count to the appropriate list.
7.  Perform an independent samples t-test using `scipy.stats.ttest_ind()` on the two lists of CFU counts. Assume equal variances for simplicity (`equal_var=True`).
8.  Print the calculated t-statistic and the p-value.
9.  Define a significance level ($\alpha$), commonly 0.05.
10. Based on the p-value and the significance level, make a conclusion about whether to reject or fail to reject the null hypothesis. Explain your reasoning.