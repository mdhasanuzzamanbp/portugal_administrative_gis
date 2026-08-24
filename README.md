# Portugal Administrative GIS & Freguesia Population Dataset

## Project Overview
The project visualizes official geographic boundaries in Portugal, including the Nomenclature of Territorial Units for Statistics (NUTS) and Official Administrative Charter of Portugal (Municipality and Freguesia; CAOP), and combines it with population data at the Freguesia level. The final outputs are prepared as GIS-ready datasets and professional cartographic products. 

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
Eurostat regional level NUTS datasets were obtained from official European geographic data sources GISCO 2024. On the other hand, local administrative datasets were obtained from CAOP 2025. However, Population data with reference year 2021 were integrated at the freguesia level boundaries. Therefore, the 2021 population is represented using 2025 Freguesia administrative boundaries
The datasets with geographic reference are listed below: 


## Data Sources

<table align="center">
  <tr>
    <th>Datasets</th>
    <th>Geographic level</th>
    <th>Usage</th>
  </tr>
  <tr>
    <td align="center">
      <a href="https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics">
        Eurostat GISCO NUTS 2024
      </a>
    </td>
    <td align="center">NUTS 1–3</td>
    <td align="center">Regional hierarchy</td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop">
        CAOP 2025
      </a>
    </td>
    <td align="center">Municipality and Freguesia</td>
    <td align="center">Administrative boundaries</td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://mapas.ine.pt/download/index2021LugaresFregs.html">
        Population dataset – INE Census 2021
      </a>
    </td>
    <td align="center">Freguesia</td>
    <td align="center">Population attributes</td>
  </tr>
</table>

<p align="center">
  <strong>NUTS:</strong> Year 2024, 1:1 Million, EPSG:3035 – ETRS89 / LAEA Europe<br>
  <strong>Map Projection Grid:</strong> EPSG:4326 (WGS 84)
</p>


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

Geographic levels used in this project are listed below:
<div align="center">
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
</div>

## Final Freguesia Population Dataset

Population data were joined to the freguesia administrative boundaries using geographic identifiers. Population data containing multiple records associated with the same freguesia were aggregated with the sum function. Then, the relevant population values were joined to the freguesia boundary layer. The final population field represents the 2021 population associated with the corresponding freguesia.
<div align="center">
<img width="131" height="222" alt="Picture2" src="https://github.com/user-attachments/assets/fb8f6023-4a97-44b2-b93b-68eb4b2e1a7d" />

The identifiers of attribute table are listed below:
<div align="center">
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
</div>

## QA/QC Results

After performing Quality control the following result has been found:
<div align="center">
| Check | Result |
|---|---:|
| Total Freguesia features | 3,259 |
| Missing `GEO_ID` | 0 |
| Duplicate `GEO_ID` | 0 |
| Invalid geometries | 0 |
| Geometry errors | 0 |
| Population NULL | 302 |
</div>
Population coverage is incomplete because the population data source does not use the same Freguesia geographic configuration as the administrative boundaries. As a result, we could not directly match 302 current Freguesia records to a population value. We retained these records with NULL population values rather than assigning potentially incorrect values.


## Limitations 
- Administrative boundaries and population data have different reference years.
- Some freguesias do not have corresponding population records in the population datasets. 
