# CHEER Project Shovels Permit Data
Please make sure that, if you want to use this data, please make sure to fill at the Form at the end to ensure the whole team aligns with whatever research being done on this data and save time and rewsources by doing so.

## Contents
 - [Original Data](#original-data) 
 - [Data Processing](#data-processing)
 - [Feature Statistics](#feature-statistics)
 - [Access Method (Jupyter Notebook)](#access-method-(jupyter-notebook))
 - [Data Usage Form](#data-usage-form)

## Original Data
Dataset location: DesignSafe 
- Shovel Permkit Data (Original): ([Link](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FBuildings%2FShovels_Permit_Data))

# Data Processing
This section describes, first, data cleaning and error correction inside the original data (#data-cleansing) and second, how the data is organized for an easier access.
- **Data Cleaning:**
  Data issues with the original database contains:
   - **Swapped lattitude and longitude values**:
   By knowing the range of lattitude and longitudes on the ESPG:4326 system, those columns are readily identified and corrections are made
   - **Different Missing Values Format**:
The missing values inisde the original data were noted using different notation; all are identified and turned into (numpy) missing value format for easier tracking.

- **Re-structuring Data**:
The original data comes with no specific order, such as being state-wise ordered, etc. Since no mising values exist for the original data column "STATE", the cleansed original data is re-ordered in a state-wise manner

## Feature Statistics
To better understand and access features, we first have categorized features into into 7 distinct groups, and then various statistics are extracted from them to better guide users into what expectation they can have from the data. For a more detailed description of the above-mentioned notes, you can follow the [**Descriptive PowerPoint file.**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).

- **Feature Categorization**:
Over 90 attributes exist in the original data, which are categorized by us into 7 groups, as follows:
  - **Unusable** These columns either suffers from all missing values, or are hashed, or ciphered in anyways uncomprehencible by the users. They must shall be removed, and are thus.
  - **ID columns** The identifiers assigned to each row of data, from which one does not contain any missing/duplicated values, and we thus have taken that as the main identifier as well.
  - **Location** Thise group of features unvweil various location data for each data row, including but not limited to state, FIPS code, etc.
  - **Property-related** These features disclose various structural-related features, such as the number of stories, unites, etc.
  - **Owner-Applicant** Biographic data from the owener and applicant of properties.
  - **Permit Details** Deatils of the permit data at different detailing level as well duration, fees, and other perimit-related information.
  - **Binary Choices** These **Boolean** features allow for a quick filtering of the data, like whether the permit is Electronics-related or not.
- **Missing Values Statistics**:
The missing value statistics for all features can be found at [**Descriptive PowerPoint file.**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).
The statistics are given on an average for all states, but critical states, i.e., states which have more than 90% mising values for features are also included.

## Access Method (Jupyter Notebook)
- Given the aboce details, a Jupyter notebook, executable on DesignSafe, is now available at [(Link)](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FBuildings%2FPermit_Data_Cleaned%2FCodes).
- The walkthrough on this code execution within the DesignSafe environment is available at [**Descriptive PowerPoint file.**](https://docs.google.com/presentation/d/15Am9-SoHL43LGmqlmvyKEnZoY-mqy97k/edit#slide=id.p1).

## Data Usage Form
- The Google Sheet file at [link](https://docs.google.com/forms/d/e/1FAIpQLScd733Tc6RolmnzLT9DV03IZrJvQsyH5JtQTCejk6X1IvhP9Q/viewform?usp=dialog) helps to keep track of research endeavors on this data, so please kindly fill this form; thank you.
- The recorded responses are saved at [link](https://docs.google.com/spreadsheets/d/11RlY_4f1IOXg-s1axi441tGfrTRSRQyT2H7fgiO_CKo/edit?resourcekey#gid=650003670), which we encourage you check that out. Thank you.
 

