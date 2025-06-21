# Roundabout Detection for Database Integration  

### Problem Statement :  
**Detecting Missing Roundabouts for Database Integration**

### Objective:
To detect roundabouts from provided geometry data and integrate them into the database. The challenge involves identifying roundabouts based on spatial patterns and geometry characteristics, even when attribute data is missing.

---

### Data Preprocessing Steps:

1. **Multipart to Singlepart:**  
   Converts multipart geometries to individual features for easier processing.

2. **Densify by Interval:**  
   Adds points at regular intervals on geometry edges to enhance circularity detection and polygon formation.

3. **Extract Nodes and Polygonize:**  
   Converts line geometries into closed polygons to detect enclosed features like roundabouts.

4. **Join Attributes by Location:**  
   Joins contextual attributes from nearby layers to detected roundabouts for further filtering and validation.

---

### Libraries Used:

- `geopandas`: For geospatial data processing
- `shapely`: Geometry operations (union, polygonization, etc.)
- `matplotlib`: Visualizing the geometries
- `os`: Directory and file management
- `fiona`: File input/output for spatial data

---

### Folder Structure:

Here/
├── HERE.ipynb # Jupyter notebook with data processing and analysis
├── polygon.qmd # Quarto Markdown summary of our process
├── polygon.shp # Shapefile (main geometry data)
├── polygon.dbf # Attribute data for shapefile
├── polygon.shx # Index file for shapefile
├── polygon.prj # Projection information
├── polygon.cpg # Encoding information
├── region 1.geojson # GeoJSON file for Region 1
├── region 2.geojson # GeoJSON file for Region 2
├── region 3.geojson # GeoJSON file for Region 3
├── Region 1.png # Visualization of Region 1
├── Region 2.png # Visualization of Region 2
├── Region 3.png # Visualization of Region 3


---


### Output:
- A map showing detected roundabouts.
- A GeoDataFrame that can be merged into the main roundabout database.

### Viewing GeoJSON Files
To view and validate the `.geojson` files visually:

1. Go to [https://geojson.tools/](https://geojson.tools/)
2. Click the "Upload" button or drag & drop any of the following files:
   - `region 1.geojson`
   - `region 2.geojson`
   - `region 3.geojson`
3. The geometries will be rendered on the interactive map.
