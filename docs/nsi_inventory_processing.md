NSI Joint Inventory v1.1 Processing
Metadata

Dataset: NSI Joint Inventory v1.1
Author: Jingya Wang
Project: CHEER Hub STARR Framework
Last updated: 2026

Overview

This document describes the preprocessing steps used to construct the NSI Joint Inventory v1.1 used in the STARR loss modeling framework.

The inventory is derived from the National Structure Inventory (NSI) dataset. NSI attributes are based on American Community Survey (ACS) 5-year estimates (2018–2022) and therefore represent building and household conditions approximately around 2022.

The original NSI dataset contains person-level records linked to buildings and includes multiple building types and occupancy categories. Several preprocessing steps are required to convert the dataset into the format required by the loss model.

The final processed dataset is saved as

nsi_joint_inventory_v1p1.parquet

and contains single-family residential buildings with standardized structural attributes.

Processing Workflow
NSI raw dataset (ACS 2018–2022)
        ↓
Remove vacant structures
        ↓
Convert person-level records to building-level records
        ↓
Filter single-family dwellings
        ↓
Standardize structural attributes
        ↓
Roof shape reassignment using nearest neighbor
        ↓
Set structural type = W (wood-frame)
        ↓
Export GeoParquet inventory
Processing Steps
1. Person-level to Building-level Conversion

The NSI dataset includes multiple rows per building, because demographic attributes are attached at the person level.

To convert the dataset to a building inventory, duplicate rows were removed using the building identifier:

fd_id_nsi

After this step, each row corresponds to one building.

2. Removal of Vacant Structures

Buildings flagged as vacant were removed from the dataset to ensure that the inventory represents occupied housing units.

This avoids including empty structures that would not participate in household-level decision models.

3. Occupancy Harmonization

NSI provides detailed occupancy descriptions. These categories were simplified to match the structural assumptions of the loss model.

Only single-family residential structures were retained.

Final filter applied:

PRIM_OCC = "Single Family Dwelling"

The following building types were excluded:

Multi-family housing

Dormitories

Hotels

Institutional buildings

Nursing homes

4. Roof Shape Filtering and Reassignment

The loss model supports only a limited set of roof geometries.

Supported roof shapes

Cross Gable

Gable

Complex Gable

Cross Hip

Hip

Unsupported roof shapes in the raw dataset

Unknown

Mobile Homes

No Structure

Flat

Instead of removing buildings with unsupported roof shapes, their roof shapes were reassigned using nearest-neighbor spatial imputation.

Procedure:

Buildings with supported roof shapes were treated as donor buildings.

Buildings with unsupported roof shapes were treated as target buildings.

Each target building was assigned the roof shape of the nearest donor building in geographic space.

This approach preserves the full building inventory while ensuring compatibility with the loss model.

5. Structural Type Standardization

The loss model uses a simplified structural classification.

All buildings were assigned the structural type

bldgtype = "W"

which represents wood-frame residential structures.

Wood-frame construction is the dominant structural type for single-family housing in the study region.

6. Structural Attribute Cleaning

Several structural attributes were standardized to match the required loss model format.

Adjustments include:

Story_AI clipped to 1–2 stories

Garage converted to a binary indicator

Numeric fields converted to numeric types

Rows missing required attributes removed

Required fields include:

bldgtype

roof_shape_1

Story_AI

Garage

PRIM_OCC

med_yr_blt

Coast_D (miles)

val_struct

val_cont

geometry

7. Geometry Processing

The original building geometry was stored as WKB byte objects.

These geometries were converted to Shapely geometry objects and saved as GeoParquet.

Coordinate reference system:

EPSG:4326
Final Dataset

Output file:

nsi_joint_inventory_v1p1.parquet

Each row represents a single residential building.

Key attributes
Field	Description
bldgtype	Structural type (wood-frame)
roof_shape_1	Roof geometry
Story_AI	Number of stories
Garage	Garage indicator
PRIM_OCC	Occupancy type
med_yr_blt	Median construction year
Coast_D (miles)	Distance to coastline
val_struct	Structure value
val_cont	Content value
geometry	Building location
Notes and Limitations

The NSI dataset reflects conditions around 2022 based on ACS 2018–2022 averages.

Roof shapes for unsupported categories were imputed using nearest-neighbor assignment, which introduces some uncertainty but avoids removing buildings.

Structural type was standardized to wood-frame ("W") to match the assumptions of the loss model.

The dataset represents baseline inventory conditions and does not include buildings constructed after the ACS sampling period.

Related Files

Raw inventory input:

Joint_HH_Inventory_NSI_East_NC_V1.parquet

Intermediate loss-model inventory:

inventory_for_loss_model.parquet

Final processed inventory:

nsi_joint_inventory_v1p1.parquet
