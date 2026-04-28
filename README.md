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




# 🦠 Outbreak Investigator


An interactive epidemiological source-tracing exercise built with **Streamlit** and **Folium**. The app generates synthetic case data clustered around a hidden origin point, then challenges students to identify the true source from a set of candidate locations on a map of Wuhan.

Designed as a live teaching demo for introducing Streamlit concepts — students adjust sidebar sliders in real time and watch the map update instantly.

> **All case data is entirely synthetic.** This tool is for educational and demonstration purposes only and makes no claims about real-world events.

---

## What students will learn

| Concept | Where it appears in `simple_code.py` |
|---|---|
| Basic app structure (title → widgets → output) | Top-level `st.title` / `st.write` calls |
| Sidebar widgets | `st.sidebar.slider`, `st.sidebar.checkbox` |
| Streamlit's reactive execution model | Every slider change re-runs the whole script |
| Synthetic data generation | NumPy Normal + Uniform distributions |
| DataFrame manipulation | Pandas `pd.DataFrame`, `iterrows` |
| Interactive map rendering | Folium `HeatMap` + `Marker`, then `st_folium` |
| Conditional display logic | `show_source` checkbox toggling marker colour |

---

## Quickstart

```bash
# 1. Clone or download this folder
cd wuhan_covid_scavenger_hunt_streamlit_teaching

# 2. Install dependencies
pip install streamlit pandas numpy folium streamlit-folium

# 3. Run the app
streamlit run simple_code.py
```

The app will open automatically at `http://localhost:8501`.

- A more sophisticated version is in `wuhan_scavenger.py`


---

## Project structure

```
.
├── simple_code.py   # Main Streamlit application (heavily annotated)
└── README.md
```

---

## Sidebar controls

| Control | Type | Description |
|---|---|---|
| Total cases | Slider (100–1000) | Total number of synthetic cases to generate |
| % of cases near the source | Slider (10–90) | Proportion clustered around the true source; higher = easier to find |
| Reveal the true source | Checkbox | Turns the true-source marker red and labels it — the "answer key" |

---

## How the simulation works

Two populations of cases are generated and combined:

1. **Cluster cases** — drawn from a tight Gaussian distribution (σ ≈ 550 m) centred on the Huanan Seafood Market. These represent people exposed at or near the true source.
2. **Noise cases** — drawn from a wide Uniform distribution covering a large area of central Wuhan. These represent background community spread and data noise.

The mix of signal and noise makes the identification task non-trivial: students must read the heatmap density to distinguish the cluster from the background.

Four **Points of Interest** markers are shown as candidate sources (one correct, three red herrings):

- Wuhan International Plaza
- **Huanan Seafood Market** ← true source
- Hankou Railway Station
- Wuhan CDC

---

## Extension exercises

The annotated source code includes suggested exercises at the bottom. Short list:

1. Add a slider to control the spatial spread (standard deviation) of the cluster.
2. Add a `st.selectbox` to switch between map tile styles (dark, satellite, OSM).
3. Add a `st.download_button` that exports the cases DataFrame as a CSV.
4. Add `st.metric` cards showing cluster density (cases per km²).
5. Replace the fixed random seed (`np.random.seed(42)`) with a `st.number_input` so students can explore different random realisations.

---

## Dependencies

| Package | Purpose |
|---|---|
| `streamlit` | Web-app framework and all UI widgets |
| `streamlit-folium` | Embeds Folium maps inside Streamlit |
| `folium` | Interactive Leaflet.js maps with HeatMap plugin |
| `pandas` | DataFrame handling for cases and POIs |
| `numpy` | Synthetic data generation (Normal + Uniform distributions) |

---

## Licence

GNU-GPL3
