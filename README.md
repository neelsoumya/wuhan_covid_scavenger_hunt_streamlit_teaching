# ⬡ Outbreak Investigator

An interactive epidemiological source-tracing tool built with Streamlit and Folium. Generates synthetic case data clustered around a hidden origin point, then challenges the user to identify the source from a set of candidate locations.

Originally written as a Jupyter notebook demonstration; converted to a fully interactive Streamlit app.

> **All case data is synthetic.** This tool is for educational and demonstration purposes only.

---

## Features

- **Heatmap visualisation** of case density across Wuhan using Folium
- **Configurable simulation** — adjust total case count, cluster percentage, and spatial spread in real time
- **Points of Interest markers** representing candidate source locations
- **"Reveal true source" toggle** for use as a teaching or demo tool
- **Dark terminal aesthetic** designed around the investigative theme

---

## Quickstart

```bash
# 1. Clone or download the repo
git clone <your-repo-url>
cd outbreak-investigator

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app
streamlit run wuhan_investigation.py
```

The app will open at `http://localhost:8501`.

---

## Project Structure

```
.
├── wuhan_investigation.py   # Main Streamlit application
├── requirements.txt         # Python dependencies
└── README.md
```

---

## Sidebar Controls

| Control | Description |
|---|---|
| Total cases | Number of synthetic cases to generate (100–1000) |
| Cluster % | Proportion of cases clustered near the true source |
| Cluster spread | Spatial standard deviation of the cluster (in km) |
| Heatmap | Toggle heatmap layer on/off |
| Points of Interest | Toggle POI markers on/off |
| Reveal true source | Highlights the true origin site in red |
| Heat radius / blur | Folium HeatMap rendering parameters |
| Tile layer | Switch between dark, light, and OSM basemaps |

---

## Dependencies

| Package | Purpose |
|---|---|
| `streamlit` | App framework and UI |
| `streamlit-folium` | Renders Folium maps inside Streamlit |
| `folium` | Interactive Leaflet.js map with HeatMap plugin |
| `pandas` | DataFrame handling for cases and POIs |
| `numpy` | Synthetic data generation |

---

## Licence

GNU-GPL3
