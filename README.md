# NESP_4.24_GOC

This repository contains the collated data associated with report for NESP Project 4.24 – Towards assessing the values of reefs in the southern Gulf of Carpentaria. A synthesis of the existing scientific data on the coral reefs in the southern Gulf of Carpentaria.

<https://www.nespmarinecoastal.edu.au/project/4-24/>

Report prepared by: Maya Srinivasan, Gemma Galbraith and Damien Burrows

Centre for Tropical Water and Aquatic Ecosystem Research (TropWater), James Cook University

<a href="https://www.tropwater.com/">
  <img src="images/f4c31c_2c1e04f0fadd407cac57f3fe6b0a72fe~mv2.png" width="300" alt="TropWater Logo">
</a>

Suggested report citation: Srinivasan, M., Galbraith, G.F. and Burrows, D. (2025) NESP Project 4.24 – Towards assessing the values of reefs in the southern Gulf of Carpentaria. A synthesis of the existing scientific data on the coral reefs in the southern Gulf of Carpentaria. [DOI:10.13140/RG.2.2.17532.50562]

The final report is available [here](https://www.nespmarinecoastal.edu.au/publication/a-synthesis-of-the-existing-scientific-data-on-the-coral-reefs-in-the-southern-gulf-of-carpentaria/)

Data have been collated from existing sources and should be cited using original attribution.

**Coral reef fish and benthic data**

Ecological survey data collected by Reef Life Survey Foundation (RLS) were extracted from the following following datasets at <https://portal.aodn.org.au/> And extracted using a bounding box with the following coordinates: -9.26N, -18.1S, 142.29E, 131.66W.

- [IMOS - National Reef Monitoring Network Sub-Facility - Global reef fish abundance and biomass](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/b273fafa-03d6-4fc2-9acf-39d8c06581e5)
- [IMOS - National Reef Monitoring Network Sub-Facility - Global mobile macroinvertebrate abundance](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/48cf3cb9-caa9-4633-9baa-8bba3c4d904a)
- [IMOS - National Reef Monitoring Network Sub-Facility - Survey metadata](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/997c2e15-b345-438f-afac-49a4ac19be38)
- [IMOS - National Reef Monitoring Network Sub-Facility - Global cryptobenthic fish abundance](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/9efa25cd-4da4-47b5-9385-45e3cbd11705)
- [IMOS - National Reef Monitoring Network Sub-Facility - Global off-transect species observations](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/a73907b7-3686-4dcf-8a1d-7efc4e5ffc05)
- [IMOS - National Reef Monitoring Network Sub-Facility - Site information](https://catalogue-imos.aodn.org.au/geonetwork/srv/eng/catalog.search#/metadata/e41efa35-03f0-4dea-be98-2a69e46b510b)

Benthic data was provided directly by RLS (benthic photo annotation data - see raw_data - RLS_GOC_benthicdata.csv). Benthic images were annotated by Reef Life Survey Foundation (RLS) in Squidle+ and the data were provided to the project team for analysis.

Hamish Malcolm provided raw data from underwater visual census surveys conducted in the southern Gulf of Carpentaria in 1997 and 1998.
(raw_data/Hamish_Malcolm_Wellesley_data.xlsx)
We obtained a scanned copy of the report from the author and entered the raw data into an Excel file.
This study is one of just three studies examining fish communities in this region, and the surveys were the first underwater visual surveys to be conducted in the southern Gulf of Carpentaria.
A total of 12 sites were surveyed across two time periods (October 1997 May 1998), with 3 sites surveyed during both time periods. 
Survey methods: At each site, one 45-minute timed swim was conducted by a single diver, recording the relative abundance of fish seen within 5 m on either side. Each species of fish was assigned an abundance category based on its relative abundance: rare/uncommon (1 to 5 individuals), common (6 to 125 individuals), and abundant (126 to >3125 individuals). 
Malcolm H (1998) Reef Fish Community and Incidental Observations: Wellesley Islands - Gulf of Carpentaria, October 1997 and May 1998. Technical report to the Queensland Department of Environment.
The Excel file contains the following sheets: 
Data - raw data, with columns for Site (site name), Time (time period) and a column for each species. Each row has the abundance category for each species at each site and time period.
Incidental sightings - rare species not included in the abundance data as just 1-3 individuals were observed during the study. The 3 columns give the common and scientific names of the species, and the number of sites each species was found at. 
Site info - list of sites with columns for Site code, Island where the site is, the latitude and longitude (columns: Lat and Long), the date surveyed in each time period (Columns: 1997 date, 1998 date), depth, visibility, and which time period each site was surveyed in (column: "Survey 1/2/both"
Notes - relative abundance categories are in column A, and the number of fish associated with each category in column B. 
Species list - a list of all species observed in this study (column: Species), the fish family each species is in (column: Family), and whether the species was included in survey data or incidental sightings (column: Survey/Incidental). 
The abundance categories are from 1 to 6, 1 = 1 individual in a 45-minute timed swim, 2 = 2 to 5 individuals, 3 = 6 to 25 individuals, 4 = 26 to 125 individuals, 5 = 126 to 525 individual, and 6 = >525 individuals.

**Notes on code structure, folders and outputs**

code

- RLS_benthic_wrangling.Rmd - this is a R markdown file that contains the code used to wrangle the benthic data provided by RLS (raw_data/RLS_GOC_benthicdata.csv). The output of this code is a csv file (analysis_data/RLS_benthic_analysis_ready.csv) which contains the benthic data in a format suitable for the analysis presented in this report.
Running this markdown requires analysis_data/RLS_benthic_cats_crosswalk.csv and generates analysis_data/RLS_benthic_analysis_ready.csv

- benthic_figures.Rmd - this is a R markdown file that contains the code used to generate the benthic figures presented in the report. It requires the output of RLS_benthic_wrangling.Rmd (analysis_data/RLS_benthic_analysis_ready.csv) and generates figures 13,14,19 and 20 as presented in the final report.

- RLS_data_prep.Rmd - this is a R markdown file that contains the code used to wrangle the RLS data provided by IMOS for reef fish abundance and biomass, macroinvertebrate abundance, survey metadata, cryptobenthic fish abundance, off-transect observations and site infomation (all in raw_data folder). The output of this code is a csv file (analysis_data/RLS_fish_analysis_ready.csv) which contains the fish data in a format suitable for the analysis presented in this report and a list of unique fish species from the RLS reef fish data (summary_data/reef_fish_species_list.csv)

- RLS_fish_figures.Rmd - this is a R markdown file that contains the code used to generate the fish figures presented in the report. It requires the output of RLS_data_prep.Rmd (analysis_data/RLS_fish_analysis_ready.csv). It calculates fish biomass based on lengthj-weight equations and size estiamtes from the RLS data and generates figures 17 and 21 as presented in the final report.

- multivariate_analysis.Rmd - this is a R markdown file that contains the code used to perform multivariate analysis on the benthic and fish data. It requires the output of RLS_benthic_wrangling.Rmd (analysis_data/RLS_benthic_analysis_ready.csv) and RLS_data_prep.Rmd (analysis_data/RLS_fish_analysis_ready.csv). It generates figures 18, 22 and 23 as presented in the final report and the summary of invertebrate abundance and species list found in summary_data (inverts_list.csv and inverts_abundance_southern_GOC.csv).
