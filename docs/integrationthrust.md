# Integration Thrust

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
- Original version of STARR  
- Static building inventory, no funding designs  
- **Code link:**  

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
