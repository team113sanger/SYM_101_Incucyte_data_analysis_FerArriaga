# **Live-cell growth assays: Incucyte Graphs at Guide Level**
This repository is a sub-repository that forms part of the analysis for the manuscript:  *"Uncovering RNA Dependencies in Lung Cancer through CRISPR–Cas13d Functional Genomics"*

## Overview

This repository contains an R Markdown workflow for processing and visualizing the Incucyte growth assay data across 
multiple cell lines (A549, H1975, and H1299).

The script loads raw Incucyte outputs, summarizes replicate values, and generates a series of plots including:

    - Green objects (GFP-positive cells) 
    - Confluence over time 
    - Barplots (guide level) at endpoint time points
    - Statistical comparison between CEG and NEG confluence 
    
All results are saved in the Output/ directory.

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

## Input Data

./Input/

Targets_biotype.xlsx – Biotype assignment per target

green_objects_<cell_line>.csv – Raw green object counts for each cell line

confluence_<cell_line>.csv – Confluence measurements for each cell line


## Output files 

All plots are saved as PDF in ~/Growth_assays-Incucytedata/Output/


## *Notes*

Green object counts are normalized to the 12h time point.

Confluence values are used directly as percentages.

Some guides may be excluded when signal detection becomes unreliable (e.g., RPS16 g3 in H1975).
