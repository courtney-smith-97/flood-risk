# Flood Risk EDA
---

## Data
Datasets were compiled using raster images and feature sets in the New York City Metropolitan area.
- [Land Cover Raster Data](https://data.cityofnewyork.us/Environment/Land-Cover-Raster-Data-2017-6in-Resolution/he6d-2qns)
  - Contains 6-inch resolution raster images with 8 classes of land cover types, including water, road cover, and green spaces.
- [NYC Planimetric Database](https://github.com/CityOfNewYork/nyc-planimetrics/blob/master/Capture_Rules.md#imagery-and-data-specifications)
  - Contains metadata of the NYC metropolitan area maintained by the NYC Department of IT and Telecommunications. Contains structure, water feature, and elevation data. Features used:
  - [Elevation](https://data.cityofnewyork.us/City-Government/1-foot-Digital-Elevation-Model-DEM-Integer-Raster/7kuu-zah7)
    - Type: 1ft resolution raster
  - [Hydrography](https://data.cityofnewyork.us/Environment/Hydrography/drh3-e2fd)
    - Type: Polygon
  - [Retaining Walls](https://data.cityofnewyork.us/City-Government/Retaining-Wall/uvgd-xsc8)
    - Type: Polyline
- [Contour Map](https://data.cityofnewyork.us/City-Government/Contours/3cdm-p29e)
  - Layer containing 2-ft contour line features
  - Type: Polyline
- [Catch Basins](https://data.cityofnewyork.us/Environment/NYCDEP-Citywide-Catch-Basins/vu7w-gbbe)
  - Type: Point
- [Subway Entrances](https://data.cityofnewyork.us/Transportation/Subway-Entrances/drex-xx56)
  - Type: Point
- [Tidal Shoreline](https://data.cityofnewyork.us/Environment/Tidally-Coordinated-Shoreline/pawq-tjb4)
  - Type: PolylineZ

## Features and EDA
Feature creation will be essential during modeling stages and should include both data from collected planimetric and land cover datasets and features engineered from those datasets to isolate risk factors in flood inundation.

Key features will help the model isolate types of risk including flood inundation, water absorption, drainage, and physical protection.

Key features:
- Elevation
- Land cover type
- Height above nearest drainage
- Distance to water features
  - Rivers
  - Coastline
  - Lakes
- Barriers to water flow
  - Retaining walls
  - Seawalls
