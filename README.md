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

<table>
  <thead>
    <tr>
      <th>Datasets</th>
      <th>Geographic level</th>
      <th>Usage</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <a href="https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics">
          Eurostat GISCO NUTS 2024
        </a> <sup>1</sup>
      </td>
      <td>NUTS 1–3</td>
      <td>Regional hierarchy</td>
    </tr>

    <tr>
      <td>
        <a href="https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop">
          CAOP 2025
        </a> <sup>2</sup>
      </td>
      <td>Municipality and Freguesia</td>
      <td>Administrative boundaries</td>
    </tr>

    <tr>
      <td>
        <a href="https://mapas.ine.pt/download/index2021LugaresFregs.html">
          Population dataset - INE Census 2021
        </a> <sup>3</sup>
      </td>
      <td>Freguesia</td>
      <td>Population attributes</td>
    </tr>

    <tr>
      <td colspan="3">
        <strong>NUTS:</strong> Year 2024, 1:1 Million, EPSG:3035 – ETRS89 / LAEA Europe<br>
        <strong>Map Projection Grid:</strong> EPSG:4326 (WGS 84)<br>
        <sup>1</sup>
        <a href="https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics">
          https://ec.europa.eu/eurostat/web/gisco/geodata/statistical-units/territorial-units-statistics
        </a><br>
        <sup>2</sup>
        <a href="https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop">
          https://www.dgterritorio.gov.pt/atividades/cartografia/cartografia-tematica/caop
        </a><br>
        <sup>3</sup>
        <a href="https://mapas.ine.pt/download/index2021LugaresFregs.html">
          https://mapas.ine.pt/download/index2021LugaresFregs.html
        </a>
      </td>
    </tr>
  </tbody>
</table>
