# Integration Thrust

Prepared by Jingya Wang (wangjy@udel.edu)

# Contents
 - [Overview of STARR](#STARR)
 - [STARR Model Versions](#versions)

# Overview of STARR

The **Stakeholder-based Tool for the Analysis of Regional Risk (STARR)** is a dynamic, stochastic computational framework designed to inform the creation and evaluation of government policies for regional disaster risk management (Davidson et al., 2025).  

STARR models the interactions among governments, insurers, and households through interconnected decision-making modules (blue boxes in Figure 1) and context modules (green boxes). The stakeholder modules represent how governments set policies, insurers adjust pricing and coverage, and households make risk-based decisions. The context modules define the underlying hazard risks, built environment, and economic conditions that shape these choices.  

Operating on an annual time step, STARR incorporates feedback loops: each year’s changes in risk exposure and economic conditions influence stakeholder responses. When hurricanes occur, they generate losses that disrupt the system, which in turn affect subsequent decisions. Figure 1 provides a schematic overview of the framework.  

Additional detail on STARR and its applications can be found in Kesete et al. (2014), Peng et al. (2014), Gao et al. (2016), Wang et al. (2020), Guo et al. (2022), and Liu et al. (2023).  

---

<img width="432" height="258" alt="image" src="https://github.com/user-attachments/assets/dc21d915-c984-412c-827a-20283166d4a0" />

*Source: Davidson et al. (2025)*

---

STARR employs a nested dynamic Stackelberg game (red boxes in Figure 1) to capture stakeholder interactions. In the outer game, the government sets policies, anticipating responses from insurers and households. Insurers then compete in the inner game, determining pricing and coverage based on household demand, which is shaped by policy interventions, risk perception, and economic conditions. Households, in turn, decide on insurance participation and risk reduction actions in response to available options and financial constraints.  

Rather than prescribing an optimized solution for all, STARR recognizes that insurers and households act in self-interest, and policy interventions must operate within these behavioral inclinations. The framework produces outputs such as recommended government policy decisions, expected stakeholder responses, and system-wide outcomes under uncertain hurricane events and evolving economic conditions.  

The context modules—including hazard, building inventory, damage and loss, and regional economy—are similar to existing regional loss-estimation models such as **HAZUS**, **IN-CORE** (Van de Lindt et al., 2023), the **FPHLM** (Gurley et al., 2005; Hamid et al., 2011), and **R2D** (Deierlein et al., 2020; McKenna et al., 2024). However, they are specifically designed to interact with the decision modules, enabling dynamic assessment of risk and policy effectiveness.
# STARR Model Versions

This document provides a simple overview of the STARR model versions and where to find them.  

---

## Baseline (STARR V0)
- # STARR V0 (Baseline)

The **Baseline STARR model (V0)** is the original implementation of the Stakeholder-based Tool for the Analysis of Regional Risk. It establishes the foundational structure of the framework, bringing together the hazard, building inventory, damage and loss, and stakeholder modules into a unified simulation.  

### Key Features
- **Static Building Inventory:** The set of buildings and households is fixed over time, without growth or change in characteristics.  
- **Hazard and Loss Representation:** Uses a scenario-based hurricane hazard module and component-based damage and loss functions to estimate wind and flood impacts on the inventory.  
- **Stakeholder Decisions:** Includes the three stakeholder modules—government, insurers, and households—interacting annually through the nested Stackelberg game.  
- **Government Policies:** Focuses on normative government decisions such as acquisition and retrofit incentives, evaluated against stakeholder responses.  
- **Insurer and Household Behavior:** Models insurers adjusting premiums and coverage based on past loss experience and households deciding on insurance purchase, retrofits, or buyouts based on preferences, risk, and incentives.  

### Purpose
STARR V0 serves as the **reference version** of the model. It demonstrates the integration of stochastic hurricane hazards, a detailed inventory of households and buildings, and dynamic decision-making processes among stakeholders. This version has been applied in early studies to evaluate how government interventions (e.g., acquisition and retrofit subsidies) influence long-term risk reduction and economic outcomes under repeated hurricane events.  

### Role in Development
- Provides the **foundation** for later variants.  
- **STARR-DBI** extends V0 by adding a dynamic building inventory.  
- **STARR-GOV v1** extends V0 by incorporating multiple funding design structures.

  ### Resources

- **Code (MATLAB):** [STEER repository](https://github.com/CHEER-Hub/STEER)  
- **Code (Python, well-commented):** [STARR-V0 repository](https://github.com/CHEER-Hub/STARR-V0)  
- **Dataset:** [DesignSafe PRJ-4392](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FIntegration%2FSTARR_V0), with full dataset manual  

### Citation
If you use STARR V0, please cite:  
Davidson, R., et al. (2025). *Stakeholder-based Tool for the Analysis of Regional Risk (STARR).* *Natural Hazards Review.*  
(plus dataset DOI once available)

### Requirements
- MATLAB version R2020b or later (for STEER implementation)  
- Python 3.10+ with standard scientific libraries (numpy, pandas, matplotlib)  

### Outputs
Typical outputs include:  
- Hurricane scenario losses by year  
- Household acquisition/retrofit decisions  
- Government spending and policy effects  
- Insurer premiums and profits  

V0 is the baseline for comparisons, ensuring that improvements or policy innovations can be clearly measured against a consistent starting point.


---

## STARR-DBI
- Extension of STARR with **Dynamic Building Inventory**  
- Captures growth and change in building stock over time  
- **Code link:**   

---

## STARR-GOV v1
- Extension of STARR with **five funding designs**  
- Vary by timing, spatial scale, and allocation basis  
- **Code link:**  

---

## Notes
- We will use consistent naming going forward: **STARR V0**, **STARR-DBI**, **STARR-GOV v1**  
- Links above should point to the correct GitHub tags/branches  
- For now, this serves as a quick reference outline
