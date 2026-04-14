# Eliminating Child Care Deserts via Optimization

## Overview
This project develops a data-driven optimization framework to address **child care supply-demand imbalance** in New York State.

The system integrates multi-source datasets and formulates the problem as a **Mixed-Integer Linear Programming (MILP)** model to determine optimal strategies for:
- Expanding existing facilities
- Constructing new facilities
- Allocating limited resources under real-world constraints

The goal is to design a scalable decision-making pipeline that balances **cost efficiency, spatial feasibility, and coverage equity**.

---

## Key Features

- **End-to-end data pipeline**
  - Raw data ingestion → cleaning → feature construction → model-ready datasets
- **Optimization modeling (MILP)**
  - Decision variables for expansion and facility construction
  - Policy-driven constraints (coverage thresholds, capacity limits)
- **Real-world constraint modeling**
  - Piecewise expansion cost functions
  - Spatial filtering using geographic distance (Haversine)
- **Scenario-based analysis**
  - Cost minimization
  - Feasibility under spatial constraints
  - Fairness-aware optimization

---

## System Design

### Data Layer
- Integrated datasets at ZIP-code level:
  - Population (age-segmented)
  - Facility capacity
  - Income & employment indicators
  - Candidate facility locations

- Data preprocessing includes:
  - Missing value handling (strict filtering for consistency)
  - Spatial deduplication (minimum distance constraints)
  - Dataset merging and feature alignment

---

### Modeling Layer

The problem is formulated as a **Mixed-Integer Linear Program (MILP)**:

- **Decision variables**
  - Capacity expansion at existing facilities
  - Number and size of new facilities
  - Allocation of slots for different age groups

- **Objective**
  - Minimize total system cost or maximize coverage under constraints

- **Constraints**
  - Coverage requirements per region
  - Capacity limits and expansion ratios
  - Spatial feasibility constraints
  - Budget and fairness constraints (advanced scenario)

The model is implemented and solved using **Gurobi**.

---

### Spatial Processing

- Distance computation via **Haversine formula**
- Enforced minimum spacing (0.06 miles) between facilities
- Preprocessing-based filtering to reduce model complexity

---

## Repository Structure

├── ChildCareDeserts_Data/        # Raw datasets
├── *.xlsx                        # Cleaned and processed datasets
├── Project 1 Code.ipynb          # Data pipeline + optimization models
├── IEOR4004_Fall25_Project1.pdf  # Problem definition
├── Optimization_Project_1.pdf    # Detailed analysis and results
└── README.md

---

## Results & Insights

- The framework identifies cost-optimal strategies for eliminating supply gaps across regions.
- New facility construction is the primary driver of capacity expansion, while incremental expansion improves cost efficiency.
- Incorporating spatial and cost realism significantly improves solution feasibility and interpretability.

---

## Tech Stack

- **Programming**: Python (Pandas, NumPy)
- **Optimization**: Gurobi (MILP)
- **Data Processing**: Data cleaning, feature engineering
- **Geospatial Processing**: Distance-based filtering

---

## Author
Althea He
Brian Tian Bai
Chloe Liu
Mary Zeng
Thanushree Ramachandraiah
Zhewei Deng (Darren) 

Columbia University | Management Science & Engineering

---

## Notes
This project demonstrates how optimization and data engineering techniques can be applied to large-scale resource allocation problems with real-world constraints.
