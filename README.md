# Denver Land Use
A parcel-based land use summary of the Denver region

## License

This data is free for research and any other potential use with attribution to the author – Garrett Fardon

## Last Updated

2025-08-25

## Projected Coordinate System

NAD 1983 HARN StatePlane Colorado Central FIPS 0502 (US Feet)

WKID: 2877

## Sources

**Colorado Public Parcels** ([link](https://cooit.maps.arcgis.com/home/item.html?id=3245c94414124882b331e35c14bb23a4)): Aggregated by the Governor's Office of Information Technology Geospatial Information Systems, contains all public parcels in the state, including land use codes supplied by counties and other jurisdictions. Sourced on 7/9/2025.

**Zoning 2023** ([link](https://data.drcog.org/dataset/zoning-2023)): Zoning shapefile sourced from DRCOG, used to supply possible ‘land use’ (with zoning classifications standing in for land use) where land use codes were not provided in the Colorado Public Parcels file.

## Land Use Categorizations

Below are the land use codes I categorized parcels by

| **Standardized Land Use Code** | **Description** |
| --- | --- |
| Residential | Any residence land use (single family, multi-unit, senior) |
| Zoning Follow Up | Should not be in the final dataset- used to indicate there's no land use data and needs to be backfilled with zoning classifications |
| Vacant | Parcel indicated as vacant |
| Commercial | Any commercial use, including office, retail |
| Exempt/Government | Exempt land use or government land use (eg: city hall, fire station) |
| Agricultural | Agricultural, or ranch use |
| Other/Unknown | Some other use/cannot be determined |
| Industrial | Industrial, including meat packing |
| School | Schools (K-12, college, public and private) |
| Mixed Use | A parcel specifically marked as mixed use |
| Open Space/Parks/Recreation | Open space, park, outdoor recreation (eg: cabins, camping, etc) |
| Medical | Hopsitals, medical offices, etc |

## Caveats

- Many parcels did not contain land use codes or contained land use codes that could not be discerned. In that case, zoning designations were appended to estimate the land use.
- Even with the above process, many parcels were missing a land use classification

## Files & Feature Layers

**Land Use Parcel Standardization.xlsx**: A spreadsheet where I standardized land use codes into the categories above. The tab \`Land Use Codes\` is where categorizations were based on the parcels’ land use codes and descriptions, while \`Zoning Code Follow Up\` used the zoning classification that had greatest geographic overlap with the parcel.

**public_parcel_drcog.shp**: The original Colorado Public Parcels file, with the majority-overlapping zoning code from Zoning 2023 added, and the land use categorizations from Land Use Parcel Standardization appended.

**parcel_land_use.shp**: A final feature class, derived from public_parcel_drcog and dissolved by the zoning categorization appended from Land Use Parcel Standardization.

**Land Use Data.gdb**: Contains all the above feature classes