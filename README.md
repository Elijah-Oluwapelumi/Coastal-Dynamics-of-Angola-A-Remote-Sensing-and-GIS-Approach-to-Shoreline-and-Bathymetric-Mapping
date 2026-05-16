# Spatio-Temporal Analysis of Coastal Change: Shoreline Mapping and Bathymetric Assessment Along the Angola Coastline

![GIS](https://img.shields.io/badge/Field-GIS-blue)
![Remote Sensing](https://img.shields.io/badge/Skill-Remote%20Sensing-green)
![ArcGIS Pro](https://img.shields.io/badge/Tool-ArcGIS%20Pro-orange)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)
![Focus](https://img.shields.io/badge/Focus-Coastal%20Geomorphology-red)

---

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Study Area](#study-area)
- [Data Sources](#data-sources)
- [Tools and Technologies](#tools-and-technologies)
- [Methodology](#methodology)
- [Results and Insights](#results-and-insights)
- [Spatial Analysis](#spatial-analysis)
- [Interpretation](#interpretation)
- [Conclusion](#conclusion)
- [Recommendations](#recommendations)
- [References](#references)

---

## Project Overview

Angola's coastline spans approximately 1,650 km along the South Atlantic Ocean, encompassing a diverse range of geomorphological and ecological features shaped by the Benguela Current, major river systems, and ongoing urbanization pressures.

This project applies **Remote Sensing and GIS** techniques to carry out a spatio-temporal analysis of Angola's coastline, integrating bathymetric mapping with automated shoreline detection. The study reveals underwater slope variability, coastal habitat zones, and current shoreline configuration to support evidence-based coastal management.

---

## Objectives

- Acquire and preprocess spatial datasets including GEBCO bathymetric data, GRID3 Africa boundary shapefiles, and Landsat satellite imagery
- Generate bathymetric products such as hillshade maps, depth transects, and 3D visualizations to reveal seafloor morphology
- Identify and classify major coastal features and potential habitat zones
- Detect the shoreline using the Digital Shoreline Analysis System (DSAS) and NDWI-based extraction
- Provide region-specific recommendations for coastal management and erosion mitigation

---

## Study Area

Angola's coastline extends from the mouth of the Congo River in the north (border with the Republic of Congo) to the Cunene River in the south (border with Namibia), spanning latitudes 4°22′S to 18°S.

The coast is divided into three distinct sectors:

- **Northern Coast** — Humid, river-influenced, with mangroves, estuaries, and lagoons
- **Central Coast** — Heavily urbanized around Luanda, with major ports, erosion risk, and industrial activity
- **Southern Coast** — Arid to semi-arid, strongly influenced by the Benguela Current upwelling system

 
<img width="5846" height="4134" alt="Study_area_1" src="https://github.com/user-attachments/assets/4934b6ff-370a-4007-b04d-6b9683ac2761" />


---

## Data Sources

| Data | Source | Purpose |
|------|--------|---------|
| GEBCO 2023 Bathymetric Grid | GEBCO Compilation Group | Seafloor depth and morphology |
| GRID3 Africa Boundary Shapefile | GRID3 | Administrative clipping and boundary mapping |
| Landsat 9 Imagery (2025) | Google Earth Engine / USGS | Shoreline detection via NDWI |

---

## Tools and Technologies

- ArcGIS Pro
- Google Earth Engine (Python API / Google Colab)
- Remote Sensing Techniques
- Raster and Vector Analysis
- Digital Shoreline Analysis System (DSAS)

---

## Methodology

### 1. Data Preprocessing

- GEBCO bathymetric data converted from NetCDF to GeoTIFF format
- Angola boundary shapefile used to clip bathymetric grid to the study area extent
- Satellite imagery cloud-filtered and atmospherically corrected within Google Earth Engine
- False color composites generated (Bands 4-3-2, Landsat) to enhance land-water contrast
- All datasets reprojected to **WGS 1984 UTM Zone 33S**

---

### 2. Hillshade Mapping

**Aim:**
- To produce a visual representation of seafloor relief by simulating light and shadow across the bathymetric surface.

**Objective:**
- To identify spatial variability in slope gradients across northern, central, and southern sectors of Angola's coast.

---

### 3. Depth Transects (A–H)

**Aim:**
- To quantify how water depth increases with distance from the shoreline at representative locations along the coast.

**Objective:**
- To draw eight evenly spaced transects perpendicular to the coastline, extract depth values, and produce profiles that distinguish shallow from steep seafloor sections.

---

### 4. Composite Depth Profile

**Aim:**
- To compare slope characteristics across all eight transects within a single plot.

**Objective:**
- To reveal the transition from depositional (north) to erosional (central) coastal environments and the mixed dynamics of the south.

---

### 5. 3D Seafloor Visualization

**Aim:**
- To provide an intuitive three-dimensional representation of the seafloor for both technical and non-technical audiences.

**Objective:**
- To extrude bathymetric data in QGIS 3D View and ArcGIS ArcScene, highlighting slope breaks, underwater ridges, and depressions.

---

### 6. Shoreline Detection (NDWI + DSAS)

**Aim:**
- To automatically extract the land–water boundary along the Angola coastline using satellite imagery.

**Objective:**
- To apply the Normalized Difference Water Index (NDWI) on Landsat 9 imagery within Google Earth Engine, convert the result to vector format, clean the output in ArcGIS Pro, and prepare it for DSAS shoreline change analysis.

NDWI Formula:

```
NDWI = (Green - NIR) / (Green + NIR)
```

---

### 7. Coastal Feature and Habitat Zone Identification

**Aim:**
- To classify the coastal environment into geomorphological and ecological zones.

**Objective:**
- To interpret bathymetric and shoreline outputs in terms of slope type, sediment pathways, and habitat suitability, supporting biodiversity and fisheries planning.

---

## Results and Insights

### Hillshade Map

The hillshade map revealed significant spatial variation across Angola's seafloor:

- **Northern Angola** — Broad, smooth continental shelf; gently sloping; favorable for artisanal fisheries and shallow-water ecosystems
- **Central Angola** — Steep submarine escarpments and possible canyon features; sediment bypasses the shelf directly to deep water
- **Southern Angola** — Mixed morphology of flat terraces and slope breaks, shaped by the Benguela Current

 <img width="5846" height="4134" alt="Hillshade" src="https://github.com/user-attachments/assets/0f6f80eb-9b2f-414c-af5f-48647103713f" />

---

### Depth Profiles (A–H)

| Transect Group | Location | Key Finding |
|----------------|----------|-------------|
| A–C | Northern Angola | Gradual slopes; broad continental shelf; depths increase slowly beyond 30–40 km offshore |
| D–E | Central Angola | Steep descent within 10–15 km; submarine canyon presence; concentrated wave energy at shoreline |
| F–H | Southern Angola | Mixed patterns; irregular ridges and troughs; Benguela Current influence evident |

 
<img width="919" height="293" alt="Depth_A" src="https://github.com/user-attachments/assets/5fa21bd9-cb5e-4ca5-97c3-b781e31e39fd" />
<img width="919" height="233" alt="Depth_B" src="https://github.com/user-attachments/assets/dad48426-ce47-4873-9ebc-4516f962c041" />
<img width="919" height="233" alt="Depth_C" src="https://github.com/user-attachments/assets/225c4ffe-2acc-4d6c-a7c5-3fbc14af1f23" />
<img width="895" height="292" alt="Depth_D" src="https://github.com/user-attachments/assets/b86c9db3-ba97-4e5e-8adc-861227b76015" />
<img width="895" height="292" alt="Depth_E" src="https://github.com/user-attachments/assets/d19afa6f-0514-4b18-9d6a-b7cee79cc968" />
<img width="895" height="292" alt="Depth_F" src="https://github.com/user-attachments/assets/609eae9e-1aa3-4c01-a530-f53cd1a24cf2" />
<img width="895" height="292" alt="Depth_G" src="https://github.com/user-attachments/assets/29525dd3-a81b-4dc9-8369-486d742fcf14" />
<img width="895" height="292" alt="Depth_H" src="https://github.com/user-attachments/assets/ac0266a2-3ead-4e9a-9bf8-4cb2126a928d" />

 <img width="5846" height="4134" alt="Transect_view" src="https://github.com/user-attachments/assets/12fb22ea-9f14-4e8c-aa3c-f634c9b6a9dd" />

---

### Coastal Features and Habitat Zones

- **Depositional environments (North)** — Mangrove forests, tidal flats, nearshore sandbanks, estuarine systems; rich biodiversity
- **Erosional environments (Central)** — Submarine canyons, narrow shelves, steep shorelines; high erosion vulnerability
- **Dynamic upwelling zone (South)** — Nutrient-rich waters; shifting sandbanks; high fish productivity; unstable coastline

<img width="5846" height="4134" alt="Coastal_features" src="https://github.com/user-attachments/assets/7076d6c9-af25-4652-8e7b-120d5120605c" />
 
---

### 3D Visualization

The 3D model confirmed the three-zone structure of Angola's coast:

- Northern shelf — gently sloping plane
- Central section — steep escarpments descending sharply into deep water
- Southern section — alternating ridges and troughs consistent with current-driven sediment redistribution

 
<img width="5846" height="4134" alt="3D_viz" src="https://github.com/user-attachments/assets/2cd99823-8679-4933-a395-e3f0e0172576" />

---

### Shoreline Detection

Automated NDWI-based shoreline extraction successfully delineated the land–water boundary along the full Angola coastline. Key observations include:

- Central Angola showed clear, continuous shoreline geometry influenced by active wave processes
- Northern estuarine zones showed more complex patterns due to sediment deposition and tidal mixing
- Southern shoreline exhibited irregular curvature and segmented features tied to Benguela Current dynamics
- Artifacts from cloud remnants and shallow-water spectral confusion were reduced through morphological filtering and manual cleaning in ArcGIS Pro

<!-- DRAG YOUR SHORELINE DETECTION MAP HERE (Figure 4.7 — Automated Shoreline Extraction of Angola Coast Using Google Earth Engine) -->
<img width="4677" height="3307" alt="Angola_shoreline" src="https://github.com/user-attachments/assets/ffc2666f-f4e3-4037-9145-6c85498d2419" />

---

## Spatial Analysis

| Zone | Shelf Type | Dominant Process | Habitat Significance |
|------|-----------|-----------------|----------------------|
| Northern Angola | Wide, gentle | Deposition | Mangroves, estuaries, biodiversity hotspot |
| Central Angola | Narrow, steep | Erosion | Limited nearshore habitat; deep-water fisheries |
| Southern Angola | Mixed, irregular | Sediment redistribution (Benguela) | Nutrient upwelling; rich fisheries; unstable coast |

---

## Interpretation

The combined bathymetric and shoreline analysis reveals that Angola's coast is not uniform — it transitions from depositional to erosional environments from north to south, driven by differences in shelf morphology, river influence, and oceanographic forcing.

Key drivers of coastal change include:

- Rapid urbanization around Luanda and other central coastal cities
- Industrial dredging, sand mining, and harbor expansion altering sediment balance
- The Benguela Current system driving strong upwelling and sediment redistribution in the south
- Sea-level rise amplifying erosion risk in low-elevation northern zones

These findings confirm the need for spatially differentiated coastal management strategies rather than a uniform national approach.

---

## Conclusion

This study demonstrates the value of integrating GEBCO bathymetric data, GRID3 administrative boundaries, Landsat satellite imagery, and GIS analysis tools to characterize Angola's coastline. The outputs — hillshade maps, depth profiles, 3D visualizations, a composite depth profile, a coastal features overlay, and an automated shoreline detection map — together provide a robust spatial framework for understanding coastal dynamics.

The methodology shows how open-source and cloud-based tools (GEBCO, GRID3, Google Earth Engine) can overcome data scarcity challenges and support evidence-based decision-making in under-studied coastal regions.

---

## Recommendations

- Prioritize erosion control infrastructure and shoreline stabilization along Central Angola, particularly near Luanda
- Establish habitat conservation programs and flood risk management plans for the low-elevation northern estuarine zones
- Implement continuous satellite monitoring of shoreline dynamics along the full coastline using updated Landsat imagery
- Integrate bathymetric data into fisheries management planning for the Benguela upwelling zone in the south
- Expand DSAS-based multi-temporal shoreline change analysis using historical Landsat archives to quantify rates of erosion and accretion
