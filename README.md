# Supplemental Material: A Data Science-Based, Tactical Role Independent, Comprehensive Metric to Evaluate Professional Football Players

This repository contains the supplemental material, datasets, and experimental results for the paper **"A Data Science-Based, Tactical Role Independent, Comprehensive Metric to Evaluate Professional Football Players"**. 

The purpose of this repository is to ensure reproducibility, transparency, and to provide researchers and analysts with the exact data used to develop and validate the proposed position-agnostic performance metric.

---

## 📂 Repository Structure

* `data/`
  * `raw_statistical_dataset.csv`: The complete dataset featuring comprehensive individual statistical metrics for professional football players.
  * `club_mapped_dataset.csv`: The same statistical dataset, updated to explicitly map and signal the specific clubs each player represented.
* `experiments/`
  * `Solution_Analysis_K2_K3_Final.pdf`: Diagnostic analysis document evaluating the behavior of feature sets under different cluster configurations.
  * `Relatorio_Ranqueamento_de_Solucoes_com_Pesos_en.pdf`: Comprehensive parametric sensitivity report detailing the behavior of feature optimization when varying performance and scope criteria weights.

---

## 📊 Datasets Overview

The datasets provided reflect the exact state of the data used throughout the entire study. They bridge raw performance statistics with strategic tactical intelligence.

### 1. Complete Statistical Dataset (`raw_statistical_dataset.csv`)
This file contains the full matrix of technical, tactical, and physical performance features extracted during the study from FBRef across multiple seasons. It serves as the baseline for the position-agnostic metric calculations.
* **Scope:** Professional football players.
* **Features Include:** Detailed passing dimensions, defensive metrics (interceptions, tackles, blocks), progression variables, and attacking outputs.

### 2. Club-Mapped Dataset (`club_mapped_dataset.csv`)
To account for contextual variables and team environments, this dataset is identical in statistical content to the first one but includes explicit variables signaling the **clubs** for which the players played during the analyzed period. 
* **Use Case:** Ideal for analyzing network effects, team-level dependencies, or contextualizing player performance based on team strength or tactical systems.

---

## 🧪 Experimental Benchmarks & Feature Selection

Before finalizing the comprehensive general-purpose metric, a series of parametric evaluations were conducted to select the most interpretable, robust, and role-independent attribute combination using Mutual Information (MI), a Greedy Randomized Adaptive Search Procedure (GRASP), and K-Means clustering.

### Experiment 1: Solution Attribute Frequency & Cluster Configuration Analysis ($K=2$ vs $K=3$)
> **Status:** Experimental Results Integrated into Final Paper
* **Objective:** To determine whether a 2-cluster or 3-cluster partition provides the most natural and stable groupings of player performance, and to track how frequently specific features are selected by the optimization algorithm across candidate subsets.
* **Key Findings:** * The **2-Cluster ($K=2$) configuration heavily dominated** the absolute peak of optimization performance (Score), providing cleaner mathematical separation than $K=3$.
  * Globally, `90s-Defensive Actions` emerged as the most resilient attribute (appearing 12 times across top-ranked solutions), followed by `Fld-Goal and Shot Creation` (11 appearances) and `Cmp%.1-Passing` (9 appearances). 
  * Solutions integrating defensive actions and passing accuracy consistently maintained maximum coverage profiles (reaching a Scope ceiling of 12).
* **Role in the Paper:** This experiment justified the choice of **$K=2$** as the structural foundation of the paper's final evaluation framework and highlighted the three optimal pillars of position-agnostic data: defensive volume, creation frequency, and passing efficiency.

### Experiment 2: Parametric Weight Sensitivity Analysis ($\alpha$ vs $\beta$)
> **Status:** Metric Composition Validated
* **Objective:** To evaluate the selection behavior of the GRASP algorithm when altering the trade-off weights between mathematical clustering quality ($\alpha$ for Score) and tactical role versatility/coverage ($\beta$ for Scope).
* **Key Findings:**
  * **Balanced Weights ($\alpha=0.5, \beta=0.5$):** The linear combination of `['90s-Defensive Actions', 'Fld-Goal and Shot Creation', 'Cmp%.1-Passing']` secured the absolute #1 spot with a Balanced Score of 0.7083.
  * **Performance Focus ($\alpha=0.75, \beta=0.25$):** The same trio solidified its dominance with a Balanced Score of 0.8542, while highly offensive variants like `['Fld-Goal and Shot Creation', '90s-Defensive Actions', 'npxG/Sh-Shooting']` climbed to 3rd place.
  * **Scope Focus ($\alpha=0.25, \beta=0.75$):** The ranking inverted to favor maximal position versatility, placing `['90s-Defensive Actions', 'Cmp%.1-Passing', 'Cmp%-Passing']` at the top with a Balanced Score of 0.5994.
* **Role in the Paper:** This experiment directly gave birth to the core metrics evaluated in the final paper: the *Score-Oriented Solution* ($S_s$), the *Balanced Solution* ($S_b$), and the *High-Scope Metric* ($S_a$). These metrics were later validated against Transfermarkt financial values and official Campeonato Brasileiro Série A team standings.

---

## 🚀 How to Use the Material

### Prerequisites
To explore the datasets or replicate any ongoing analysis, we recommend using Python (via Google Colab or locally) with the following stack:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn