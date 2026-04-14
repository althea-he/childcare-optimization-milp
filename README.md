# 🗽 Eliminating Child Care Deserts via Optimization

## 📌 Overview
This project builds a data-driven optimization system to address child care supply-demand imbalance in New York State.

The system integrates multi-source datasets and formulates the problem as a Mixed-Integer Linear Programming (MILP) model to determine optimal strategies for:

- Expanding existing facilities  
- Constructing new facilities  
- Allocating limited resources under real-world constraints  

The goal is to design a scalable decision-making pipeline that balances cost efficiency, spatial feasibility, and coverage equity.

---

## 🚀 Key Features

### 🧩 End-to-End Data Pipeline
- Raw data ingestion → cleaning → feature engineering → model-ready datasets  
- ZIP-level data integration across multiple sources  

### 📊 Optimization Modeling (MILP)
- Decision variables for expansion and facility construction  
- Policy-driven constraints (coverage thresholds, capacity limits)  

### 🌍 Real-World Constraint Modeling
- Piecewise expansion cost functions  
- Spatial filtering using geographic distance (Haversine)  

### ⚖️ Scenario-Based Analysis
- Cost minimization  
- Feasibility under spatial constraints  
- Fairness-aware optimization  

---

## 🏗️ System Design

### 📦 Data Layer
Integrated datasets at ZIP-code level:
- Population (age-segmented)  
- Facility capacity  
- Income & employment indicators  
- Candidate facility locations  

Data preprocessing includes:
- Missing value handling (strict filtering for consistency)  
- Spatial deduplication (minimum distance constraints)  
- Dataset merging and feature alignment  

---

### 🧠 Modeling Layer
The problem is formulated as a **Mixed-Integer Linear Program (MILP)**:

**Decision Variables**
- Capacity expansion at existing facilities  
- Number and size of new facilities  
- Allocation of slots for different age groups  

**Objective**
- Minimize total system cost OR maximize coverage under constraints  

**Constraints**
- Coverage requirements per region  
- Capacity limits and expansion ratios  
- Spatial feasibility constraints  
- Budget and fairness constraints (advanced scenario)  

**Solver**
- Gurobi (Python)  

---

### 📍 Spatial Processing
- Haversine distance calculation  
- Minimum spacing enforcement (0.06 miles)  
- Preprocessing to reduce model complexity  

---

## ⚙️ How to Run

```
# Create environment
conda env create -f environment.yml

# Activate environment
conda activate your_env_name

# Run notebook
jupyter notebook "Project 1 Code.ipynb"

```

## 📂 Repository Structure

```
├── ChildCareDeserts_Data/        # Raw datasets
├── *.xlsx                        # Cleaned datasets
├── Project 1 Code.ipynb          # Modeling & experiments
├── IEOR4004_Fall25_Project1.pdf  # Problem definition
├── Optimization_Project_1.pdf    # Final report
└── README.md
```

## 📈 Results & Insights
	•	The framework identifies cost-optimal strategies for eliminating supply gaps across regions
	•	New facility construction is the primary driver of capacity expansion
	•	Incremental expansion improves cost efficiency
	•	Spatial and cost constraints significantly impact feasibility

## 🛠️ Tech Stack
	•	Python (Pandas, NumPy)
	•	Gurobi (MILP)
	•	Data Engineering & Feature Engineering
	•	Geospatial Processing

## 👥 Contributors
	•	Althea He
	•	Brian Tian Bai
	•	Chloe Liu
	•	Mary Zeng
	•	Thanushree Ramachandraiah
	•	Zhewei Deng


## ✨ Notes

This project demonstrates how optimization and data engineering techniques can be applied to large-scale resource allocation problems with real-world constraints.
  
