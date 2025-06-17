---
layout: page
title: Lab 4 - Lists and Loops (Iteration)
nav_exclude: true
---


## Lab 4: Tracking river dolphin Groups - Lists and Loops (Iteration)

**Context for Lab 4:** Mapping the spatial distribution of affected *Labeo bata* and South Asian River Dolphins with high bacterial loads is a crucial step in our investigation. By correlating the locations of diseased fish with toxin levels from Lab 3, and mapping dolphins with high CFU counts from Lab 2, we can identify potential disease hotspots and explore links between environmental pollution and disease burden. This spatial analysis allows us to pinpoint the most severely impacted areas, guiding further investigation and intervention efforts towards critical zones. For dolphins, understanding the spatial distribution of high bacterial loads helps track the potential spread of infection. Tracking the spatial patterns of affected *Labeo bata* over time can reveal the potential spread of the disease within the fish population, indicating possible transmission routes. Similarly, mapping dolphins with high bacterial loads can show if the infection is localized or widespread, and repeated sampling can highlight trends in its emergence. Understanding these disease spread dynamics is vital for predicting future impacts and implementing effective containment or mitigation strategies, whether targeting pollution sources upstream or protecting healthy dolphin populations. The spatial data generated directly informs targeted sampling and intervention strategies. Areas with high disease prevalence in either species warrant more intensive investigation, optimizing resource allocation. If correlations between specific toxins and disease are found, interventions can be tailored to address those pollutants in the most affected regions. This focused approach allows for more efficient data collection and and the development of evidence-based strategies to improve water quality and protect vulnerable aquatic life. Ultimately, the spatial data and identified correlations provide compelling evidence for conservation and management decisions. Visualizing the disease burden and associated environmental factors can effectively communicate the severity of the problem to stakeholders and policymakers. This evidence supports the implementation of regulations to control pollution, establish protected zones, and initiate habitat restoration efforts, contributing to the long-term protection of the endangered South Asian River Dolphin and the health of the river ecosystem.

**Problem:** Write a Python script that:
1. Stores the number of affected river dolphins per sampling location in a list.
2. Stores the identifiers of sampling locations with high bacterial CFU counts in another list.
3. Iterates through the list of affected river dolphins per location and calculates the total number of affected individuals across all locations.
4. For each river dolphins sampling location, determine if the number of affected individuals exceeds a predefined ”concern threshold” (indicating a potentially severe outbreak within that location).
5. For each river dolphins sampling location, check if its identifier is present in the list of locations with high bacterial CFU counts.
6. Print the total number of affected river dolphins.

### Worksheet:

1.  Create a list of sampling location identifiers: `["LB_LOC01", "LB_LOC02", "LB_LOC03", "LB_LOC04", "LB_LOC05"]`.
2.  Create a list representing the number of affected river dolphins in each location: `[15, 32, 5, 48, 20]`.
3.  Create a list of sampling location identifiers where at least one river dolphins had a high bacterial CFU count: `["LB_LOC02", "LB_LOC04"]`.
4.  Define a concern threshold for the number of affected river dolphins (e.g., `concern_threshold = 30`).
5.  Initialize a variable to store the total number of affected river dolphins to 0.
6.  Use a `for` loop to iterate through the list of affected counts and calculate the total. Print the total.
7.  Use a `for` loop to iterate through the sampling location identifiers. For each location:
    * Get the corresponding number of affected river dolphins from the affected counts list (using the index).
    * Check if the number of affected river dolphins exceeds the `concern_threshold`.
    * Check if the current location identifier is present in the list of high CFU locations.
    * Print a summary for each location including its identifier, the number of affected river dolphins, whether the threshold was exceeded, and whether high CFU was detected. The output should be clearly formatted.