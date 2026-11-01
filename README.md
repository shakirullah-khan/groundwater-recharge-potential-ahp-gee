# Multi-Criteria Groundwater Recharge Potential Assessment & Managed Aquifer Recharge (MAR) Site Suitability Using AHP and Google Earth Engine

## Project Overview
This repository contains the geospatial workflows, Multi-Criteria Decision Analysis (MCDA) formulations, and cloud-based spatial modeling pipelines developed to delineate **Groundwater Recharge Potential Zones (GWRPZ)** across three hydrogeologically distinct districts in Khyber Pakhtunkhwa, Pakistan: **Charsadda**, **Nowshera**, and **Swat**.

Developed under a **UNICEF-sponsored project** at the **National Institute of Urban Infrastructure Planning (NIUIP)**, this research integrates Google Earth Engine (GEE), multi-spectral satellite remote sensing, and Saaty’s Analytical Hierarchy Process (AHP). The framework evaluates **twelve (12) multi-thematic parameters**, including satellite spectral indices (NDBI, NDVI, WVWI, MSI), land surface temperature (LST), topographic dynamics, river proximity, and in-situ water table observations.

To connect spatial modeling with practical water resources management, computational predictions were validated through **empirical field investigations** in designated low-recharge zones to identify optimal locations for Managed Aquifer Recharge (MAR) and rainwater harvesting interventions.

---

## Study Area Hydrogeological Context

The assessment evaluates three distinct physiographic and hydrogeological regimes:

| District | Physiographic Setting | Primary Drainage | Hydrogeological Significance |
| :--- | :--- | :--- | :--- |
| Swat | Alpine mountain terrain | Swat River Basin | Headwater catchment, snowmelt/rainfall recharge, fracture-dominated crystalline bedrock |
| Charsadda | Lowland alluvial floodplain | Kabul & Swat Confluence | High water table, fertile alluvium, intense agricultural seepage, shallow unconfined aquifer |
| Nowshera | Semi-arid lowland / piedmont | Kabul River downstream | Stressed aquifer units, deep water tables, high vulnerability to depletion, prime MAR candidate |

---

## Thematic Criteria & Analytical Hierarchy Process (AHP)

The model synthesizes twelve (12) geospatial parameters derived from multi-sensor satellite imagery (Sentinel-2, Landsat-8/9, SRTM DEM), meteorological data (CHIRPS), and field observations:

1. **Land Use / Land Cover (LULC):** Quantifies vegetation canopy, water bodies, and permeable soils versus surface runoff generation.
2. **Distance to Rivers:** Buffer zones measuring proximity to active river channels providing perennial recharge.
3. **Water Table Depth:** In-situ groundwater measurements indicating unsaturated vadose zone storage capacity.
4. **Normalized Difference Built-up Index (NDBI):** Delineates impervious man-made structures that impede infiltration.
5. **Distance to Roads:** Identifies transportation corridors and engineered linear impervious barriers.
6. **Normalized Difference Vegetation Index (NDVI):** Indicates biomass density promoting soil percolation and reducing runoff velocity.
7. **Topographic Slope:** Derived from SRTM 30 m DEM; governs surface water retention time versus runoff acceleration.
8. **Water Vapor / Water Index (WVWI):** Captures localized surface moisture availability and atmospheric-hydrologic flux.
9. **Land Surface Temperature (LST):** Thermal proxy for evapotranspiration dynamics and soil moisture depletion.
10. **Moisture Stress Index (MSI):** Evaluates canopy and surface moisture stress in the root zone.
11. **Precipitation:** Spatial distribution of meteorological input driving volumetric aquifer replenishment.
12. **Soil Type:** Subsurface texture controlling hydraulic conductivity and infiltration rates.

### Normalized Criteria Weights (AHP Matrix)
Pairwise comparisons were executed using Saaty’s 1–9 fundamental scale. To guarantee mathematical consistency, the principal eigenvalue (was calculated to verify the Consistency Index  and Consistency Ratio:


*A consistency ratio of CR < 0.10 was strictly maintained across all district models to confirm criteria weighting validity.*

| Parameter | Assigned Weight (%) | Hydrogeological & Spatial Significance |
| :--- | :--- | :--- |
| **LULC** | 13% | Primary control on surface infiltration, vegetation interception, and runoff |
| **Distance to rivers** | 13% | Proximity to perennial channels providing direct continuous recharge |
| **Water Table** | 10% | Depth to unconfined aquifer indicating available storage capacity |
| **NDBI** | 10% | Quantifies urban built-up imperviousness impeding natural percolation |
| **Distance to roads** | 10% | Linear infrastructure corridors influencing artificial drainage and compaction |
| **NDVI** | 7% | Vegetation density promoting root-zone macro-porosity and retention |
| **Slope** | 7% | Topographic gradient dictating overland runoff velocity vs. infiltration time |
| **WVWI** | 7% | High-resolution satellite proxy for water vapor and surface moisture presence |
| **LST** | 7% | Surface thermal signature inversely proportional to moisture retention |
| **MSI** | 6% | Moisture Stress Index reflecting plant and soil water stress conditions |
| **Precipitation** | 5% | Atmospheric driver of regional hydrologic replenishment |
| **Soil type** | 5% | Near-surface vadose zone permeability and soil texture |
| **Total** | **100%** | **Consolidated Multi-Criteria Analytical Framework** |

---

## Delineated Groundwater Recharge Potential Zones (GWRPZ)

The final spatial recharge index was computed using a weighted linear combination overlay:


The output index is classified into discrete hydrological zones:
* **Excellent Recharge Potential:** Unconsolidated river alluvium, flat agricultural land, dense vegetation (high NDVI), shallow-to-moderate water tables, and close proximity to rivers.
* **Good Recharge Potential:** Low-gradient terraces, semi-permeable soils, moderate vegetative cover, and intermediate distance from drainage networks.
* **Moderate Recharge Potential:** Undulating topography , clayey soils, mixed rural-settlement areas, and moderate moisture stress.
* **Poor Recharge Potential:** Steep rocky terrain , dense urban built-up zones (high NDBI), compacted road corridors, high LST, and impervious lithological units.

---

## Field Validation & Managed Aquifer Recharge (MAR)

To transition computational predictions into practical water resources engineering, empirical field investigations were conducted in identified **Poor and Moderate Recharge Zones**:

1. **Ground-Truth Site Inspections:** Visited depleted groundwater zones across Charsadda, Nowshera, and Swat to record field hydrogeology, soil compaction, and local tubewell drawdown history.
2. **Percolation Basins & Infiltration Trenches:** Identified sites on permeable alluvial terraces in Nowshera to capture seasonal river floodwaters and induce artificial recharge.
3. **Check Dams & Gully Plugs:** Mapped along steep ephemeral drainage streams in Swat to reduce runoff velocities, prevent soil erosion, and increase streambed recharge.
4. **Rooftop Rainwater Harvesting (RWH):** Delineated for high-NDBI built-up municipal centers in Charsadda and Nowshera to reduce municipal runoff and replenish local water tables.

---

## Notebook Structure & Code Execution

* `notebooks/01_swat_district_gwrp.ipynb`: GEE data ingestion, 12-thematic-layer extraction, AHP weighted overlay, and GWRPZ mapping for Swat District.
* `notebooks/02_charsadda_district_gwrp.ipynb`: Floodplain hydrogeology modeling, spectral index processing, and recharge zoning for Charsadda District.
* `notebooks/03_nowshera_district_gwrp.ipynb`: Aquifer depletion analysis, water stress evaluation, and MAR site suitability mapping for Nowshera District.

### Setup and Running Locally


---

## Project Affiliation & Author Details
* **Shakir Ullah Khan**
* Assistant Engineer, National Institute of Urban Infrastructure Planning (NIUIP), Pakistan
* Project Sponsor: Supported under the UNICEF Drinking Water & Aquifer Sustainability Framework
* Email: 22bnciv1222@uetpeshawar.edu.pk
* LinkedIn: www.linkedin.com/in/shakir-ullah-khan-409811397
