# CHEER Project Shovels Permit Data

If you plan to use this data, please ensure you fill out the [Data Usage Form](#data-usage-form) at the end of this document. There are only a few questions. This helps the entire team stay aligned with ongoing research and optimizes time and resources. Thanks!

## Contents
- [Original Data](#original-data)
- [Data Processing](#data-processing)
- [Feature Statistics](#feature-statistics)
- [Access Method (Jupyter Notebook)](#access-method-jupyter-notebook)
- [Data Usage Form](#data-usage-form)

## Original Data
**Dataset location:** DesignSafe  
- **Shovel Permit Data (Original):** [Link](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FBuildings%2FShovels_Permit_Data) These are the 'original' raw data, please **do not edit**, change, or delete these files.
- There are over 200 files with many attribute columns and ultimately tens of millions of data rows. Please use the processed data for analysis, see [Access Method (Jupyter Notebook)](#access-method-jupyter-notebook).
- If you can not access any of the links that take you to DesignSafe Data Depot, check to make sure you have an account on DesignSafe and that you have been added to the project.

## Raw Data Processing
This section covers two main aspects:  
1. **Data Cleaning and Error Correction** in the original dataset.  
2. **Data Re-structuring** for easier access.

### **Raw Data Cleaning**
The original dataset contains the following issues:

- **Swapped latitude and longitude values:**  
  Using the known range of latitude and longitude values in the **EPSG:4326** system, incorrect values were identified and corrected.

- **Inconsistent missing value notation:**  
  The original dataset used different formats to denote missing values. These have been standardized to the **NumPy missing value format** for consistency.

### **Raw Re-structuring Data**
The dataset initially lacked a specific order (e.g., by state). Since the `"STATE"` column has no missing values, the cleaned dataset has been **grouped by state** for better accessibility.

## Feature Statistics
To enhance data usability, we categorized features into seven distinct groups and extracted various statistics to help users understand the dataset. For a more detailed explanation, refer to the [**Descriptive PowerPoint file**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).

### **Feature Categorization**
The dataset contains over **90 attributes**, categorized as follows:

- **Unusable:** Columns that are entirely missing, encrypted, or otherwise incomprehensible. These have been removed.  
- **ID Columns:** Identifiers assigned to each row. One of these columns contains no missing or duplicate values and has been selected as the **primary identifier**.  
- **Location Data:** Includes various geographical identifiers such as state, FIPS code, etc.  
- **Property-Related Data:** Features describing structural attributes, such as the number of stories, units, etc.  
- **Owner-Applicant Data:** Biographical details of property owners and applicants.  
- **Permit Details:** Information about permits, including duration, fees, and permit type.  
- **Binary Choices:** Boolean indicators for quick filtering (e.g., whether a permit is electronics-related).  

### **Missing Values Statistics**
The missing value statistics for all features can be found in the [**Descriptive PowerPoint file**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).  
Statistics are presented as an average for all states, but **critical states** (i.e., those with more than **90% missing values** for certain features) are also highlighted.

## Access Method (Jupyter Notebook)
- A **Jupyter Notebook** executable on **DesignSafe** is available at:  
  [Link](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FBuildings%2FPermit_Data_Cleaned%2FCodes).  
- A walkthrough on executing this code within the **DesignSafe** environment can be found in the [**Descriptive PowerPoint file**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).

## Access Method (Direct)
- The processed data are available as parquet files by state. See ...

## Data Usage Form
- To keep track of research activities related to this data, please **fill out the Google Form**:  
  [Form Link](https://docs.google.com/forms/d/e/1FAIpQLScd733Tc6RolmnzLT9DV03IZrJvQsyH5JtQTCejk6X1IvhP9Q/viewform?usp=dialog).  
- Recorded responses are saved in the following Google Sheet:  
  [Responses Link](https://docs.google.com/spreadsheets/d/11RlY_4f1IOXg-s1axi441tGfrTRSRQyT2H7fgiO_CKo/edit?resourcekey#gid=650003670).  

Thank you for your cooperation!
