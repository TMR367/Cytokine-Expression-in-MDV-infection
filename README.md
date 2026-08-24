D# MDV Burden and Cytokine Expression in Naturally Infected Chickens

## Overview

This repository contains the dataset and R scripts associated with the study:

**“Paired liver–spleen profiling links Marek’s disease virus burden to cytokine remodeling in naturally infected chickens.”**

The study investigated relationships between Marek’s disease virus (MDV) genomic burden and the expression of six immune-related cytokines in paired liver and spleen tissues from naturally infected chickens. MDV burden was quantified by qPCR, while cytokine expression was assessed by RT-qPCR using GAPDH as the reference gene.

The repository is provided to support transparency, reproducibility, and reuse of the statistical analyses reported in the manuscript.

## Repository contents

* **MDV_Cytokine_Combined_Analysis_Data.xlsx** – MDV-load and cytokine-expression dataset used for statistical analysis.
* **MDV_Final_Analysis_Single_Workbook.R** – R script used for statistical analyses and generation of Figures 1–5 and mixed-effects model outputs.
* **README.md** – description of the dataset, variables, and analysis workflow.

## Study groups

The dataset includes:

* **MDV-positive chickens:** 18 birds with complete paired liver and spleen measurements.
* **Control chickens:** 5 apparently healthy birds confirmed negative for MDV.

The bird was considered the biological unit, with liver and spleen representing paired observations from the same individual.

MDV-positive birds were additionally divided into lower- and higher-burden groups for descriptive visualization using the median systemic MDV burden of **2,983.54 copies/ng DNA**. This classification was not considered a diagnostic or biological threshold.

## Data dictionary

| Variable          | Description                                                                                  | Unit/format              |
| ----------------- | -------------------------------------------------------------------------------------------- | ------------------------ |
| `SampleName`      | Unique identification code for each chicken                                                  | Character                |
| `Tissue`          | Tissue from which the measurement was obtained                                               | Liver / Spleen           |
| `MDV_Rep1`        | First technical replicate of MDV genomic load                                                | copies/ng DNA            |
| `MDV_Rep2`        | Second technical replicate of MDV genomic load                                               | copies/ng DNA            |
| `MDV_Rep3`        | Third technical replicate of MDV genomic load                                                | copies/ng DNA            |
| `MDV_Mean`        | Mean MDV load calculated from three technical replicates                                     | copies/ng DNA            |
| `MDV_CV_percent`  | Coefficient of variation among MDV technical replicates                                      | %                        |
| `MDV_Status`      | Molecular classification according to MDV detection                                          | MDV-positive / Control   |
| `Systemic_Burden` | Bird-level systemic burden calculated from paired liver and spleen MDV loads                 | copies/ng DNA            |
| `Burden_Group`    | Descriptive classification based on the median systemic burden                               | Control / Lower / Higher |
| `IFNG_Rep1–3`     | Technical replicates of GAPDH-normalized IFN-γ expression                                    | Relative expression      |
| `IFNG_Mean`       | Mean normalized IFN-γ expression                                                             | Relative expression      |
| `IL2_Rep1–3`      | Technical replicates of GAPDH-normalized IL-2 expression                                     | Relative expression      |
| `IL2_Mean`        | Mean normalized IL-2 expression                                                              | Relative expression      |
| `IL4_Rep1–3`      | Technical replicates of GAPDH-normalized IL-4 expression                                     | Relative expression      |
| `IL4_Mean`        | Mean normalized IL-4 expression                                                              | Relative expression      |
| `IL6_Rep1–3`      | Technical replicates of GAPDH-normalized IL-6 expression                                     | Relative expression      |
| `IL6_Mean`        | Mean normalized IL-6 expression                                                              | Relative expression      |
| `IL10_Rep1–3`     | Technical replicates of GAPDH-normalized IL-10 expression                                    | Relative expression      |
| `IL10_Mean`       | Mean normalized IL-10 expression                                                             | Relative expression      |
| `IL17_Rep1–3`     | Technical replicates of GAPDH-normalized IL-17 expression                                    | Relative expression      |
| `IL17_Mean`       | Mean normalized IL-17 expression                                                             | Relative expression      |
| `*_CV_percent`    | Coefficient of variation among the three technical replicates for the corresponding cytokine | %                        |

## Systemic MDV burden

For each MDV-positive bird, systemic burden was calculated from the mean MDV loads in paired liver and spleen samples as:

**Systemic MDV burden = √[(mean liver MDV load) × (mean spleen MDV load)]**

The median systemic burden among the 18 MDV-positive birds was **2,983.54 copies/ng DNA**.

For descriptive analyses:

* **Lower burden:** ≤ 2,983.54 copies/ng DNA
* **Higher burden:** > 2,983.54 copies/ng DNA

Continuous MDV burden, rather than the categorical grouping, was used for the primary association analyses.

## Cytokine targets

The following cytokines were evaluated:

* IFN-γ – interferon gamma
* IL-2 – interleukin 2
* IL-4 – interleukin 4
* IL-6 – interleukin 6
* IL-10 – interleukin 10
* IL-17 – interleukin 17

GAPDH was used as the reference gene for normalization.

## Statistical analysis

Analyses were performed in R. The main analyses included:

* paired Wilcoxon signed-rank test for liver versus spleen MDV burden;
* Kruskal–Wallis tests for descriptive comparisons among control, lower-burden, and higher-burden groups;
* Spearman rank correlations between tissue-specific MDV burden and cytokine expression;
* linear mixed-effects models with bird identity included as a random intercept;
* MDV burden-by-tissue interaction testing;
* Benjamini–Hochberg correction for multiple testing; and
* generation of publication figures and statistical summary tables.

For the mixed-effects models, MDV burden was log10-transformed and cytokine expression was log2-transformed before analysis.

## Reproducibility

To reproduce the analyses:

1. Download the Excel dataset and R script.
2. Place both files in the same working directory.
3. Open `MDV_Final_Analysis_Single_Workbook.R` in RStudio.
4. Install any required R packages listed at the beginning of the script.
5. Run the complete script.

The script generates Figures 1–5 and the corresponding statistical output tables.

## Data interpretation

Control birds had non-detectable MDV results. These observations should therefore be treated as **non-detects rather than quantitative zero viral loads**. Controls were excluded from statistical models requiring continuous MDV burden.

The lower- and higher-burden categories were created only for descriptive visualization and should not be interpreted as latent, clinical, diagnostic, or biologically validated stages of Marek’s disease.

## Data availability

The dataset supporting the study and the associated R scripts are publicly available through this repository. A permanently archived version of the dataset should be cited using the corresponding repository DOI or accession number when available.

## Contact

For questions concerning the dataset or analysis, please contact:

**Dr. Tofazzal Md Rakib**
Department of Pathology and Parasitology
Faculty of Veterinary Medicine
Chattogram Veterinary and Animal Sciences University
Chattogram, Bangladesh
Email: **[rakibtofazzal@cvasu.ac.bd](mailto:rakibtofazzal@cvasu.ac.bd)**
