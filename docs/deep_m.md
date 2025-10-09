# Developed Deep Models to Support Inventory Generation

Prepared by Hesam Soleimani (soleimanisam92@g.ucla.edu)

Updated by: Hesam Soleimani

Status: Functioning with ongoing updates planned

Last Update: October 10, 2025


# Contents
- [Roof Classifier](#roof_c)
- [(Attahced) Garage Detector](#garage_d)
- [Number of Stories Classifier](#story_n)
- [Building Utility Classifier](#utility_c)
- [Version Control](#version-c)

# Overview

This file recaps various deep models developed to support the Inventory generator, FORTUNA, which has not yet been implemented in the FORTUNA GitHub repository. Model, their utility, and sample Jupyter Notebooks to showcase their application are included here.

## Roof Classifier

This module is to classifiy roof types from satellite images to categorize them intro roof shapes required by loss estimation module (see[Loss Model][]).

### Roof Classifier Version Control

| Version        | Main Feature(s)                          | Key Purpose                                         | Upgrades| Resources |
|----------------|--------------------------------------------|-----------------------------------------------------|-----------|-----------|
| **Roof Classifier (V0)** | Roof Shapes - | Identofy roof shapes from 9 classes of 0:'Hip',1:'Cross Hip',2:'Complex Gable',3:'Cross Gable',4:'Gable',5:'Flat',6:'Mobile Homese',7:'Unknown',8:'No Structure'|-|[Roof classifciation details](https://docs.google.com/presentation/d/1j-qWMzhk3FdkP_NkvGKfYh8FEoBm3XSb/edit?rtpof=true)<br> [Trained Model](https://drive.google.com/file/d/1gtv-tEI4gKX7HWdKwDcIyR4yWrBO6PMd/view)<br> [Notebook to Run the Model](https://colab.research.google.com/drive/1UqWvAuVcVKqE-X8n9mvMzVM8yt2aKUxh)|
---
