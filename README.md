# Aerial Imagery Extraction
The aim of this project is to gather high quality aerial imagery of Victoria, Australia using free services and open source libraries.
# Requirements (python3)
* `fiona`
* `shapely`
* `pandas`
* `numpy`
* `rtree` (you will also have to install spatial index shared library)

# Installing spatialindex on Linux
```sh
brew install spatialindex
```

# Process/thinking behind this project
1. Acquire bounding box for victoria
2. Define an `offset` using an online aerial imagery tool, this variable will be used to space images apart just enough so they overlap a little.
3. Create a box full of coordinates within the ranges of victorias bounding box
4. Filter out coordinates not within victorias boundaries using the ESRI Local Government Areas shape file.
5. After consolidating points separated by a certain `offset` within the boundaries of victorian LGAs, use these points to create geocoded images using an online tool.
6. Automate pulling of images from an online aerial/satellite imagery tool, perhaps with selenium.

# Concerns / Blockers
The amount of points generated in this project may be too time consuming to even automatically generate imagery from a website interface.

# Notebooks
1. `Phase 1 - Find Victorias Bounding Box.pynb` - Used to explore the shape files, and generate victorias bounding box.
2. `Phase 2 - Create Points, Filter Points.pynb` - Used to generate coordinates baseed on predefined offsets and filter those points using the shape file boundaries and spatial index (rtree).
