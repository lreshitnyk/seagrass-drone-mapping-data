# Time Series of Eelgrass (*Zostera marina*) Extent Derived from Drone Surveys, Central Coast, British Columbia

[![CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![DOI](https://img.shields.io/badge/DOI-10.21966%2F03pw--2190-blue)](https://doi.org/10.21966/03pw-2190)

## Summary

This repository contains a time series of eelgrass (*Zostera marina*) meadow extent derived from remotely piloted aerial system (RPAS/drone) surveys along British Columbia's Central Coast, spanning 2015–2025.

Surveys are conducted annually or biannually during low-tide windows at long-term Hakai Institute monitoring sites. High-resolution RGB orthomosaics are used to delineate eelgrass extent using object-based image analysis (OBIA) and manual GIS methods, with a minimum mapping unit of 4 m². Outputs are reviewed by trained analysts and delivered as vector polygon features in NAD83 UTM Zone 9N.

## Monitoring Sites

Core monitoring sites are mapped annually or biannually. Additional sites have been mapped opportunistically or as part of shorter-term projects and are included in the dataset.

| Site Name           | Latitude    | Longitude     | Survey Frequency  |
|---------------------|-------------|---------------|-------------------|
| Pruth Bay           | 51.645614°  | -128.119975°  | Annual            |
| Choked Pass         | 51.673388°  | -128.118387°  | Annual            |
| Koeye               | 51.780988°  | -127.869248°  | Annual            |
| Triquet Bay         | 51.808600°  | -128.236102°  | Annual         |
| Goose SW            | 51.923913°  | -128.467971°  | Biannual          |
| McMullin North      | 52.061502°  | -128.413301°  | Biannual          |
| Underhill           | 51.770577°  | -128.059800°  | Opportunistic     |
| Stirling Bay        | 51.750023°  | -128.105737°  | Opportunistic     |
| Nalau               | 51.750656°  | -128.030805°  | Opportunistic     |
| West Bay McNaughton | 51.954961°  | -128.231514°  | Opportunistic     |
| Goose Grass Bay     | 51.659071°  | -128.117477°  | Opportunistic     |
| Triquet North       | 51.808379°  | -128.247389°  | Opportunistic     |

## Data

Data are provided as a compressed geodatabase (`.gdb.zip`) in `data/`. The geodatabase contains:

- **Eelgrass extent polygons** — annual delineations of *Z. marina* meadow extent at each monitoring site
- **Area of interest (AOI) polygons** — consistent survey boundaries enabling temporal comparison
- **Monitoring site locations** — point features for each long-term site

Data dictionaries for each layer are provided as CSV files in `docs/`.

## Methods

RPAS surveys are conducted annually during morning low tides (winds < 19 kt, no rain) using a small, commercially available drone (DJI Phantom 3 Pro, DJI Phantom 4 Pro, DJI Mavic 3E). Imagery is collected following automated grid flight plans (Pix4D Capture App, Map Pilot, or DJI Go 4) to ensure complete site coverage with sufficient photo overlap. Flight altitude is set to maximise detail and meet ground sampling distance (GSD) specifications.

Orthomosaics are generated using a Structure from Motion Multi-View Stereo (SfM-MVS) workflow (Pix4Dmapper, DroneDeploy, or Agisoft Metashape Pro) and georeferenced using ground control points collected during the survey or co-registered to a reference orthomosaic.

Eelgrass extent is delineated using a combination of object-based image analysis (OBIA) in eCognition Developer 9 and manual delineation in ArcMap (v10.8). Segmentation outputs are imported into ArcGIS, where objects are classified as eelgrass by a trained analyst based on photo-interpretive characteristics. Where segmentation performs poorly, segments are removed and redrawn manually. Where available, towed underwater video data are used to aid image interpretation. A minimum mapping unit (MMU) of 4 m² is applied. A second analyst reviews and edits all delineations, and the final features are dissolved into a single polygon per site.

Areal extent data are provided as vector polygon features in NAD83 UTM Zone 9N, clipped to each site area of interest (AOI) to ensure consistent survey boundaries are compared over time, and published to a geodatabase. For further details on factors affecting mapping confidence, see Nahirnick et al. (2018).

## Citation

If you use this dataset, please cite:

> Reshitnyk, L., Guyn, A., Holmes, K., & Mai, T. (2026). Eelgrass (*Zostera marina*) extent at sites along the Central Coast, British Columbia. Hakai Institute. https://doi.org/10.21966/03pw-2190

A `CITATION.cff` file is included for machine-readable citation.

## Data Access & Attribution

This dataset is licensed under [CC-BY-4.0](LICENSE). You are free to share and adapt the data provided you give appropriate credit.

We ask that users:
- Provide attribution per the citation above
- Communicate and/or collaborate with Hakai if you are considering using this dataset for manuscripts or other forms of reporting
- Provide helpful feedback on data quality
- Report any data quality issues via GitHub Issues

For questions about the data, contact [data@hakai.org](mailto:data@hakai.org).

## References

Nahirnick, N. K., Reshitnyk, L., Campbell, M., Hessing-Lewis, M., Costa, M., Yakimishyn, J., & Lee, L. (2018). Mapping with confidence; delineating seagrass habitats using Unoccupied Aerial Systems (UAS). *Remote Sensing in Ecology and Conservation*, 5(2), 121–135. https://doi.org/10.1002/rse2.98

## Related Resources

- [Hakai Institute Nearshore Program](https://www.hakai.org/nearshore)
- [Dataset metadata record](https://doi.org/10.21966/03pw-2190)
- [Kelp drone mapping data (companion dataset)](https://github.com/HakaiInstitute/kelp-drone-mapping-data)
