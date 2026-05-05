# West Pacific Leatherback Turtle Population Assessment

This repository contains the data, modeling logic, and dynamic reporting code for assessing the population status and trends of the **West Pacific Leatherback Turtle (*Dermochelys coriacea*) Distinct Population Segment (DPS)**. 

This project is maintained by the **National Marine Fisheries Service (NMFS)** and **NOAA Fisheries** to support ongoing status reviews under the **Endangered Species Act (ESA)**.

## Project Overview

The West Pacific leatherback DPS is a critically imperiled population nesting primarily in Indonesia, the Solomon Islands, and Papua New Guinea. This repository provides a reproducible Quarto-based workflow to generate status reports that synthesize:
* **Abundance Estimates**: Currently indexed at **1,277 nesting females** based on standardized monitoring at Jamursba-Medi and Wermon, Indonesia.
* **Population Trends**: Long-term annual declines, including a **-5.7%** annual trend at Jamursba-Medi.
* **Threat Assessments**: Evaluations of primary stressors including fisheries bycatch, egg harvest, and climate change impacts.

## Repository Structure

* `PIFSC_MTAP_SAR_MMPAStyle.qmd`: The primary Quarto document used to render the final assessment in `.docx` or `.pdf` formats.
* `2025_abundance_trend.R`: R script for calculating dynamic abundance indices using a 3-year remigration interval and 5.5 clutch frequency.
* `take_helper_Fn.R`: Helper functions for mortality and "take" data processing.
* `figures/`: A directory containing spatial and demographic visualizations from the 2020 ESA Status Review:
    * **ESA_Fig8_DPSs.png**: Global DPS boundary map.
    * **ESA_Fig11_PAC_BycatchHotspots.png**: Fisheries bycatch risk maps.
    * **ESA_Fig39_WP_Nesting.png**: West Pacific nesting site distribution.
    * **ESA_Fig40_WP_SatTracks.png**: Satellite telemetry showing bimodal migration.

## Technical Summary

| Parameter | Value |
| :--- | :--- |
| **Species** | *Dermochelys coriacea* |
| **DPS** | West Pacific |
| **Abundance Index** | 1,277 Nesting Females |
| **Long-term Trend** | -5.7% (Jamursba-Medi) |
| **Clutch Frequency** | 5.5 nests/season |
| **ESA Status** | Endangered |
| **Extinction Risk** | High |

## Usage

To generate the report, ensure you have **R**, **RStudio**, and **Quarto** installed. Ensure the `figures/` directory is in the same working directory as the `.qmd` file.

To render the report from the command line:
```bash
quarto render PIFSC_MTAP_SAR_MMPAStyle.qmd
```

## Disclaimer

This repository synthesizes and reviews the best available scientific and commercial data but does not represent a final decision by the National Marine Fisheries Service or the U.S. Fish and Wildlife Service regarding species listing status or regulatory changes.

## Reference

National Marine Fisheries Service and U.S. Fish and Wildlife Service. (2020). *Endangered Species Act status review of the leatherback turtle (Dermochelys coriacea)*. Report to the National Marine Fisheries Service Office of Protected Resources and U.S. Fish and Wildlife Service.
