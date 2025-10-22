# Developed Deep Models to Support Inventory Generation

Prepared by: **Hesam Soleimani** *(emeritus)* ([soleimanisam92@g.ucla.edu](mailto:soleimanisam92@g.ucla.edu))  
Updated by: **Hesam Soleimani**  
Status: **Functioning**, with ongoing updates planned  
Last Update: **October 10, 2025**

---

# Contents
- [Overview](#overview)
- [Roof Classifier](#roof-classifier)
- [Building Type Classifier](#building-type-classifier)
- [Version Control](#version-control)

---

# Overview

This document summarizes various deep learning models developed to support the **FORTUNA** inventory generator.  
These models have not yet been integrated into the official FORTUNA GitHub repository.  
Each model’s purpose, type, and example Jupyter notebooks demonstrating their applications are provided here.

---

## Roof Classifier

This module classifies **roof types** from satellite imagery to categorize them into roof shapes required by the loss estimation module (see [Loss Model](https://github.com/CHEER-Hub/Inventory-Loss-link/blob/main/Inv_Loss_Link.py)).

### Roof Classifier Version Control

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|-----------------|--------------|-----------|------------|
| **Roof Classifier (V0)** | Roof Shape Classification | Identifies roof shapes across 9 classes:<br>0: Hip<br>1: Cross Hip<br>2: Complex Gable<br>3: Cross Gable<br>4: Gable<br>5: Flat<br>6: Mobile Home<br>7: Unknown<br>8: No Structure | – | [Roof Classification Details](https://docs.google.com/presentation/d/1j-qWMzhk3FdkP_NkvGKfYh8FEoBm3XSb/edit?rtpof=true)<br><br>[Trained Model](https://drive.google.com/file/d/1gtv-tEI4gKX7HWdKwDcIyR4yWrBO6PMd/view)<br><br>[Notebook to Run the Model](https://colab.research.google.com/drive/1UqWvAuVcVKqE-X8n9mvMzVM8yt2aKUxh)<br><br>[Data](https://drive.google.com/drive/u/0/folders/1tXIJrfNMAPWr9qx_SnvmX7yRZAxhGUe4) |

---

## Building Type Classifier

This module classifies **building types** from street-view images to categorize them into the groups required by the loss model (see [Loss Model](https://github.com/CHEER-Hub/Inventory-Loss-link/blob/main/Inv_Loss_Link.py)).

### Building Type Classifier Version Control

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|-----------------|--------------|-----------|------------|
| **Building Type Classifier (V0)** | Building Utility Classification | Identifies building utilities across 4 classes:<br>0: Multi-Family<br>1: Mobile/Manufactured Homes <br>2: Non-Residential<br>3: Single-Family | – | [Building Type Classification Details](https://docs.google.com/presentation/d/1_4VMdOTwEs-NgynvBFSNkRI2JrJDA1Th/edit)<br><br>[Trained Model](https://drive.google.com/file/d/19uEGtwpdshSYNZm3mI-ggPVDWMTsevNa/view?usp=sharing)<br><br>[Notebook to Run the Model](https://colab.research.google.com/drive/15gdlvNB7lg13_20TMDEbO6JTAvHI4JOl)<br><br>Available on UCLA Team SSD drives (due to large file size) |
