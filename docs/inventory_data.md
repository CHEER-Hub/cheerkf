# Inventory Data

Prepared by: **Hesam Soleimani** ([soleimanisam92@g.ucla.edu](mailto:soleimanisam92@g.ucla.edu))  
Updated by: **Hesam Soleimani**  
Status: **Functioning**, with ongoing updates planned  
Last Update: **October 13, 2025**

---

## Contents
- [Overview](#overview)
- [Data Structure](#data-structure)
- [Version Control](#version-control)

---

## Overview

This document summarizes the **Inventory data structure**, its directory organization, and additional information regarding its fields.

---

## Data Structure

The **Inventory data structure** can be summarized as follows:  

### 1. Fusion Data

This dataset is the direct output of the **Inventory Generation** module, [FORTUNA](https://github.com/CHEER-Hub/Fortuna).  
It integrates features and attributes from multiple data sources, including:

- **NSI** ([Dictionary](https://docs.google.com/spreadsheets/d/1Z0g9yA_5fAORfJGk5esTt3T2dLyZsIgU/edit?gid=1943153730#gid=1943153730))  
- **FEMA** ([Dictionary](https://docs.google.com/spreadsheets/d/1zFzPMPG8u-Yd-fiS9QfiTtJ-QW3nHI18/edit?gid=1407154341#gid=1407154341))  
- **Microsoft U.S. Building Footprints** ([Dictionary](https://docs.google.com/spreadsheets/d/1NREWWRxikSWwr0uPS4z1WV4kbR-7Tom2/edit?gid=425705631#gid=425705631))

---

### 2. CHEER-Inventory Data

This dataset represents a **purposeful selection** of the Fusion Data, including features relevant to CHEER’s research focus.  
Additional attributes have been added to support the [CHEER-Safe Model](https://github.com/CHEER-Hub/LossModel).  
A comprehensive [Inventory Data Dictionary](https://docs.google.com/spreadsheets/d/1r9AM08eoTDRibuY9zpnoblz-OcNvFjjgzd8PikwpRYg/edit) explains all included features.

---

## Version Control

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|------------------|--------------|-----------|------------|
| **Inventory Data (V0)** | Inventory coverage for NC and TX (FIPS: 48201 and 48181) study regions | Supports [CHEER-Safe](https://github.com/CHEER-Hub/LossModel) with required building-level features | – | 1. [Data Fusion](https://drive.google.com/drive/folders/1-56QruV-7C5Es4YyoCTIhtcg1VA4aug2): ordered by FIPS codes.<br><br>2. [CHEER-Inventory](https://drive.google.com/drive/folders/1-2mgVZZDV-0LBTeJw6-P2e-ORm25rUyD): selected features with additional AI-driven attributes supporting the loss model (state-level data). |

---

