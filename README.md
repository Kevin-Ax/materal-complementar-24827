# Supplemental Material: A Data Science-Based, Tactical Role Independent, Comprehensive Metric to Evaluate Professional Football Players

This repository contains the supplemental material, datasets, and preliminary experimental results for the paper **"A Data Science-Based, Tactical Role Independent, Comprehensive Metric to Evaluate Professional Football Players"**. 

The purpose of this repository is to ensure reproducibility, transparency, and to provide researchers and analysts with the exact data used to develop and validate the proposed performance metric.

---

## 📂 Repository Structure

* `data/`
  * `raw_statistical_dataset.csv`: The complete dataset featuring comprehensive statistical metrics for professional football players.
  * `club_mapped_dataset.csv`: The same statistical dataset, updated to explicitly map and signal the specific clubs each player represented.
* `experiments/`: Dedicated folder for preliminary tests and experimental benchmarks.

---

## 📊 Datasets Overview

The datasets provided reflect the exact state of the data used throughout the entire study. They bridge raw performance statistics with tactical analysis.

### 1. Complete Statistical Dataset (`raw_statistical_dataset.csv`)
This file contains the full matrix of technical, tactical, and physical performance features extracted during the study. It serves as the baseline for the position-agnostic metric calculations.
* **Scope:** Professional football players.
* **Features Include:** Detailed passing metrics, defensive actions, progression statistics, and attacking outputs.

### 2. Club-Mapped Dataset (`club_mapped_dataset.csv`)
To account for contextual variables and team environments, this dataset is identical in statistical content to the first one but includes explicit variables signaling the **clubs** for which the players played during the analyzed period. 
* **Use Case:** Ideal for analyzing network effects, team-level dependencies, or contextualizing player performance based on team strength.

---

## 🧪 Preliminary Experiments

Before finalizing the comprehensive metric, a series of preliminary evaluations were conducted to benchmark feature importance, attribute combinations, and model consistency. 

### Experiment 1: [Name/Focus of Experiment 1]
> **Status:** Preliminary Results Available
* **Objective:** *[To be completed - e.g., Feature selection sensitivity analysis or algorithm benchmarking]*
* **Key Findings:** *[To be completed]*

### Experiment 2: [Name/Focus of Experiment 2]
> **Status:** Preliminary Results Available
* **Objective:** *[To be completed - e.g., Comparison against traditional role-dependent metrics]*
* **Key Findings:** *[To be completed]*

---

## 🚀 How to Use the Material

### Prerequisites
To explore the datasets or replicate any ongoing analysis, we recommend using Python (via Google Colab or locally) with the following stack:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn