# Developed Deep Models to Support Inventory Generation

Prepared by: **Hesam Soleimani** ([soleimanisam92@g.ucla.edu](mailto:soleimanisam92@g.ucla.edu))  
Updated by: **Hesam Soleimani**  
Status: **Functioning**, with ongoing updates planned  
Last Update: **October 10, 2025**

---

# Contents
- [Overview](#overview)
- [Roof Classifier](#roof_c)
- [Building Type Classifier](#Type_c)
- [Version Control](#version-c)

---

# Overview

This file summarizes various deep learning models developed to support the **FORTUNA** inventory generator.  
These models have not yet been implemented in the official FORTUNA GitHub repository.  
Each model’s purpose, Type, and sample Jupyter notebooks demonstrating their applications are included here.

---

## Roof Classifier

This module classifies **roof types** from satellite images to categorize them into roof shapes required by the loss estimation module (see [Loss Model](https://github.com/CHEER-Hub/Inventory-Loss-link/blob/main/Inv_Loss_Link.py)).

### Roof Classifier Version Control

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|------------------|--------------|-----------|------------|
| **Roof Classifier (V0)** | Roof Shapes | Identifies roof shapes across 9 classes:<br>0: Hip<br>1: Cross Hip<br>2: Complex Gable<br>3: Cross Gable<br>4: Gable<br>5: Flat<br>6: Mobile Home<br>7: Unknown<br>8: No Structure | – | [Roof Classification Details](https://docs.google.com/presentation/d/1j-qWMzhk3FdkP_NkvGKfYh8FEoBm3XSb/edit?rtpof=true)<br><br>[Trained Model](https://drive.google.com/file/d/1gtv-tEI4gKX7HWdKwDcIyR4yWrBO6PMd/view)<br><br>[Notebook to Run the Model](https://colab.research.google.com/drive/1UqWvAuVcVKqE-X8n9mvMzVM8yt2aKUxh) |

---

## Building Type Classifier

This module classifies **Building Type** from street-view images to categorize them into categories needed by the loss model (see [Loss Model](https://github.com/CHEER-Hub/Inventory-Loss-link/blob/main/Inv_Loss_Link.py)).

### Building Type Classifier

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|------------------|--------------|-----------|------------|
| **Building Type Classifier (V0)** | Building Type | Identifies building utilities across 4 classes:<br>0: Single-Familty<br>1: Multi-Family<br>2: Mobile-Manufactored Homes<br>3: Non-Residential| – | [Roof Classification Details](https://docs.google.com/presentation/d/1_4VMdOTwEs-NgynvBFSNkRI2JrJDA1Th/edit)<br><br>[Trained Model](https://drive.google.com/file/d/19uEGtwpdshSYNZm3mI-ggPVDWMTsevNa/view?usp=sharing)<br><br>[Notebook to Run the Model](https://colab.research.google.com/drive/15gdlvNB7lg13_20TMDEbO6JTAvHI4JOl) |


