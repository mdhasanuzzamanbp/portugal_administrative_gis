# Portugal Administrative GIS & Freguesia Population Dataset

## Project Overview
The project visualize official geographic boundaries in Portugal both The Nomenclature of Territorial Units for Statistics (NUTS) and Official Administrative Charter of Portugal (Municipality and Freguesia; CAOP) and combined it with population data at the Freguesia level. The final outputs are prepared as GIS-ready datasets and professional cartographic products. 

The project integrates: 

- NUTS 1, NUTS 2 and NUTS 3 statistical regions
- Local administrative level boundaries
- Freguesia-level population data

## Project Objectives

1. Building a clear administrative and statistical geographic hierarchy for Portugal. 
2. Preparing NUTS 1, NUTS 2 and NUTS 3 datasets. 
3. Processing local administrative CAOP boundaries. 
4. Integrating Freguesia population data and boundaries. 
5. Performing spatial and attribute-level QA/QC. 
6. Producing clean and deliverable GIS-ready Shapefile. 
7. Generating professional maps for visualization and documentation. 

## Data Processing Workflow

1. Downloaded NUTS and CAOP datasets from Eurostat GISCO and Dgterritorio 
2. Filtered the NUTS and CAOP datasets for Portugal
3. Separated NUTS 1, NUTS 2, and NUTS 3 Layers
4. Merged CAOP layers of different regions in Portugal
5. Downloaded the INE Population dataset. 
6. Inspected geographic identifiers and attribute fields.
7. Matched population records to Freguesia geographic identifiers
8. Calculated and verified geographic attributes
9. Aggregated the population data in Freguseia level
10. Joined population data to the Freguesia boundary
11. Created population-based symbology. 
12. Performed QA/QC validation. 
13. Exported final deliverable GIS datasets
14. Produced cartographic layouts and documentation

## Tools
QGIS: Select features, Merge vector layers, Aggregate, Join, Symbology, Attribute table, Vector geometry, Check validity, QA/QC, Layout
Microsoft Word: Documentation
Microsoft Excel: Data Dictionary



Data Sources
Eurostat regional level NUTS datasets were obtained from official European geographic data sources GISCO 2024. On the other hand, local administrative datasets were obtained from CAOP 2025. However, Population data with reference year 2021 were integrated at the freguesia level boundaries. Therefore, 2021 population represented using 2025 Freguesia administrative boundaries
The datasets with geographic reference are listed below: 



## Data Sources

| Datasets | Geographic level | Usage |
|---|---|---|
| [Eurostat GISCO NUTS 2024](https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics) | NUTS 1–3 | Regional hierarchy |
| [CAOP 2025](https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop) | Municipality and Freguesia | Administrative boundaries |
| [Population dataset – INE Census 2021](https://mapas.ine.pt/download/index2021LugaresFregs.html) | Freguesia | Population attributes |

**NUTS:** Year 2024, 1:1 Million, EPSG:3035 – ETRS89 / LAEA Europe  
**Map Projection Grid:** EPSG:4326 (WGS 84)

## Geographic Hierarchy

Portugal's geographic structure includes both territorial and local administrative units. The NUTS classification is used for statistical and regional levels, while municipalities and Freguesias represent local administrative level geography.

<img width="386" height="397" alt="Picture1" src="https://github.com/user-attachments/assets/e0c33bc0-ef07-4a2b-8eb3-2087d8b2676f" />


