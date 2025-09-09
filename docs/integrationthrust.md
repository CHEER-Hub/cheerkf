# Integration Thrust

Prepared by Jingya Wang (wangjy@udel.edu)

# Contents
- [Overview of STARR](#overview-of-starr)
- [STARR Model Versions](#starr-model-versions)
  - [Quick Summary](#starr-model-versions--quick-summary)
  - [Baseline (STARR V0)](#baseline-starr-v0)
  - [STARR-DBI](#starr-dbi)
  - [STARR-GOV-V1](#starr-gov-v1)

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

## Quick Summary

The Stakeholder-based Tool for the Analysis of Regional Risk (STARR) has been extended into several versions.  
This page provides a quick overview; see the following sections for full details.

| Version        | Main Feature(s)                           | Key Purpose                                         | Resources |
|----------------|--------------------------------------------|-----------------------------------------------------|-----------|
| **STARR V0 (Baseline)** | Original framework with static building inventory; hazard, loss, and stakeholder modules | Serves as the reference version; evaluates baseline government acquisition and retrofit policies | [MATLAB code](https://github.com/CHEER-Hub/STEER) · [Python code](https://github.com/CHEER-Hub/STARR-V0) · [Dataset PRJ-4392](https://www.designsafe-ci.org/data/browser/projects/PRJ-4392/workdir/%2FIntegration%2FSTARR_V0) |
| **STARR-DBI** | Adds **Dynamic Building Inventory (DBI)**; buildings/households evolve each year | Evaluates land use restrictions, acquisitions, and growth impacts on risk and equity | [Code](https://github.com/CHEER-Hub/STARR_DBI) · [Housing Projection PRJ-4651](https://doi.org/10.17603/ds2-tnqp-ag38) · [Full framework PRJ-5985](https://doi.org/10.17603/ds2-n11h-fr68) |
| **STARR-GOV v1** | Adds **five disaster funding designs** (varied by timing, scale, and allocation basis) | Tests how funding structures influence long-term losses, spending, and stakeholder outcomes | [Code](https://github.com/CHEER-Hub/STARR_gov_model_V1) · [Dataset PRJ-6106](https://doi.org/10.17603/ds2-vxbh-cm52) |

---

**Tip:**  
- Use **V0** as the baseline reference.  
- Use **DBI** to study growth and land use policies.  
- Use **GOV v1** to study mitigation funding program designs.  



---

## STARR V0 (Baseline)

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
- **STARR-GOV-V1** extends V0 by incorporating multiple funding design structures.
- More in the future...

### Resources

- **Code (MATLAB):** [STEER repository](https://github.com/CHEER-Hub/STEER)  
- **Code (Python, commented):** [STARR-V0 repository](https://github.com/CHEER-Hub/STARR-V0)  
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

---
Final Mark: V0 is the baseline for comparisons, ensuring that improvements or policy innovations can be clearly measured against a consistent starting point.


---

## STARR-DBI

The **STARR-DBI** model extends the Baseline STARR (V0) by incorporating a **Dynamic Building Inventory (DBI)**. This version accounts for growth and change in the building stock over time, enabling a more realistic representation of long-term hurricane risk and policy outcomes.  

### Key Features
- **Dynamic Building Inventory:** Building counts and household distribution evolve each year, reflecting new construction, acquisitions, and growth patterns.  
- **Land Use Policies:** Implements policy rules that restrict or allow new construction in flood-prone zones based on expected flood depth.  
- **Integrated Risk Assessment:** Losses are separated by existing versus new buildings, showing how land use and acquisition policies affect risk.  
- **Multi-Stakeholder Outcomes:** Captures government spending, insurer profits, and household expenditures as exposure changes over time.  

### Purpose
STARR-DBI was developed to assess how **land use planning and acquisition policies** influence disaster losses, government spending, and household outcomes over time. It captures the dynamic interplay between building growth, policy interventions, and stakeholder decisions in hazard-prone regions.  

### Role in Development
- Builds directly on **STARR V0** by adding a dynamic building–household inventory.  
- Enables evaluation of policies that restrict new development or combine restrictions with acquisitions.  
- Provides insights into how new development interacts with mitigation policies, affecting risk and equity.  

### Resources
- **Code (Python):** [STARR-DBI repository](https://github.com/CHEER-Hub/STARR_DBI)  
- **Housing Inventory Projection Method:** [DesignSafe PRJ-4651](https://doi.org/10.17603/ds2-tnqp-ag38)  
- **Full STARR-DBI Framework (inputs & outputs):** [DesignSafe PRJ-5985](https://doi.org/10.17603/ds2-n11h-fr68)  
- **Publication:** Wang, J., Williams, C., Davidson, R., Nozick, L., & Millea, M. (n.d.). *Coupling Land Use Planning and Multi-Stakeholder Dynamics to Inform Disaster Risk Management: Who Pays for Risk and Who Gains from Intervention?* Under Review, *Earth’s Future*  

### Citation
If you use STARR-DBI, please cite:  
Wang, J., Williams, C., Davidson, R., Nozick, L., & Millea, M. (n.d.). *Coupling Land Use Planning and Multi-Stakeholder Dynamics to Inform Disaster Risk Management: Who Pays for Risk and Who Gains from Intervention?* Under Review, *Earth’s Future*.  

### Requirements
- Python 3.x with standard scientific libraries (numpy, pandas, matplotlib)  
- Additional input datasets for land use restriction factors and housing projections  

### Example Figures
- **Figure 2.** Capacity Reduction Factor vs. Annual Expected Flood Depth:  
  - Baseline strategy (blue, dashed)  
  - Low-restriction strategy (green, dash-dot)  
  - High-restriction strategy (red, solid)  
<img width="251" height="188" alt="image" src="https://github.com/user-attachments/assets/c44b2e35-b25f-4170-ab23-dec2ecd28988" />


- **Figure 3.** Change in outcomes from Year 1 to Year 20 across six strategies varying by land use policy and acquisition. Values include total, insured, and uninsured losses; hazard-specific losses by building type; annual insurer profits; and mean annual household expenditures.  

<img width="468" height="353" alt="image" src="https://github.com/user-attachments/assets/1aec0eca-877c-44e0-abfc-b7c653d1e749" />


### Outputs
Typical outputs include:  
- Losses by year, separated into **existing vs. new buildings** and by hazard type (wind/flood)  
- Effects of acquisition and land use policies on total, insured, and uninsured losses  
- Annual insurer profits and insolvency risk  
- Mean household expenditures across income and risk categories  

---

Final Mark: STARR-DBI highlights how land use restrictions and acquisition programs interact with long-term growth, shaping who bears disaster costs and who benefits from intervention.


---

## STARR-GOV-V1

The **STARR-GOV-V1** model extends the Baseline STARR (V0) by incorporating **five disaster mitigation funding designs**. This version evaluates how the structure of funding—its timing, spatial scale, and allocation basis—shapes long-term outcomes for governments, insurers, and households under repeated hurricane impacts.  

### Key Features
- **Five Funding Designs:**  
  1. **Fixed efficient** – Consistent annual funding; state allocates directly to census tracts with the greatest risk reduction efficiency.  
  2. **Fixed uniform** – Consistent annual funding; state allocates equally to counties, which then allocate to census tracts for efficiency.  
  3. **Fixed population-based** – Consistent annual funding; state allocates to counties based on population, then counties allocate to census tracts for efficiency.  
  4. **Event-triggered efficient** – Post-disaster funding (20% of prior-year damages); state allocates directly to census tracts with greatest efficiency.  
  5. **Event-triggered damage-based** – Post-disaster funding; state allocates to counties based on county-level damage, counties then allocate to census tracts for efficiency.  
- **Policy Design Dimensions:** Vary by timing (consistent vs. triggered), spatial scale (state vs. county), and allocation basis (risk reduction efficiency, damage, or population).  
- **Multi-Stakeholder Outcomes:** Tracks long-term losses, government spending, insurer profits, and household expenditures.  

### Purpose
STARR-GOV-V1 was developed to explore how different designs of **mitigation funding programs** influence both the scale of risk reduction and the distribution of costs and benefits. It highlights trade-offs between efficiency, equity, and timing of investment.  

### Role in Development
- Builds directly on **STARR V0**, focusing on **funding structure** rather than land use or inventory dynamics.  
- Provides the computational basis for comparative policy evaluation across multiple funding strategies.  
- Supports policy-oriented insights on how program design—not just funding levels—affects outcomes.  

### Resources
- **Code (Python):** [STARR-GOV-V1 repository](https://github.com/CHEER-Hub/STARR_gov_model_V1)  
- **Datasets and Outputs:** [DesignSafe PRJ-6106](https://doi.org/10.17603/ds2-vxbh-cm52)  
- **Publication:** Wang, J., Siders, A.R., Davidson, R., & Nozick, L. (n.d.). *Stakeholder Dynamics in Disaster Mitigation Funding: The Roles of Timing, Spatial Scale and Allocation Basis in Policy Design.* Under Review, *Environmental Science & Policy*  

### Citation
If you use STARR-GOV-V1, please cite:  
Wang, J., Siders, A.R., Davidson, R., & Nozick, L. (n.d.). *Stakeholder Dynamics in Disaster Mitigation Funding: The Roles of Timing, Spatial Scale and Allocation Basis in Policy Design.* Under Review, *Environmental Science & Policy*.  

### Requirements
- Python 3.x with standard scientific libraries (numpy, pandas, matplotlib)  
- Input data for funding design experiments included in DesignSafe dataset  

### Example Figure
- **Figure 4.** Expected annual loss (EAL) over a 20-year period under five funding designs: Fixed efficient, Fixed uniform, Fixed population-based, Event-triggered efficient, and Event-triggered damage-based. The figure shows how EAL evolves as acquisitions and retrofits accumulate under each policy design.  

<img width="428" height="248" alt="image" src="https://github.com/user-attachments/assets/3bb499e5-eafc-4ecc-809f-227ca3b1482f" />


### Outputs
Typical outputs include:  
- Expected annual losses (EAL) over time under different funding designs  
- Breakdown of total, insured, and uninsured losses  
- Government spending on acquisitions and retrofits  
- Annual insurer profits and household expenditures  

---

Final Mark: STARR-GOV-V1 demonstrates how **policy design features—timing, scale, and allocation basis—profoundly influence mitigation outcomes**, providing evidence for designing disaster funding programs that are both effective and equitable.


---

## Notes
- We will use consistent naming going forward: **STARR V0**, **STARR-DBI**, **STARR-GOV-V1**  
- Links above should point to the correct GitHub tags/branches  
- For now, this serves as a quick reference outline
