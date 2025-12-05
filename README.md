#**Live-cell growth assays: Incucyte Graphs at Guide Level**

##Overview

This project contains an R Markdown workflow for processing and visualizing Incucyte growth assay data across 
multiple cell lines (A549, H1975, and H1299).

The script loads raw Incucyte outputs, summarizes replicate values, and generates a series of plots including:

    - Green objects (GFP-positive cells) 
    - Confluence over time 
    - Barplots (guide level) at endpoint time points
    - Statistical comparison between CEG and NEG confluence 
    
All results are saved in the Output/ directory.

##Input Data

Place all raw files into:

~/Growth_assays-Incucytedata/Input/

Targets_biotype.xlsx – Biotype assignment per target

green_objects_<cell_line>.csv – Raw green object counts for each cell line

confluence_<cell_line>.csv – Confluence measurements for each cell line


##Output

All plots are saved as PDF in ~/Growth_assays-Incucytedata/Output/


##*Notes*

Green object counts are normalized to the 12h time point.

Confluence values are used directly as percentages.

Some guides may be excluded when signal detection becomes unreliable (e.g., RPS16 g3 in H1975).
