# NSI Joint Inventory v1.1 Processing

## Metadata

**Dataset:** NSI Joint Inventory v1.1  
**Author:** Jingya Wang  
**Project:** CHEER Hub STARR Framework  
**Last updated:** 2026  

---

## Overview

This document describes the preprocessing steps used to construct the **NSI Joint Inventory v1.1** used in the STARR loss modeling framework.

The inventory is derived from the **National Structure Inventory (NSI)** dataset. NSI attributes are based on **American Community Survey (ACS) 5-year estimates (2018–2022)** and represent building and household conditions approximately around **2022**.

The original NSI dataset contains **person-level records linked to buildings** and includes multiple building types and occupancy categories. Several preprocessing steps are required to convert the dataset into the format required by the loss model.

The final processed dataset is saved as

```
nsi_joint_inventory_v1p1.parquet
```

and contains **single-family residential buildings with standardized structural attributes**.

---

## Processing Workflow

```
NSI raw dataset (ACS 2018–2022)
        ↓
Convert person-level records to building-level records
        ↓
Remove vacant structures
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
```

---

## Processing Steps

### 1. Person-level to Building-level Conversion

The NSI dataset includes multiple rows per building because demographic attributes are attached at the person level.

Duplicate rows were removed using the building identifier

```
fd_id_nsi
```

After this step, each row corresponds to **one building**.

---

### 2. Removal of Vacant Structures

Buildings flagged as **vacant** were removed to ensure the inventory represents **occupied housing units**.

---

### 3. Occupancy Harmonization

The NSI dataset provides detailed occupancy classifications through the `PRIM_OCC` field derived from `occtype_nsi`.

The mapping between the NSI occupancy codes and the descriptive categories is shown below.

| occtype_nsi | PRIM_OCC |
|-------------|----------|
| RES1-1SNB | Single Family Residential, 1 story, no basement |
| RES1-1SWB | Single Family Residential, 1 story, with basement |
| RES1-2SNB | Single Family Residential, 2 story, no basement |
| RES1-2SWB | Single Family Residential, 2 story, with basement |
| RES1-3SNB | Single Family Residential, 3 story, no basement |
| RES1-3SWB | Single Family Residential, 3 story, with basement |
| RES1-SLNB | Single Family Residential, split-level, no basement |
| RES1-SLWB | Single Family Residential, split-level, with basement |
| RES2 | Manufactured Home |
| RES3A | Multi-Family housing 2 units |
| RES3B | Multi-Family housing 3-4 units |
| RES3C | Multi-Family housing 5-10 units |
| RES3D | Multi-Family housing 10-19 units |
| RES3E | Multi-Family housing 20-50 units |
| RES3F | Multi-Family housing 50 plus units |
| RES4 | Average Hotel |
| RES5 | Institutional Dormitory |
| RES6 | Nursing Home |

For compatibility with the STARR loss model, only **single-family residential structures** were retained.

Specifically, buildings corresponding to the following categories were kept:

- RES1-1SNB  
- RES1-1SWB  
- RES1-2SNB  
- RES1-2SWB  
- RES1-3SNB  
- RES1-3SWB  
- RES1-SLNB  
- RES1-SLWB  

These categories were simplified into a single occupancy class used in the loss model:

```
PRIM_OCC = "Single Family Dwelling"
```

All other occupancy categories were excluded, including:

- Manufactured homes (`RES2`)
- Multi-family housing (`RES3A` – `RES3F`)
- Hotels (`RES4`)
- Institutional dormitories (`RES5`)
- Nursing homes (`RES6`)

---

### 4. Roof Shape Filtering and Reassignment

The loss model supports only a limited set of roof geometries.

#### Supported roof shapes

- Cross Gable  
- Gable  
- Complex Gable  
- Cross Hip  
- Hip  

#### Unsupported roof shapes

- Unknown  
- Mobile Homes  
- No Structure  
- Flat  

Buildings with unsupported roof shapes were not removed. Instead, roof shapes were reassigned using **nearest-neighbor spatial imputation**.

Procedure:

1. Buildings with supported roof shapes were treated as **donor buildings**
2. Buildings with unsupported roof shapes were treated as **target buildings**
3. Each target building was assigned the roof shape of the **nearest donor building**

This preserves the full spatial distribution of buildings while ensuring compatibility with the loss model.

---

### 5. Structural Type Standardization

The loss model uses a simplified structural classification.

All buildings were assigned

```
bldgtype = "W"
```

which represents **wood-frame residential structures**.

Wood-frame construction is the dominant structural type for single-family housing in the study region.

---

### 6. Structural Attribute Cleaning

Structural attributes were standardized to match the required loss model format.

Adjustments include:

- `Story_AI` clipped to **1–2 stories**
- `Garage` converted to a **binary indicator**
- Numeric fields converted to numeric types
- Rows missing required attributes removed

Required fields include:

- bldgtype
- roof_shape_1
- Story_AI
- Garage
- PRIM_OCC
- med_yr_blt
- Coast_D (miles)
- val_struct
- val_cont
- geometry

---

### 7. Geometry Processing

Original geometry stored as **WKB bytes** was converted to **Shapely geometry objects** and saved as **GeoParquet**.

Coordinate reference system:

```
EPSG:4326
```

---

## Final Dataset

Output file

```
nsi_joint_inventory_v1p1.parquet
```

Each row represents a **single residential building**.

### Key attributes

| Field | Description |
|------|-------------|
| bldgtype | Structural type (wood-frame) |
| roof_shape_1 | Roof geometry |
| Story_AI | Number of stories |
| Garage | Garage indicator |
| PRIM_OCC | Occupancy type |
| med_yr_blt | Median construction year |
| Coast_D (miles) | Distance to coastline |
| val_struct | Structure value |
| val_cont | Content value |
| geometry | Building location |

---

## Notes and Limitations

- The NSI dataset reflects **conditions around 2022** based on **ACS 2018–2022 averages**
- Roof shapes for unsupported categories were **imputed using nearest-neighbor assignment**
- Structural type was standardized to **wood-frame ("W")**
- The dataset represents **baseline inventory conditions** and does not include buildings constructed after the ACS sampling period

---

## Related Files

Raw inventory input

```
Joint_HH_Inventory_NSI_East_NC_V1.parquet
```

Intermediate inventory

```
inventory_for_loss_model.parquet
```

Final inventory

```
nsi_joint_inventory_v1p1.parquet
```
