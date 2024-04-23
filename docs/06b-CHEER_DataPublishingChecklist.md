# CHEER Hub Top Ten Data Tips

Prepared by: Caroline Williams

Updated by: N/A

Last Update: April 11, 2024

kf* Manager: Caroline Williams (cjw@udel.edu)

***

## 1. Background
Data publication can lead to more impactful and transparent research. By making your data available to the public (and aligning with [FAIR Data Principles](https://www.nature.com/articles/sdata201618)), researchers and the wider community have the potential to validate your findings and extend your research for new applications.

The purpose of this data publishing procedure is to guide you through the publishing process and to also provide a check to ensure your data package contains all necessary contents to improve transparency and reusability. A well-organized dataset can even be recognized through a [DesignSafe Dataset Award](https://www.designsafe-ci.org/community/dataset-awards/).

A dataset can be a single file or a collection of input files, code, figure files, and other artifacts.


## 2. Data Checklist

!!!!! SHOULD THIS BE A GOOGLE FORM? OR A DOC WITH CHECKBOXES? SOMETHING ELSE? !!!!!


* Notice
  * Send an email to the kf* manager to notify them that you’re getting ready to publish your data. Please include the date you plan to submit your dataset for review, and the ideal date for data publication.
* This dataset aligns with the [CHEER Top Ten Data Tips](06a-CHEER_DataTips.md)
* File structure 
  * All folder and file names align with CHEER file naming convention (see “File naming standards” in [CHEER DesignSafe Data Upload Procedures](05b-CHEER_DesignSafe_DataUpload.md)). 
  * Include the following, remembering that ALL published data will be public
Metadata file(s)
    * All relevant code (i.e., do not include temporary scripts or scripts not used in the workflow)
    * All (non-sensitive) input files needed for analysis (see “Identifying Sensitive Data” section in the DesignSafe Data Upload procedures)
    * Modeling files (e.g., your fitted ML model)
    * Key output files (e.g., datasets that others can use, files that are key to your analysis for the published paper)
    * Key analysis figures (only those relevant to your paper)
    * If you’re unsure, make an “Archive” folder and save intermediate files in the Archive folder
  * What not to include: 
    * Sensitive data: proprietary, personally-identifiable information (Examples: NCIUA data, anything you needed an API key to obtain (Census, Microsoft Images, Parcel data), raw survey data with identifiable information)
    * Scratch or temporary files
    * Files related to scenarios not presented in your paper
    * Files considered for input, but not used in the final version
* License type chosen (see [CHEER Top Ten Data Tips](06a-CHEER_DataTips.md) for guidance)
* Metadata file contains (refer to CHEER Metadata Template):
  * Header with project name, NSF award #, dataset authors, DesignSafe project number, date, version, license, language, reference
  * Summary of dataset
  * About five key words listed
  * Description of folder and file structure contained in dataset
    * Describe folder structure
    * Describe any file naming conventions used
* Code contains:
  * Header with:
    * Project name, NSF award #, dataset authors, DesignSafe project number, date, version, license, language, reference
    * File path of metadata document
    * Project summary: <Brief summary of what the code does>
  * Every chunk (1-5 lines) of code has description comments
  * Spell-check comments
  * Functions contain:
    * Description of function
    * List of inputs and outputs, each with variable name, data type, and description
  * Defined classes contain:
    * All classes and methods have description, attribute names, and data type listed
  * If your code is in python:
    * All function and class descriptions are in docstring format
  * Check file paths
    * Remove file paths to sensitive data
    * Ensure all file paths are correct
    * [Optional] Point all file paths to expected published path (Ex. DesignSafe published project path format: /corral/projects/NHERI/projects/<project-uid>/)

## 3. Submit CHEER Data Catalog Form

!!!!! NOT SURE WHAT TO ADD TO THIS SECTION HERE ARE A FEW SNIPPETS FROM THE EXISTING DATA CATALOG GOOGLE FORM: !!!!!

* How can this dataset be used by CHEER team members?
* How can this dataset be used in the wider community? Describe a envisioned/hypothetical scenario.
* Who do you plan to share this dataset with (CHEER team members, community/practitioner partners, wider community)? 

## 4. kf* Manager Review
Email kf* stating that have completed the data publishing checklist, submitted the data catalog form, and require a review. This is not intended to be an intensive/abrasive review, but rather a friendly team-oriented review. The goal is to ensure that data is as “FAIR” as possible.

Allow at least one week for the kf* Manager's review.

## 5. 	Approval for publication
If you are publishing on DesignSafe's Data Depot: 
* The kf* Manager will move your data to a new DesignSafe project, publish this data, and send you the DOI and citation
If you are not publishing on DesignSafe's Data Depot: 
* The kf* Manager will respond via email to work with you individually to publish the data
* In this correpondence, you all will decide who will publish the data, who will share the relevant citation and DOI to the kf* Manager
 
!!!!!!!!! ADD STUFF ABOUT PUBLISHING CODE ON GITHUB/ZENODO? !!!!!!!!!

## 6. 	DesignSafe Acknoledgement 
If you used DesignSafe resources to store, analyze, or publish your data, you should acknowledge the support from the DesignSafe project and the National Science Foundation in any publication of material, whether copyrighted or not, by using the following paper as a reference:

Rathje, E., Dawson, C. Padgett, J.E., Pinelli, J.-P., Stanzione, D., Adair, A., Arduino, P., Brandenberg, S.J., Cockerill, T., Dey, C., Esteva, M., Haan, Jr., F.L., Hanlon, M., Kareem, A., Lowes, L., Mock, S., and Mosqueda, G. 2017. “DesignSafe: A New Cyberinfrastructure for Natural Hazards Engineering,” ASCE Natural Hazards Review, doi:10.1061/(ASCE)NH.1527-6996.0000246.

