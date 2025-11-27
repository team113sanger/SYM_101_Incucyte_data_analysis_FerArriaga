Live-cell growth assays: Incucyte Graphs at Guide Level

Overview

This project contains an R Markdown workflow for processing and visualizing Incucyte growth assay data across 
multiple cell lines (A549, H1975, and H1299).
The script loads raw Incucyte outputs, summarizes replicate values, and generates a series of plots including:

    -Green object (GFP-positive cell) timelines

    -Confluence timelines

    -Barplots at endpoint time points

    -Basic statistical comparisons

All results are saved in the Output/ directory.

Requirements

R (version ≥ 4.0 recommended)

Packages:

FSA

gridExtra

reshape

ggpubr

tidyverse

dplyr

ggplot2

readxl

The project used renv to manage package versions.


Input Data

Place all raw files into:

~/Growth_assays-Incucytedata/Input/

Targets_biotype.xlsx – Biotype assignment per target

green_objects_<cell_line>.csv – Raw green object counts for each cell line

confluence_<cell_line>.csv – Confluence measurements for each cell line


Output

Timeline plots of green objects per target and biotype

Barplots of green objects at the final time point

Confluence plots for selected biotypes

All plots are saved as PDF in ~/Growth_assays-Incucytedata/Output/


Notes

Green object counts are normalized to the 12h time point.

Confluence values are used directly as percentages.

Some guides may be excluded when signal detection becomes unreliable (e.g., RPS16 g3 in H1975).