# Conjoint Analysis on Smart Glasses

This project evaluates **which smart-glasses features matter most to consumers** and what product configuration is likely to win in the market. I combined **qualitative interviews** with a **survey-based conjoint study** (built and distributed using **Qualtrics**) and estimated **part-worth utilities** and **attribute importance** using **XLSTAT (OLS, ranking-based conjoint)**.

---

## Overview

Smart glasses combine eyewear with capabilities like cameras, AR navigation, and AI assistants. The goal of this study was to quantify **feature trade-offs** and identify an **optimal product concept** aligned with user preferences.

**Core question:**  
> “If we change price, camera quality, interaction method, and AR features, what drives preference the most?”

---

## Research Workflow (What I Did)

### 1) Exploratory Research — Interviews
I conducted target-group interviews and discussions to:
- Understand desired use-cases (navigation, hands-free utility, content capture)
- Identify adoption barriers (privacy, comfort, price sensitivity)
- Finalize a realistic set of conjoint **attributes + levels**

### 2) Survey Design & Data Collection — Qualtrics
- Built a ranking-based conjoint survey in **Qualtrics**
- Collected respondent rankings of product profiles
- Exported results for analysis and modeling

### 3) Conjoint Modeling — XLSTAT
- Ran a **Conjoint Analysis (OLS)** with **Ranking** as the response type
- Estimated:
  - **Part-worth utilities** (preference contribution of each feature level)
  - **Attribute importance (%)**
- Ran a **market simulation (First Choice)** to estimate **market shares** for competing product concepts

---

## Data

### `profiles_data.csv`
Contains:
- The 10 evaluated profiles (product concepts)
- Attribute levels per profile (Price, Camera, Interaction, etc.)
- Individual respondent rankings for each profile

### `conjoint_analysis_report.csv`
Contains XLSTAT output:
- Part-worth utilities (individual + descriptive statistics)
- Attribute importances (individual + mean)
- Model configuration: **OLS**, **Ranking response**, constraint **a1 = 0**
- Simulation outputs (utilities and market share)

---

## Attributes & Levels

| Attribute | Levels |
|---|---|
| **Price** | $250, $300, $500 |
| **Camera** | 8 Mp, 12 Mp |
| **Interaction Method** | Gesture, Voice |
| **Bone Conduction Audio** | No, Yes |
| **AI Assistant** | No, Yes |
| **360° View** | No, Yes |
| **AR Map Navigation** | No, Yes |
| **Polarisation** | No, Yes |

---

## Key Results

### Attribute Importance (Mean)
Based on the conjoint model, the average importance across respondents was:

- **Price:** 22.032%
- **Camera:** 16.181%
- **Polarisation:** 13.125%
- **Bone Conduction Audio:** 12.004%
- **AI Assistant:** 10.043%
- **360° View:** 9.479%
- **Interaction method:** 8.650%
- **AR Map navigation:** 8.485%

**Interpretation:** Price is the strongest driver overall, followed by camera quality and “core eyewear” value (polarisation), then audio + AI features.

---

## Part-Worth Utility Insights (Descriptive Mean)

Higher utility = higher preference.

### Price (reference level = $250)
- **$300:** -0.462 (less preferred than $250)
- **$500:** -1.192 (strongly less preferred)

### Camera (reference = 8 Mp)
- **12 Mp:** +0.288 (preferred)

### Interaction (reference = Gesture)
- **Voice:** -0.141 (slightly less preferred than gesture)

### Bone Conduction Audio (reference = No)
- **Yes:** +1.301 (strong positive preference)

### AI Assistant (reference = No)
- **Yes:** +0.679 (preferred)

### 360° View (reference = No)
- **Yes:** +0.231 (slightly preferred)

### AR Map Navigation (reference = No)
- **Yes:** +0.333 (preferred)

### Polarisation (reference = No)
- **Yes:** +0.865 (strong preference)

---

## Recommended “Best” Concept (Highest-Utility Configuration)

Based on selecting the highest-utility level for each attribute:

- **Price:** $250  
- **Camera:** 12 Mp  
- **Interaction:** Gesture  
- **Bone Conduction Audio:** Yes  
- **AI Assistant:** Yes  
- **360° View:** Yes  
- **AR Map Navigation:** Yes  
- **Polarisation:** Yes  

This is the most preferred configuration according to the estimated average part-worths.

---

## Market Simulation (First-Choice Share)

I simulated a market with **11 competing product concepts** and estimated market shares using a **First Choice** rule.

**Notable outcome:**  
- **Product/Profile 11** achieved **~19.231% market share**, one of the highest in the simulation.

**Profile 11 configuration:**
- Price: **$300**
- Camera: **12 Mp**
- Interaction: **Gesture**
- Bone Conduction Audio: **Yes**
- AI Assistant: **Yes**
- 360° View: **Yes**
- AR Map Navigation: **No**
- Polarisation: **No**

**Interpretation:** Even though $250 is preferred in isolation, Profile 11 appears to hit a strong **feature–price balance** that appeals to a large share of respondents under competitive choice conditions.

---

## Tools Used

- **Qualtrics** — survey design & data collection  
- **XLSTAT (Student 2023.3.1.1416)** — conjoint analysis + simulations  
- **Microsoft Excel** — data preparation and reporting

---

## Notes on Privacy
Interview and survey data may include personal information. Any public release should remove personally identifying details.

---

## Author
Satvik Reddy Tanuboddi  
GitHub: https://github.com/SatvikReddyTanuboddi1
