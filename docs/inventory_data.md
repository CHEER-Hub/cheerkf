# Inventory Data

Prepared by: **Hesam Soleimani** ([soleimanisam92@g.ucla.edu](mailto:soleimanisam92@g.ucla.edu))  
Updated by: **Hesam Soleimani**  
Status: **Functioning**, with ongoing updates planned  
Last Update: **October 13, 2025**

---

# Contents
- [Overview](#overview)
- [Data Structure](#data_struc)
- [Version Control](#version-c)

---

# Overview

This file summarizes the Inventory data structure, directory and additional information on its fileds.

---

## Data Structure

The Inventory data strcuture can be summarized as the following:<br>
1- Fusion Data:

This data is the direct outcome of the Inventory Generation module, [FORTUNA](https://github.com/CHEER-Hub/Fortuna). Accordingly, it consists of various features and attributes from NSI ([Dictionary]](https://docs.google.com/spreadsheets/d/1Z0g9yA_5fAORfJGk5esTt3T2dLyZsIgU/edit?gid=1943153730#gid=1943153730)), FEMA ([Dictionary]](https://docs.google.com/spreadsheets/d/1zFzPMPG8u-Yd-fiS9QfiTtJ-QW3nHI18/edit?gid=1407154341#gid=1407154341)), and Microsoft US-Building ([Dictionary]](https://docs.google.com/spreadsheets/d/1NREWWRxikSWwr0uPS4z1WV4kbR-7Tom2/edit?gid=425705631#gid=425705631)) data.

2- CHEER-Inventory Data

This data is purposeful selection of the Fusion Data, from which features are includeed that are of CHEER interest. Moreover, additional features are added to demanded by the [CHEER-Safe model](https://github.com/CHEER-Hub/LossModel). The Inventory data [Dictionary](https://docs.google.com/spreadsheets/d/1r9AM08eoTDRibuY9zpnoblz-OcNvFjjgzd8PikwpRYg/edit) clarify the features. 

---

### Version Control


| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|------------------|--------------|-----------|------------|
| **Inventory Data (V0)** | Inventory over NC and TX (FIPS: 48201 and 48181) study regions | Supporting [CHEER-Safe](https://github.com/CHEER-Hub/LossModel) with required building features| – | [Data Fusion](https://drive.google.com/drive/folders/1-56QruV-7C5Es4YyoCTIhtcg1VA4aug2), ordered by FIPS codes.<br>2: [CHEER-Inventory](https://drive.google.com/drive/folders/1-2mgVZZDV-0LBTeJw6-P2e-ORm25rUyD), selected features with additional AI-driven features to support the loss model (state-level data). |

---
---

