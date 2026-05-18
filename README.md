# West Pacific Leatherback Turtle Population Assessment

This repository contains the modeling logic and dynamic reporting code for assessing the population status and trends of the **West Pacific Leatherback Turtle (*Dermochelys coriacea*) Distinct Population Segment (DPS)**. 

*(Note: To protect sensitive species data, raw empirical nesting counts are **not** hosted in this repository. Users must supply their own authorized datasets to render the analysis.)*

This project is maintained by the **National Marine Fisheries Service (NMFS)** and **NOAA Fisheries** to support ongoing status reviews under the **Endangered Species Act (ESA)**.

## Project Overview

The West Pacific leatherback DPS is a critically imperiled population nesting primarily in Indonesia, the Solomon Islands, and Papua New Guinea. This repository provides a reproducible Quarto-based workflow with an integrated Bayesian state-space model to generate status reports that synthesize:
* **Abundance Estimates**: Dynamic calculation of nesting females based on standardized monitoring (e.g., currently indexed at ~1,277 nesting females).
* **Population Trends**: Long-term annual decline estimates (e.g., historically ~ -5.7% annually at primary index beaches) and 50-year projection thresholds.
* **Threat Assessments**: Evaluations of primary stressors including fisheries bycatch, egg harvest, and climate change impacts.

## Repository Structure

* `PIFSC_MTAP_SAR_MMPAStyle.qmd`: The primary Quarto document used to execute the JAGS imputation and state-space models, and render the final assessment.
* `figures/`: A directory containing spatial and demographic visualizations from the 2020 ESA Status Review:
    * **ESA_Fig8_DPSs.png**: Global DPS boundary map.
    * **ESA_Fig11_PAC_BycatchHotspots.png**: Fisheries bycatch risk maps.
    * **ESA_Fig39_WP_Nesting.png**: West Pacific nesting site distribution.
    * **ESA_Fig40_WP_SatTracks.png**: Satellite telemetry showing bimodal migration.
* `.gitignore`: Configured to prevent accidental uploads of `.csv` data files.

## Technical Summary (Default Parameters)

| Parameter | Value |
| :--- | :--- |
| **Species** | *Dermochelys coriacea* |
| **DPS** | West Pacific |
| **Clutch Frequency** | 5.5 nests/season |
| **Remigration Interval** | 3.06 years |
| **ESA Status** | Endangered |
| **Extinction Risk** | High |

## Prerequisites & Dependencies

To execute the code and generate the report, you must have the following installed on your system:
1. **R** and **RStudio**
2. **Quarto CLI**
3. **JAGS (Just Another Gibbs Sampler):** Must be installed at the system level (outside of R) for the `jagsUI` package to compile the Bayesian models.

**R Packages Required:**
```R
install.packages(c("ggplot2", "dplyr", "tidyr", "flextable", "jagsUI"))
```

## Data Schema Requirements

Because raw data is excluded from version control, you must place your authorized nesting data into the root directory before rendering. 

The Quarto document specifically looks for two files with the following exact names and column headers:

1. **`JM_nests_October2025.csv`**
   * Required columns: `Year_begin`, `Month_begin`, `JM_Nests`
2. **`W_nests_October2025.csv`**
   * Required columns: `Year_begin`, `Month_begin`, `W_Nests`

## Usage

Ensure your data folder with two CSV files and the `figures/` directory are in the same working directory as the `.qmd` file.

To render the report from RStudio, click the **Render** button. Alternatively, render from the terminal:
```bash
quarto render PIFSC_MTAP_SAR_MMPAStyle.qmd
```
*(Note: The MCMC simulations utilize 50,000 iterations by default. Rendering may take a few minutes depending on your hardware.)*

## Disclaimer

This repository synthesizes and reviews the best available scientific and commercial data but does not represent a final decision by the National Marine Fisheries Service or the U.S. Fish and Wildlife Service regarding species listing status or regulatory changes.

## Reference

National Marine Fisheries Service and U.S. Fish and Wildlife Service. (2020). *Endangered Species Act status review of the leatherback turtle (Dermochelys coriacea)*. Report to the National Marine Fisheries Service Office of Protected Resources and U.S. Fish and Wildlife Service.