# Identification of Manual Recommended Tracks for Maritime Navigation

## Overview

This project presents a computational framework for identifying potential undocumented shallow-water navigational corridors using historical vessel trajectory data and S-57 hydrographic chart information.

The system combines spatial trajectory analysis, computational geometry, graph-based clustering, density estimation, and raster-based structure extraction methods to reconstruct navigational pathways from noisy real-world vessel movement observations.

The project was developed as part of a Master's thesis focused on spatial machine learning, trajectory mining, and geometry-based reconstruction methods for maritime navigation.

---

## Project Objectives

The primary objective of this project is to:

* Detect recurrent navigational corridors from historical vessel trajectory data
* Identify shallow-water passages potentially missing from existing recommendation systems
* Integrate hydrographic chart information with trajectory observations
* Reconstruct representative navigational centerlines from noisy spatial movement data
* Evaluate the reliability and directional consistency of extracted corridors

---

## Methodology

The analytical pipeline combines multiple stages of spatial and geometric processing.

### 1. Data Preparation

* Spatial harmonization of trajectory and hydrographic datasets
* Extraction of shallow-water regions from S-57 bathymetric data
* Trajectory segmentation and cleaning
* Duplicate removal and land-intersection filtering

### 2. Trajectory Similarity Analysis

Trajectory similarity is evaluated using the **Discrete Fréchet Distance (DFD)**, a shape-aware geometric similarity metric preserving both spatial proximity and trajectory ordering.

### 3. Graph-Based Clustering

Trajectory relationships are represented as a graph structure where:

* Nodes represent trajectories
* Edges represent similarity relationships

Connected component analysis is then used to identify recurrent movement structures.

### 4. Corridor Identification

Kernel Density Estimation (KDE) is applied to clustered trajectories to construct continuous spatial density surfaces representing concentrated vessel movement.

### 5. Corridor Extraction

Representative navigational centerlines are extracted using:

* Ridge extraction
* Skeletonization
* Spline interpolation

These methods transform noisy trajectory-derived density surfaces into simplified geometric corridor representations.

### 6. Directional and Reliability Analysis

The framework additionally evaluates:

* Directional consistency
* Vessel diversity
* Tidal dependency
* Corridor reliability 

### 7.Spatial Constraint Assessment

* Proximity to surrounding land masses
* Corridor confinement characteristics
* Spatial context of vessel movement

---

## Computational Geometry and Spatial Processing

The project incorporates several computational geometry and spatial reconstruction concepts:

* Trajectory similarity analysis
* Graph topology and spatial connectivity
* Raster-based density surface reconstruction
* Ridge extraction
* Skeletonization
* Spatial interpolation
* Geometric centerline reconstruction
* Directional vector analysis


---

## Technologies Used

### Programming Language

* Python

### Geospatial Processing

* GeoPandas
* Shapely
* PyProj
* Rasterio

### Data Processing

* Pandas
* NumPy

### Machine Learning / Analysis

* Skimage
* SciPy

### Graph Analysis

* NetworkX

### Visualization

* Matplotlib
* QGIS

---

## Dataset Description

The project integrates three primary data sources:

### Historical Vessel Trajectories

Large-scale vessel movement observations collected from navigation application users.

### S-57 Hydrographic Data

Electronic Navigational Chart (ENC) data containing:

* Bathymetry
* Coastlines
* Land polygons
* Navigational information

### Recommended Track Data

Existing manually recommended navigational routes used for comparative evaluation.

### Data Availability

The datasets used in this project are not publicly available due to privacy, licensing, and data-sharing restrictions associated with the original maritime trajectory and navigational data sources. Consequently, the raw datasets are not distributed as part of this repository.

This repository provides the implementation code and methodological framework used throughout the project. Where possible, the codebase has been structured to support adaptation to alternative geospatial trajectory datasets.

---

## Repository Structure

```text
.
├── data/
│   ├── raw/
│   ├── processed/
│   └── outputs/
│
├── notebooks/
│   ├── preprocessing/
│   ├── clustering/
│   ├── corridor_extraction/
│   └── evaluation/
│
├── src/
│   ├── preprocessing/
│   ├── similarity/
│   ├── clustering/
│   ├── extraction/
│   ├── evaluation/
│   └── visualization/
│
├── figures/
├── requirements.txt
└── README.md
```

---

## Example Workflow

```text
Trajectory Data + S-57 Data
            ↓
Spatial Filtering
            ↓
Trajectory Similarity Analysis
            ↓
Graph-based Clustering
            ↓
Kernel Density Estimation
            ↓
Corridor Extraction
            ↓
Directional Analysis
            ↓
Cross-reference with Exisiting Reccomendations
            ↓
Reliability Assessment
            ↓
Spatial Constraint Assessment
            ↓
Visaulization 
            ↓
Candidate Navigational Corridors
```

---

## Research Context

This work was conducted as part of a Master's thesis exploring:

* Spatial trajectory mining
* Geometric representation extraction
* Spatial machine learning
* Reconstruction from noisy observations
* Maritime navigation analytics

---

## Limitations

Several limitations should be considered:

* Computational cost for large-scale pairwise trajectory comparisons
* Incomplete vessel metadata
* Potential GNSS positional inaccuracies
* Variability in trajectory sampling density
* Regional limitations of hydrographic chart coverage

The project should therefore be interpreted as a research-oriented proof-of-concept rather than a production-ready navigational system.

---

## Future Work

Potential future extensions include:

* Integration of deep learning and geometric learning methods
* Automatic parameter optimization
* Improved trajectory representation learning
* Real-time corridor detection
* Extension toward 3D spatial reconstruction methods
* Integration with computer vision and raster-based segmentation pipelines

---

## Author

Agata Zabuska

Master's Thesis Project

---

## License

This project is licensed under the MIT License.  
You are free to use, modify, and distribute this software in accordance with the terms of the MIT License.
