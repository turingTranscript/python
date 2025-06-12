---
layout: page
title: Lab 2 – Variables, Input & Basic Data Types
nav_exclude: true
---

## Lab 2: Gathering Initial Evidence - Variables, Input & Basic Data Types

**The Infected River Dolphin Profile:** In the early stages of investigating the South Asian River Dolphin disease, establishing a baseline understanding of the affected population is critical. Collecting fundamental data points will help identify potential patterns and risk factors. We must determine the average age of affected dolphins, as age can influence disease susceptibility due to varying immune system strength and potential for toxin accumulation. Understanding the typical diet (categorical) of these dolphins is also crucial, as nutritional deficiencies, exposure to toxins through prey, or even pathogen transmission via diet could play a role. Finally, quantifying the estimated bacterial load (CFU) from infected dolphins will directly indicate the presence and severity of bacterial infections, a potential primary or secondary factor in the observed illness. Gathering this initial information requires specific methodologies. Age estimation might involve analyzing teeth wear or growth layers. Diet can be assessed through stomach content or fecal analysis, behavioral observation, or local ecological knowledge. Bacterial load necessitates laboratory analysis of biological samples to quantify viable bacteria. The rationale behind collecting each data type lies in its potential to reveal key aspects of the disease. Age can highlight vulnerable life stages, diet can expose links to environmental toxins or pathogens, and bacterial load can confirm and quantify infections. By systematically collecting and analyzing the average age, typical diet, and bacterial load of affected South Asian River Dolphins, we can begin to characterize the disease and identify potential contributing factors. This baseline data will serve as a foundation for further investigation into the underlying causes and potential solutions, allowing us to move towards a more comprehensive understanding of this threat to an endangered species.

**Problem:** Write a Python script to prompt the user for this information using the `input()` function. Store the data in appropriate variable types (integer, string, float). Perform a simple calculation (e.g., estimate the total bacterial count based on CFU/ml and a sample volume). Print a well-formatted summary of the infected river dolphin profile.

```math
N_{total} = C_{CFU/ml} \times V_{sample}
```

$N_{total}$ represents the Total Bacterial Count.
$C_{CFU/ml}$ represents the Bacterial Concentration in Colony Forming Units per milliliter.
$V_{sample}$ represents the Sample Volume in milliliters.

### Worksheet:

1.  Write a Python script that prompts the user to enter the average age of the affected river dolphins. Store this as an integer.
2.  Prompt the user to enter the typical diet of the river dolphins (e.g., ”small fish”, ”crustaceans”). Store this as a string.
3.  Prompt the user to enter the estimated bacterial concentration in a sample from an infected dolphin (in CFU/ml). Store this as a float.
4.  Prompt the user to enter the volume of the sample (in ml). Store this as a float.
5.  Calculate the estimated total bacterial count in the sample by multiplying the bacterial concentration by the sample volume.
6.  Print a summary with the collected information and the calculated total bacterial count, clearly labeled.