# GIS Project - Agri PV Multi Criteria Decision Analysis (MCDA)

This repository hosts the core analytical model for identifying optimal Agrivoltaic (Agri-PV) sites across Karnataka, India. By overlapping solar potential with existing agricultural land, this project aims to provide a data-driven roadmap for dual-use land energy systems.

**🎯 Project Objective**

The goal is to solve the "Land-Energy Conflict" by identifying regions where high solar radiation coincides with active cropland, minimizing the displacement of food production while maximizing renewable energy yield.

**🏗️ Methodology & Data Layers**

The study follows a Weighted Linear Combination (WLC) model, integrating three primary spatial datasets:

#### 1. Administrative Boundaries (Vector)

Source: DataMeet: https://github.com/datameet/maps/tree/master/States

File: admin2.shp

Purpose: Provides the "Study Area" mask. It allows us to aggregate suitability scores at the District and Taluk levels for policy recommendations.

#### 2. Agriculture(Cropland) Potential 

Source: ESA WorldCover 10m (Extracted via Google Earth Engine).

Processing: I built a custom cloud-pipeline to isolate cropland pixels and export them as a high-performance GeoTIFF.

> The details on how to extract the cropland data using googth earth clound api is in the following repository Link: https://github.com/soujanyakris/Agri-PV-MCDA-Cloud-Geospatial-Data-Extraction

File: karnataka_cropland_new.tif

Logic: Areas with value 1 (Cropland) are included; all other land types (Forest, Urban) are excluded.

#### 3. Solar Irradiation (Raster)

Source: Global Solar Atlas: https://globalsolaratlas.info/download

File: GHI.tif

Purpose: Represents the "Energy Yield" factor. Higher GHI values indicate higher efficiency for PV installations.

**💻 Technical Stack**

GIS Analysis: Python (geopandas, numpy, geemap, ee)

Visualization: matplotlib, folium

**📂 Repository Structure**

/files: Contains processed GeoTIFFs and Shapefiles (linked via .gitignore).

suitability_model.ipynb: The master MCDA script (Work in Progress).
