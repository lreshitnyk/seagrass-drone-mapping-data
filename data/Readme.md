# Data

This folder contains the eelgrass (*Zostera marina*) extent geodatabase.

## File

| File | Description |
|------|-------------|
| `CentralCoast_SeasonalDroneEelgrassPolygons.gdb.zip` | Compressed Esri geodatabase containing all eelgrass extent layers |

## Geodatabase Layers

| Layer name | Geometry | Description |
|------------|----------|-------------|
| `CentralCoast_DroneEelgrassPolygons_Seasonal_[years]` | Polygon | Annual eelgrass meadow extent delineations at each monitoring site |
| `Hakai_CentralCoast_Permanent_eelgrass_monitoring_sites_locations` | Point | Long-term monitoring site reference locations |
| `Hakai_Drone_AOIs` | Polygon | Area-of-interest boundaries used to standardize survey extent across years |

Data dictionaries for each layer are in the `docs/` folder.

## Coordinate System

NAD83 UTM Zone 9N (EPSG: 26909)
