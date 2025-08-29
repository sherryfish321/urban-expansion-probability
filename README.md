# Urban Expansion Probability Mapping (Rio de Janeiro, Brazil)

## 📌 Project Overview
This project demonstrates a **data pipeline for urban expansion risk analysis** using open geospatial datasets.  
It aligns with research assistantship requirements in geospatial modeling and biodiversity by showcasing:
- Geospatial data processing with **GeoPandas** and **Rasterio**
- Change detection from **ESA WorldCover (2020–2021)**
- A probability model of urban expansion using **Logistic Regression**
- Visualization of high-risk areas with **Folium interactive maps**

---

## 📂 Project Structure

urban-expansion-probability/
- data/ # Source data (not included, see Data Sources below)
- notebooks/ # Jupyter/Colab notebooks
- results/ # Model outputs and maps
- geoproject.py # (Optional) Python script version
- requirements.txt # Dependencies
- README.md

---

## ⚙️ Methods
1. **Data Acquisition**  
   - ESA WorldCover 2020 & 2021 Land Cover Maps (`.tif`)  
   - GADM Level-2 administrative boundaries for Rio de Janeiro  

2. **Preprocessing**  
   - Reproject shapefile to match raster CRS  
   - Clip WorldCover rasters to AOI (Rio de Janeiro)  
   - Generate regular sampling points within AOI  

3. **Feature Engineering**  
   - Land cover type in 2020 (one-hot encoded)  
   - Distance to city center  

4. **Modeling**  
   - Logistic Regression with balanced class weights  
   - Target label: **non-urban (2020) → urban (2021)**  

5. **Visualization**  
   - Predicted probabilities mapped on **Folium interactive map**  
   - Exported HTML + static PNG for quick inspection  

---

## 📊 Results
- **ROC-AUC**: ~0.8 (demo results, depending on sampling density)  
- **High-probability hotspots** identified on Rio’s urban fringe  
- **Outputs**:  
  - `results/risk_map.html` – interactive web map  
  - `results/risk_map.png` – static preview  
  - `results/predictions_points.csv` – model outputs for each sampled point  

---

## 🔗 Data Sources
- ESA WorldCover: [https://esa-worldcover.org/en](https://esa-worldcover.org/en)  
- GADM Administrative Boundaries: [https://gadm.org/](https://gadm.org/)  

---

## 🛠️ Tech Stack
- Python (GeoPandas, Rasterio, Shapely, Scikit-learn)  
- Folium (interactive maps)  
- Jupyter/Google Colab  

