# Hazards Thrust

# Contents
 - [Data Management](#data-management) 
 - [Code Management](#code-management)
 - [Description Version 1.0 Dataset, 5 Jun 2024](#description-version-1.0-dataset,-5-Jun-2024)
   - [General Computational Process](#general-computational-process) 
   - [File Header](#file-header)
 - [Prior versioning notes](#prior-version-notes) 

# Data Management
Dataset location: DesignSafe 
- [V1.0, North Carolina](https://www.designsafe-ci.org/data/browser/projects/1798100155562136046-242ac117-0001-012/Hazards%2FNC_Present_0_v1.zip) 

# Hazard Model Information
General Information:
 - ADCIRC
   - Source: https://github.com/adcirc/adcirc
   - General info: https://wiki.adcirc.org/Main_Page, https://www.adcirc.org, https://www.adcircpredition.org 
 - P-Cliper
 - CREST

## Version 1.0 Model configuration:
North Carolina
 - ADCIRC
 - CREST
 - P-Cliper

See below for previous version details.

# Description Version 1.0 Dataset
Posting date: 5 Jun 2024

The version 1.0 of the Hazards Thrust contains the hazard model output (response) for each hurricane event impacting the North Carolina coast from the first 1000 years of the STORM stochastic / synthetic dataset for the present climate. 

The STORM dataset is described in the references below. 

Dataset location: DesignSafe  [here.](https://www.designsafe-ci.org/data/browser/projects/1798100155562136046-242ac117-0001-012/Hazards%2FNC_Present_0_v1.zip) 

## General computational process 
For each track in {STORM dataset for NC, for the present climate}:
1. OU: run CREST to generate:
- Time series of river flows for input into ADCIRC
- Maximum inland inundation field 
- Both posted for UNC to retrieve and place in the computational workflow
2. UNC: run ADCIRC to:
- Compute storm surge using meteorological forcing plus the river flow
- Generate maximum water level surface (water level above MSL)
- Generate maximum overland inundation (water level above ground)
3. UNC: Generate simulation "data package" for downstream uses:
- Interpolate triangular ADCIRC output to CREST grid
- Compute time history of wind velocity and mean sea level pressure from track parameters:
  - Uses a modified Holland vortex model 
  - Evaluated on the CREST grid
  - Computes open-water and open-terrain wind speeds
  - Max wind speeds from time histories of wind velocities
- Package up the max wind, surge and inundation levels into one csv file 


## File Header
Each file has a header defined as: 
```
# Project: NSF-CHEER
# FileDate: 18-Sep-2023 12:06:38
# StormID: NC_Present_0_01454
#
# Columns are:
#    1: Longitude, decimal degrees
#    2: Latitude, decimal degrees
#    3: Maximum Wind Speed, meters/sec, 10-meter, Open Terrain-Adjusted
#    4: Maximum Wind Speed, meters/sec, 10-meter, MSL
#    5: Maximum Inundation Level, meters above terrain, dry == -9999 meters
#    6: Maximum Surge Water Level, meters MSL, dry == -9999 meters
#    7: Maximum Surge Inundation Level, meters above terrain, dry == -9999 meters
#
-81,33.5,5.90501837061405,8.49234989753118,-9999,-9999,-9999
etc etc
```

## Units 
 - Wind speeds are m/s, at a vertical level 10-meter, and representing a 10-minute averaging period.  Both open-terrain and open-water are provided.

 - Water levels (columns 5-7) are in meters relative to either the ground / terrain level (for inundation) or MSL for the Surge Water Level. 
Dry values are indicated with a flag of -9999.  

### Variable definitions:
Maximum Inundation Level [meters above terrain, dry == -9999 meters] - Computed by CREST as the highest precipitation-driven water level above ground level.  A value of -9999 indicates no accumulated rainfall at the location.

Maximum Surge Water Level [meters MSL, dry == -9999 meters] - Computed by ADCIRC as the highest water level reached (during the simulation) above the mean sea level (MSL) datum. MSL is the vertical datum used to define the topographic heights and bathymetric depths of the ADCIRC grid nodes.  A value of -9999 indicates no "storm surge" at the location.  I.e., the location never got wetted during the simulation.

Maximum Surge Inundation Level [meters above terrain, dry == -9999 meters] - Computed by ADCIRC as the maximum water depth reached (during the simulation) above ground level for ADCIRC nodes that are "land" nodes.  Ground level in this case is ADCIRC's representation of the topographic height, and may not be the same as the CREST model's topography.  

# STORM Synthetic Hurricane Dataset(s) references
The 10,000 year TC STORM dataset, based on the present climate, is publicly accessible and can be found on the 4TU.Centre for Research Data repository (https://doi.org/10.4121/uuid:82c1dc0d-5485-43d8-901a-ce7f26cda35d). The dataset is split in separate files per basin, with each .txt-file containing 1,000 years of simulations (i.e. 10 files per basin). Each .txt-file consists of a series of arrays, with each array being a single time step (3-hourly) for a synthetic TC. The colmns of the arrays are given in this table:

Bloemendaal, Nadia; Haigh, I.D. (Ivan); de Moel, H. (Hans); Muis, S; Haarsma, R.J. (Reindert) et. al. (2022): STORM IBTrACS present climate synthetic tropical cyclone tracks. Version 4. 4TU.ResearchData. dataset. https://doi.org/10.4121/12706085.v4

Bloemendaal, Nadia; de Moel, H. (Hans); Martinez, Andrew B.; Muis, S. (Sanne); Haigh, I.D. (Ivan) et. al. (2023): STORM Climate Change synthetic tropical cyclone tracks. Version 2. 4TU.ResearchData. dataset. https://doi.org/10.4121/14237678.v2

 - https://www.nature.com/articles/s41597-020-0381-2
 - https://doi.org/10.4121/uuid:82c1dc0d-5485-43d8-901a-ce7f26cda35d
 - https://data.4tu.nl/articles/STORM_IBTrACS_present_climate_synthetic_tropical_cyclone_tracks/12706085?file=24876980

# Prior Version Notes 

V0: 
