# **Live-cell growth assays: Incucyte Graphs at Guide Level**
This repository is a sub-repository that forms part of the analysis for the manuscript:  *"Uncovering RNA Dependencies in Lung Cancer through CRISPR–Cas13d Functional Genomics"*

## Overview

This repository contains an R Markdown workflow for processing and visualizing IncuCyte growth assay data across multiple cell lines (A549Cas13d, H1975Cas13d, and H1299Cas13d) for target validation.

## Project structure 

## Required Software and environment 

- **R** (version **4.5.0 or later**)
- **R packages**:
  - tidyverse
  - readxl
  - FSA
  - ggpubr
  - gridExtra
  - reshape

This project uses the **`renv`** package to manage R package dependencies and ensure reproducibility.
All required package versions are recorded in the `renv.lock` file.

To set up the environment:

```r
install.packages("renv")
renv::restore()
```

## Input Data

This analysis was performed using data obtained from the **IncuCyte S3 Live-Cell Analysis System** (Sartorius).

Green object counts were quantified and normalized to the **12-hour time point** using the IncuCyte software.

All input data are located in the `Input/` directory:

### Files

- **Targets_biotype.xlsx**  
  Assigns biotypes to each target.

- **green_objects_<cell_line>.csv**  
  Raw green object counts for each cell line.

- **confluence_<cell_line>.csv**  
  Confluence measurements for each cell line.


## Output files 

All output plots are saved as PDF files in the `Output/` directory.

- **Confluence plots**  
  Confluence after 48 h for the A549Cas13d and H1299Cas13d cell lines, and after 72 h for the H1975Cas13d cell line, showing values for CEG, NEG, and NT control.  
  Values from the three guides targeting the same gene were averaged.

- **Green object bar plots (guide level)**  
  Counts of GFP-positive cells at the guide level. Each bar represents the mean across technical replicates (n = 2), with error bars indicating standard deviation (SD).

- **Green object counts per target**  
  GFP-positive cell counts summarized at the target level, showing the impact of targeting different transcripts on cell growth.  
  Values from the three guides targeting the same gene were averaged.
  
## *Notes*

Green object counts are normalized to the 12h time point.

Confluence values are used directly as percentages.

Some guides may be excluded when signal detection becomes unreliable (e.g., RPS16 g3 in H1975).
