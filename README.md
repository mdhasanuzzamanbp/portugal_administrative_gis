# Portugal Administrative GIS & Freguesia Population Dataset

## Executive Summary
<p align="justify">
The project visualizes official geographic boundaries in Portugal, including the Nomenclature of Territorial Units for Statistics (NUTS) and Official Administrative Charter of Portugal (Municipality and Freguesia; CAOP), and combines it with population data at the Freguesia level. The final outputs are prepared as GIS-ready datasets and professional cartographic products. 
</div>
The project integrates: 

- NUTS 1, NUTS 2 and NUTS 3 statistical regions
- Local administrative level boundaries
- Freguesia-level population data

## Project Maps

### Portugal NUTS Hierarchy
This map visualizes Portugal's statistical geographic hierarchy from NUTS 1 to NUTS 3. It shows the spatial organization of the NUTS regions, including mainland Portugal, Madeira, and the Azores.
[See Table 2](#table-2-geographic-hierarchy-and-administrative-levels)

<p align="center">
<img width="auto" height="2000" alt="01_Portugal_NUTS_Hierarchy" src="https://github.com/user-attachments/assets/02a93b40-da9c-4424-b011-c47283f552b2" />
</p>

### Municipality, Freguesia & Population
This map shows Portugal's local administrative geography, including municipality and Freguesia boundaries. Freguesia polygons are symbolized according to 2021 population, while municipality boundaries are displayed according to CAOP 2025. [See Table 1](#table-1-geographic-data-sources-and-reference-years) 

<p align="center">
<img width="7086" height="3484" alt="02_Portugal_Municipality_Freguesia_Population" src="https://github.com/user-attachments/assets/d7a61a8b-07b0-405e-9819-cdd658478e77" />
</p>

## Project Objectives

1. Building a clear administrative and statistical geographic hierarchy for Portugal. 
2. Preparing NUTS 1, NUTS 2, and NUTS 3 datasets. 
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
9. Aggregated population records at the Freguesia level
10. Joined population data to the Freguesia boundary
11. Created population-based symbology. 
12. Performed QA/QC validation. 
13. Exported final deliverable GIS datasets
14. Produced cartographic layouts and documentation

[Full GIS Workflow](https://github.com/mdhasanuzzamanbp/portugal_administrative_gis/tree/main/screenshots) 

## Tools
**QGIS:** Select features, Merge vector layers, Aggregate, Join, Symbology, Attribute table, Vector geometry, Check validity, QA/QC, Layout
**Microsoft Word:** Documentation<br>
**Microsoft Excel:** Data Dictionary


## Data Sources
<p align="justify">
Eurostat regional-level NUTS datasets were obtained from official European geographic data sources GISCO 2024. On the other hand, local administrative datasets were obtained from CAOP 2025. However, Population data with reference year 2021 were integrated at the freguesia level boundaries. Therefore, the 2021 population is represented using 2025 Freguesia administrative boundaries
The datasets with geographic reference are listed below: 
</div>

### Table 1. Geographic Data Sources and Reference Years

| Datasets | Geographic level | Usage |
|---|---|---|
| [Eurostat GISCO NUTS 2024](https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics) | NUTS 1–3 | Regional hierarchy |
| [CAOP 2025](https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop) | Municipality and Freguesia | Administrative boundaries |
| [Population dataset – INE Census 2021](https://mapas.ine.pt/download/index2021LugaresFregs.html) | Freguesia | Population attributes |

>**Note:** NUTS: Year 2024, 1:1 Million, EPSG:3035 – ETRS89 / LAEA Europe  
**Map Projection Grid:** EPSG:4326 (WGS 84)

## Geographic Hierarchy

Portugal's geographic structure includes both territorial and local administrative units. The NUTS classification is used for statistical and regional levels, while municipalities and Freguesias represent local administrative level geography.

<div align="center">
<img width="386" height="397" alt="Picture1" src="https://github.com/user-attachments/assets/e0c33bc0-ef07-4a2b-8eb3-2087d8b2676f" />
</div>


### Table 2. Geographic Hierarchy and Administrative Levels

| Level | Geography | Role |
|---|---|---|
| Country | Portugal | National level |
| NUTS 1 | Territory of the Mainland and Autonomous Regions | Statistical classification |
| NUTS 2 | Administrative Regions | Statistical and planning |
| NUTS 3 | Inter-municipal Communities and Metropolitan Areas | Detailed regional statistics |
| Municipality | Município | Local administrative level |
| Freguesia | Freguesia | Local administrative subdivision |

> **Note:** NUTS 1, 2 and 3 are statistical subdivisions defined by Eurostat.  
> Municipality and Freguesia are local administrative levels.

## Final Freguesia Population Dataset
<p align="justify">
Population data were joined to the freguesia administrative boundaries using geographic identifiers. Population data containing multiple records associated with the same freguesia were aggregated with the sum function. Then, the relevant population values were joined to the freguesia boundary layer. The final population field represents the 2021 population associated with the corresponding freguesia.
</div>

<div align="center">
<img width="131" height="222" alt="Picture2" src="https://github.com/user-attachments/assets/fb8f6023-4a97-44b2-b93b-68eb4b2e1a7d" />
</div>


### Table 3. Freguesia Attribute Fields and Descriptions

| Field | Description |
|---|---|
| `GEO_ID` | Freguesia geographic identifier |
| `FREGUESIA` | Freguesia name |
| `MUNICIPIO` | Municipality |
| `DISTRICT` | District |
| `NUTS1` | NUTS 1 region |
| `NUTS2` | NUTS 2 region |
| `NUTS3` | NUTS 3 region |
| `AREA_HA` | Area in hectares |
| `POPULATION` | Total number of inhabitants |
| `COUNTRY` | Country |
| `SOURCE` | Boundary/source information |

## QA/QC Results

### Table 4. Quality Assurance and Quality Control (QA/QC) Results

| Check | Result |
|---|---:|
| Total Freguesia features | 3,259 |
| Missing `GEO_ID` | 0 |
| Duplicate `GEO_ID` | 0 |
| Invalid geometries | 0 |
| Geometry errors | 0 |
| Population NULL | 302 |

<p align="justify">
Population coverage is incomplete because the population data source does not use the same Freguesia geographic configuration as the administrative boundaries. As a result, we could not directly match 302 current Freguesia records to a population value. We retained these records with NULL population values rather than assigning potentially incorrect values.
</div>

## Limitations 
- Administrative boundaries and population data have different reference years.
- Some freguesias do not have corresponding population records in the population datasets. 
