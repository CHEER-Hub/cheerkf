# Inventory–Loss Link

**Prepared by:** [Hesam Soleimani](mailto:soleimanisam92@g.ucla.edu)  
**Updated by:** Hesam Soleimani  
**Status:** *Functioning*, with ongoing updates planned  
**Last Update:** October 12, 2025  

---

# Overview

This document summarizes the **Inventory–Loss Link** module, which executes the **CHEER-Safe** loss model using a **building-by-building** schema derived from the developed inventory system.  

The following table tracks the version history of this module, outlines its functionality and objectives, and provides references to detailed documentation and related CHEER resources.

---

## Version Control

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|-----------------|--------------|-----------|------------|
| **Inventory–Loss Link (V0)** | Region-wide, building-level hurricane damage assessment (including both flood and wind impacts). | The key purposes are:<br>1. Transform the input building inventory into **CHEER-Safe** native archetypes.<br>2. Extract flood depth and wind ratio for each entity.<br>3. Calculate flood, wind, and total losses (in %).<br>4. Transform the loss data structure into a structured object. | – | [GitHub Page (archived as V0, with documentation included)](https://github.com/CHEER-Hub/Inventory-Loss-link/tree/main) |
| **Inventory–Loss Link (V1)** | Region-wide, building-level hurricane damage assessment (including both flood and wind impacts). | Same as V0, with the following improvements:<br>1. In cases of stochastic behavior in the inventory or assigned configuration, perform **random sampling**.<br>2. Transform the loss data structure to align with the **STARR** framework. | – | [GitHub Page (live and archived as V1)](https://github.com/CHEER-Hub/Inventory-Loss-link/tree/main)<br><br>[Documentation](https://cheer-hub.github.io/Inventory-Loss-link/Data_Fusion.html) |

---
