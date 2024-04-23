# CHEER Hub Top Ten Data Tips

Prepared by: Caroline Williams

Updated by: N/A

Last Update: April 11, 2024

kf* Manager: Caroline Williams (cjw@udel.edu)

***

## 1. Background



## 2. Data Checklist
* Notice
  * Send an email to the kf* manager to notify them that you’re getting ready to publish your data. Please include the date you plan to submit your dataset for review, and the ideal date for data publication.
File structure 
All folder and file names align with CHEER file naming convention (see “File naming standards” in DesignSafe Data Upload procedures). 
Include the following, remembering that ALL published data will be public
Metadata file(s)
All relevant code (i.e., do not include temporary scripts or scripts not used in the workflow)
All (non-sensitive) input files needed for analysis (see “Identifying Sensitive Data” section in the DesignSafe Data Upload procedures)
Modeling files (e.g., your fitted ML model)
Key output files (e.g., datasets that others can use, files that are key to your analysis for the published paper)
Key analysis figures (only those relevant to your paper)
If you’re unsure, make an “Archive” folder and save intermediate files in the Archive folder
What not to include: 
Sensitive data: proprietary, personally-identifiable information (Examples: NCIUA data, anything you needed an API key to obtain (Census, Microsoft Images, Parcel data), raw survey data with identifiable information)
Scratch or temporary files
Files related to scenarios not presented in your paper
Files considered for input, but not used in the final version
License type chosen (see Top Ten Data Tips for guidance)
Metadata file contains (refer to CHEER Metadata Template):
Header with project name, NSF award #, dataset authors, DesignSafe project number, date, version, license, language, reference
Summary of dataset
~five key words listed
Description of folder and file structure contained in dataset
Describe folder structure
Describe any file naming conventions used
[If applicable] 
Code contains:
Header with 
project name, NSF award #, dataset authors, DesignSafe project number, date, version, license, language, reference
path of metadata document
Project summary: <Brief summary of what the code does>
Every chunk (1-5 lines) of code has description comments
Spell-check comments
Functions contain:
Description of function
List of inputs and outputs, each with variable name, data type, and description
Defined classes contain:
All classes and methods have description, attribute names, and data type listed
If your code is in python:
All function and class descriptions are in docstring format
Check file paths
Remove file paths to sensitive data
Ensure all file paths are correct
[Optional] Point all file paths to expected published path (Ex. DesignSafe published project path format: /corral/projects/NHERI/projects/<project-uid>/)




## 2. Next Steps
* [CHEER Hub DesignSafe Sign-Up](05a-CHEER_DesignSafe_SignUp.md)
* [CHEER Hub DesignSafe Data Upload Procedures](05b-CHEER_DesignSafe_DataUpload)
* CHEER Hub Code Templates
* CHEER Hub GitHub Procedures
