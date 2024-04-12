# CHEER Hub DesignSafe Data Upload

Prepared by: Caroline Williams

Updated by: N/A

Last Update: April 11, 2024

kf* Manager: Caroline Williams (cjw@udel.edu)

***

## 1. 	Background

<img align="right" src="_media/05b-DataDepotScreenshot.png" width="350px" alt="A screenshot of the Data Depot interface">

CHEER primarily uses the [Data Depot](https://www.designsafe-ci.org/data/browser/public/) on DesignSafe to store and publish data. While DesignSafe has a [comprehensive guide](https://www.designsafe-ci.org/user-guide/managingdata/) for managing and publishing data on the DesignSafe Data Depot, the following is intended to provide streamlined steps to upload data on the CHEER project in DesignSafe.

There are three main places where a DesignSafe user can access and store data on DesignSafe: 
* **My Data**: personal storage location only accessible to you
* **My Projects**: shared storage locations (“Projects”) that are only accessible to designated team members
* **Published**: published data open to the public

The [CHEER project folder](https://www.designsafe-ci.org/data/browser/projects/1798100155562136046-242ac117-0001-012/) is a private location to store data that can only be shared among CHEER team members. Only CHEER team members have access to this project folder. 

Once a dataset is ready to be published for public use, the data will be moved from the CHEER project folder (PRJ-4392) to a new project on the DesignSafe Data Depot (PRJ-<new number>). This new project will then be published and receive a DOI. See the CHEER Hub Data Publishing Procedure doc when you’re ready to publish data.

***
**IMPORTANT**: Identifying Sensitive Data</p>

Before uploading any data to DesignSafe, you *must consult with your advisor* to determine whether your data are sensitive data or not. Sensitive data includes, but is not limited to:
* **Proprietary data**
  * Examples: insurance claims data, Zillow/ZTRAX data, satellite or street view images, non-public parcel data
  * Generally, anything requiring a Data Use Agreement or a private key to access the data is sensitive data
* **Personally identifiable information (PII)**
  * Examples: names, social security numbers, license/passport numbers, anything that can pinpoint an individual
* **Institutional Review Board (IRB)**
  * Any sensitive content identified in an IRB document including PII, interview recordings, other sensitive research data
* **Other**: HIPPA, FERPA, ITAR, CUI, EAR, or anything else listed on [TACC’s protected data service](https://tacc.utexas.edu/about/security-and-compliance/protected-data-service/)

***

## 2. 	Uploading data to the CHEER project folder

Depending on the number and size of files/folders that you need to transfer to the CHEER project folder, there are primarily two different ways to upload the data: 1) normal data transfer method, or 2) large data transfer method. Figure 1 (next page) summarizes these steps, with detailed instructions below.

<p align="center">
  <img align="center" src="_media/05b-DesignSafe_DataUploadFlow.png" width="600px" alt="A flow chart with a summary of steps to upload data. These summarized steps align with the text.">
</p>

<ol>
<li>First identify whether you are in possession of sensitive data (see box above).</li>
  <ol>
  <li>If you <b>do</b> have sensitive data, send an email to the kf* manager to decide how to proceed as a team. One possibility that the team may pursue is to work with [TACC’s Protected Data Service team](https://tacc.utexas.edu/about/security-and-compliance/protected-data-service/).</li>
  <li>If you <b>do not</b> have sensitive data, proceed with the following steps.</li>
  </ol>

<li>Review the CHEER Hub’s [CHEER Hub Top Ten Data Tips](06a-CHEER_DataTips.md) to ensure your data aligns with the CHEER recommendations</li>


<img align="right" src="_media/05b-CHEER_DesignSafe_ChangingFilesInterface.png" width="350px" alt="A screenshot of the DesignSafe interface showing the buttons to use to adjust files">


<li>If you are transferring files that are < 2GB in size, or < 25 files or < 3 folders, you can follow the <b>normal data transfer method</b>:</li>
  <ol>
  <li>Go to the [DesignSafe website](https://www.designsafe-ci.org/)</li>
  <li>Sign in using your TACC user name</li>
  <li>Go to CHEER project folder in Data Depot</li>
    <ol>
    <li>Go to the “Use DesignSafe” tab, then click “Data Depot”</li>
    <li>Click “My Projects” on the left panel</li>
    <li>Click on the CHEER project folder (PRJ-4392)</li>
      <ul>
      <li>Note: If you do not see PRJ-4392, email the kf* manager with your TACC user name to make sure they added you to the CHEER project folder</li>
      </ul>
    </ol>
  <li>Navigate to the folder corresponding to your project.</li>
    <ol>
    <li>Click on the thrust folder related to your project (Buildings, Economy, Government, Hazards, Households)</li>
      <ul>
      <li>Note: If you would like to create a new folder here, please contact the kf* manager first.</li>
      </ul>
    <li>If you need to add a new folder for your project, click the “Add” button in the left panel and create a new folder. When naming the folder, you <b>must</b> adhere to the following:</li>
      <ul>
      <li>The name <b>must not have spaces</b>. Use capitalization or underscores to separate words (e.g., HousingInventoryProjection, housing_inventory_projection)</li>
      <li>Make the folder name concise yet descriptive (i.e. avoid unfamiliar arbitrary acronyms or generic descriptions)</li>
      <li>Thrust teams should discuss how they want to organize their folder</li>
      </ul>
    </ol>
  <li>To upload files, click on the “Add” button on the left panel and select “File upload: max 2GB”</li>
    <ol>
    <li>Choose your file and press “Begin upload”</li>
    <li>To rename, move, copy, download, or delete a folder or file, you must check the box next to the file/folder, then click on the appropriate action in the top panel (below the search bar)</li>
    </ol>
  <li>For help with transferring files on the Data Depot, submit a [help ticket](https://www.designsafe-ci.org/help/new-ticket/)</li>
  </ol>

<li>If you are transferring files that are > 2GB in size, or > 25 files or > 3 folders, you need to follow the <b>large data transfer method</b>:</li>
  <ol>
  <li>If you do not have an authentication app on your phone (e.g., [Google Authenticator](https://apps.apple.com/us/app/google-authenticator/id388497605), [Microsoft Authenticator](https://apps.apple.com/us/app/microsoft-authenticator/id983156458), [Duo](https://apps.apple.com/us/app/duo-mobile/id422663827)), download the app of your choice.</li>
    <ol>
    <li>Note: it’s possible that you already have an authenticator app on your phone for your university’s multi-factor authentication (MFA), for GitHub, or other needs. You can use this same app in the following steps.</li>
    </ol>
  <li>Set up multi-factor authentication on TACC (see [TACC guide](https://docs.tacc.utexas.edu/basics/mfa/) for details):</li>
    <ol>
    <li>Go to the [TACC portal (https://tacc.utexas.edu/)](https://tacc.utexas.edu/portal/login) (*this is a different website than the DesignSafe homepage*)</li>
    <li>Sign in using your TACC username and password</li>
    <li>Click on your username in the upper right corner</li>
    <li>Click on “Manage Account”</li>
    <li>Click on “Pair Device”</li>
    <li>Select “Token App”</li>
    <li>Click on the gray square to generate a QR code</li>
    <li>Open your authenticator app on your phone and select the option to pair an account/token (likely represented by a “+” sign in the upper right corner of your phone screen)</li>
    <li>The app will launch your phone’s camera and you will need to scan the QR code.</li>
    <li>Your device is now paired. Every time you are asked for a TACC token, you will need to open this app on your phone and enter the code associated with TACC.</li>
    <li>For help, submit a [help ticket](https://www.designsafe-ci.org/help/new-ticket/)</li>
    </ol>
  <li>Next, you’ll need to download Cyberduck to your computer, which is a software that will transfer files from your computer to DesignSafe (known as an SSH file transfer protocol (SFTP) client).</li>
    <ol>
    <li>[Download Cyberduck](https://cyberduck.io/download/) on your computer</li>
      <ul>
      <li>Note: you may download/use a different SFTP client (e.g., WinSCP, Fetch, Globus) if you prefer.</li>
      <li>Note: Cyberduck may prompt you to make a donation, but this is unnecessary and you can ignore</li>
      </ul>
    </ol>
  <li>Set up bookmark in Cyberduck</li>
    <ol>
    <li>Open Cyberduck</li>
    <li>Select “Bookmark” from the top bar, then select “New Bookmark” from the dropdown.</li>
    <li>Add the following information to the bookmark screen:</li>
      <ul>
      <li>Select “SFTP (SSH file transfer protocol)” from dropdown of options</li>
      <li>Nickname: corral</li>
      <li>URL: [ignore - this will auto-populate as you enter info in other boxes]</li>
      <li>Server: data.tacc.utexas.edu</li>
      <li>Username: {your TACC username}</li>
      <li>Anonymous login: [ignore]</li>
      <li>Password: {your TACC password}</li>
      <li>SSH private key: None</li>
      <li>Client certificate: None</li>
      <li>Select “more options” to reveal eight more bookmark settings</li>
      <li>Path: /corral/projects/NHERI/projects/1798100155562136046-242ac117-0001-012/</li>
        <ul>
        <li>Note: the long number in this path identifies the CHEER project folder on DesignSafe. See [this guide](https://www.designsafe-ci.org/user-guide/managingdata/#setting-path-to-ds-on-corral) for more information about DesignSafe file paths.</li>
        </ul>
      <li>Web URL: [ignore]</li>
      <li>Download folder: [select folder that you’d like files to be downloaded to on your local computer]</li>
      <li>Transfer files: Default</li>
      <li>Timezone: UTC</li>
      <li>Encoding: UTF-8</li>
      <li>Connect mode: Default</li>
      <li>Then close bookmark box</li>
      </ul>
    <li>Select the “corral” bookmark</li>
    <li>Enter your six-digit TACC token (accessible through your authenticator app on your phone)</li>
    <li>You now have access to the CHEER project folder on DesignSafe. The file structure you see here should be the same as the [CHEER project folder available on the DesignSafe web interface](https://www.designsafe-ci.org/data/browser/projects/1798100155562136046-242ac117-0001-012/).</li>
    </ol>
  <li>Click on the thrust folder related to your project (Buildings, Economy, Government, Hazards, Households)</li>
    <ol>
    <li>Note: If you would like to create a new folder here, please contact the kf* manager first.</li>
    <li>Navigate to the folder corresponding to your project within your thrust’s folder.</li>
      <ul>
      <li>If you need to add a new folder for your project, click on “File” > “New Folder”</li>
      <li>When naming the folder, you must adhere to the following:</li>
        <ul>
        <li>The name <b>must not have spaces</b>. Use capitalization or underscores to separate words (e.g., HousingInventoryProjection, housing_inventory_projection)</li>
        <li>Make the folder name concise yet descriptive (i.e. avoid unfamiliar arbitrary acronyms or generic descriptions)</li>
        <li>Thrust teams should discuss how they want to organize their folder</li>
        </ul>
      </ul>
    </ol>
  <li>Drag files from your computer into the Cyberduck interface which will initiate the file transfer. (You can also drag files from Cyberduck to your computer, which would initiate a file download.)</li>
    <ol>
    <li>When you’re adding and moving files in Cyberduck, you will frequently be asked to add a TACC token. Therefore, it’s best to have your phone nearby and your authenticator app open when you’re transferring many files.</li>
    </ol>
  <li>For help with transferring files on Cyberduck, submit a [help ticket](https://www.designsafe-ci.org/help/new-ticket/)</li>
</ol>

## 3. File naming standards
While everyone should review the [CHEER Hub Top Ten Data Tips](06a-CHEER_DataTips.md), the following summarizes the requirements for CHEER file naming.
* **MOST IMPORTANT: do not use spaces in file names**
* Underscores or capitalization are your friend (e.g., REACH_module_outputs, REACHmoduleOutputs)
* Don’t use special characters (& ,* % # ;*( !@$^~' { [?<-)
* Don’t depend on letter case alone to distinguish between files
  * Ex. Don’t use BldgInv_v1.csv and bldginv_v1.csv as two different file names
* When many versions of a file will exist, lead the file name with the date: YYYY-MM-DD_<fileName>
  * Ex. 2024-01-26_<fileName>
* Make file name meaningful and descriptive (i.e., “a24_temp_draft.csv” is not meaningful)
* For the main part of file name (e.g., <fileName> in example below) lead with most general description and end with more specific description
  * Ex. 2024-01-26_CHEER_BldgInv_RoofShapeImputation_Gable.csv
* When using sequential numbering, use leading zeros
  * Ex. “001”, not “1”
* Only use a period before the file extension
* Limit file names to 32 characters or less.

## 4. Next Steps
Now you’re likely interested in developing your code or using DesignSafe HPC resources. To do so, follow the instructions provided in the following guides:
* CHEER Hub Code Templates
* CHEER Hub GitHub Procedures
* CHEER Hub DesignSafe HPC Usage Procedures
















