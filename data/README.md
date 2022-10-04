# Flood Risk EDA
---

## Data
Datasets were compiled using raster images and feature-sets in the New York City Metropolitan area.
- [NYC Planimetric Database](https://github.com/CityOfNewYork/nyc-planimetrics/blob/master/Capture_Rules.md#imagery-and-data-specifications)
  - Contains metadata of the NYC metropolitan area maintained by the NYC Department of IT and Telecommunications. Contains structure, water feature, and elevation data.
- [Land Cover Raster Data](https://data.cityofnewyork.us/Environment/Land-Cover-Raster-Data-2017-6in-Resolution/he6d-2qns)
  - Contains 6-inch resolution raster images with information on land cover types including shorelines, road cover, and green spaces.

## Features and EDA
Feature creation will be essential during modeling stages and should include both data from collected planimetric and land cover datasets and features created from those datasets to isolate risk factors in flood inundation.

Key features will help the model isolate types of risk including flood inundation, water absorption, water drainage, and physical protection.

Key features:
- Point elevation
- Land cover type
- Height above nearest drainage
- Distance to water features
  - Rivers
  - Coastline
  - Lakes
- Barriers to water flow
  - Retaining walls
  - Seawalls
