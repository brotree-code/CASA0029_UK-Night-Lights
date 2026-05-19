# Spatio-Temporal Analysis of UK Night Lights (2015–2021)

This is an individual urban data visualisation project developed for **CASA0029 Urban Data Visualisation** at UCL CASA.

The project explores spatio-temporal changes in anthropogenic night-time light intensity across the United Kingdom between 2015 and 2021. It uses VIIRS Nighttime Lights data and presents the results through an interactive 3D web map built with **Mapbox GL JS**.

## Live Demo

- **Live Demo:** https://brotree-code.github.io/CASA0029_UK-Night-Lights/
- **GitHub Repository:** https://github.com/brotree-code/CASA0029_UK-Night-Lights

---

## Project Overview

Night-time light data is widely used in urban spatial science as a proxy for economic activity, population density and urbanisation. By comparing annual night-time light intensity in 2015 and 2021, this project aims to reveal regional differences in development intensity and highlight major urban agglomerations across the UK.

The main goal is to transform high-dimensional raster-based spatial data into an accessible and visually engaging **3D web mapping interface**, allowing users to explore the distribution and change of night-time light intensity across the country.

---

## Research Aim

This project asks:

- How does night-time light intensity vary spatially across the UK?
- What changes can be observed between 2015 and 2021?
- How can 3D web mapping help communicate urban activity patterns more intuitively?
- Can interactive visualisation make large-scale spatial data more accessible to non-specialist users?

---

## Data Sources

### VIIRS Nighttime Lights

The main dataset is the **VIIRS Nighttime Lights (VNL) V2 Annual Composite**, provided by the Earth Observation Group and NOAA.

- Years used: **2015** and **2021**
- Sensor: **VIIRS Day/Night Band (DNB)**
- Original coordinate reference system: **WGS 84, EPSG:4326**
- Data type: Raster night-time light intensity

### UK Administrative Boundaries

UK administrative boundary data was obtained from the **Office for National Statistics Open Geography Portal**.

The boundary data was used to clip the night-time light raster data to the UK study area.

---

## Data Processing Workflow

The spatial processing workflow was conducted in **QGIS** before the data was exported for web visualisation.

Main steps:

1. Download VIIRS annual night-time light raster data for 2015 and 2021.
2. Clip the raster datasets to the United Kingdom boundary.
3. Create or use a **5 km × 5 km UK National Grid** in **EPSG:27700**.
4. Calculate zonal statistics to obtain the mean night-time light intensity for each grid cell.
5. Reproject the processed vector grid data to **WGS 84, EPSG:4326** for web compatibility.
6. Export the processed data as **GeoJSON**.
7. Upload the GeoJSON files to **Mapbox Studio** as tilesets.
8. Render the data in an interactive web map using **Mapbox GL JS**.

---

## Visualisation Design

The visualisation is implemented as a single-page web application using **Mapbox GL JS v3.9.0**.

### Visual Style

The project uses a **Black-Gold Fire** visual style:

- Low-intensity areas are displayed in dark red or near-black tones.
- High-intensity areas are displayed in bright gold.
- The basemap is kept minimal and dark to maximise contrast and reduce visual noise.

This design choice helps emphasise night-time light intensity while keeping the interface visually clear.

### 3D Representation

Night-time light intensity is visualised using **Mapbox fill-extrusion**:

- Each grid cell is rendered as a 3D bar.
- Bar height represents mean night-time light intensity.
- Higher bars indicate stronger night-time light intensity and likely higher levels of urban activity.

---

## Interactivity

The web map includes a custom HTML/CSS control panel that supports interactive exploration.

Main interactive features include:

- Toggle between **2015** and **2021** night-time light layers.
- Navigate to major UK urban centres using **FlyTo** buttons.
- Explore the spatial structure of night-time light intensity in 3D.
- Compare urban agglomerations and regional differences.

Example cities included in the navigation interface:

- London
- Birmingham
- Manchester
- Leeds
- Newcastle
- Edinburgh

---

## Key Findings

The 3D visualisation shows that night-time light intensity across most major UK urban areas remained relatively stable between 2015 and 2021. This suggests that many large cities already had mature urban lighting and infrastructure patterns during this period.

However, some areas show noticeable localised changes. In particular, the Cardiff area displays a visible increase in brightness, which may suggest local urban development, increased economic activity or changes in lighting infrastructure.

Overall, the project demonstrates that interactive 3D web visualisation can help communicate subtle regional differences in urban activity patterns more effectively than static maps.

---

## Technical Stack

- **QGIS**
- **Mapbox Studio**
- **Mapbox GL JS**
- **HTML**
- **CSS**
- **JavaScript**
- **GeoJSON**
- **VIIRS Nighttime Lights**
- **ONS UK boundary data**

---

## Repository Structure

| File | Description |
| --- | --- |
| `index.html` | Main web map file used for GitHub Pages deployment |
| `Spatio-Temporal Analysis of UK Night Lights (2015-2021).html` | Original HTML version of the visualisation |
| `Spatio-Temporal Analysis of UK Night Lights (2015-2021).pdf` | Project report / exported assessment document |
| `Spatio-Temporal Analysis of UK Night Lights (2015-2021).docx` | Word version of the project report |
| `uk_2015.geojson` | Processed 2015 UK night-time light grid data |
| `uk_2021.geojson` | Processed 2021 UK night-time light grid data |
| `Introduction.docx` | Project introduction and methodological notes |

---

## Limitations

This project is designed primarily as a visualisation and exploratory spatial communication exercise. Several limitations should be considered:

- Night-time lights are only a proxy for urbanisation and economic activity.
- Changes in brightness may reflect lighting infrastructure, sensor conditions or data processing differences, not only socio-economic change.
- The 5 km grid smooths local variation and may obscure fine-scale urban patterns.
- The project focuses on visual comparison rather than statistical modelling.
- Interpretation should therefore be exploratory rather than causal.

---

## Relevance

This project demonstrates skills in:

- Raster-to-vector geospatial processing
- QGIS-based zonal statistics
- Coordinate reference system transformation
- GeoJSON preparation for web mapping
- Mapbox Studio tileset workflow
- Mapbox GL JS 3D visualisation
- Interactive spatial storytelling
- Urban data communication

It is relevant to research and applied work involving **urban data visualisation, Web GIS, smart city dashboards, spatial storytelling and interactive geospatial applications**.

---

## References

1. Earth Observation Group, Payne Institute for Public Policy. (2022). *VIIRS Nighttime Light (VNL) V2*. Colorado School of Mines.  
   https://eogdata.mines.edu/products/vnl/

2. Office for National Statistics. (2021). *Local Authority Districts (May 2021) Boundaries UK BGC*. ONS Geography Open Data.  
   https://geoportal.statistics.gov.uk/

3. Mapbox. (2024). *Mapbox GL JS Documentation*.  
   https://docs.mapbox.com/mapbox-gl-js/
