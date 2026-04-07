# childcare-desert-elimination
Mixed-integer optimization model for eliminating childcare deserts in New York State using Gurobi

# Eliminating Child Care Deserts in New York State through Optimization

## Overview

This project addresses the problem of childcare deserts in New York State using optimization modeling. A childcare desert is defined as a region where the supply of licensed childcare facilities is insufficient to meet local demand.

Using demographic, economic, and spatial datasets, the project develops optimization models to determine cost-effective strategies for expanding existing childcare facilities and constructing new ones. The goal is to improve accessibility while respecting budget, capacity, and fairness constraints.

---

## Objectives

* Identify the minimum funding required to eliminate childcare deserts
* Incorporate realistic expansion costs and spatial constraints
* Ensure equitable access to childcare across regions
* Optimize allocation of new facilities and expansions under budget limitations

---

## Methodology

### Data Processing

* Integrated multiple datasets at the ZIP code level:

  * Population by age group
  * Employment rates
  * Average income
  * Existing childcare capacity
  * Potential facility locations
* Classified ZIP codes as high-demand or normal-demand based on socioeconomic criteria
* Computed childcare demand and capacity thresholds

---

### Optimization Model

The problem is formulated as a **Mixed-Integer Linear Program (MILP)** and implemented in Python using Gurobi.

Key decision variables:

* Number and type of new facilities built per ZIP code
* Expansion levels of existing facilities
* Allocation of childcare slots (including age-specific capacity)

Core constraints:

* Elimination of childcare deserts (coverage requirements)
* Capacity requirements for children aged 0–5
* Expansion limits for existing facilities
* Budget constraints
* Spatial constraints on facility placement

---

### Model Extensions

#### Task 1: Baseline Model

* Minimize total cost of eliminating all childcare deserts
* No spatial or advanced cost constraints

#### Task 2: Realistic Constraints

* Introduced piecewise-linear expansion costs
* Added geographic spacing constraints for new facilities

#### Task 3: Fairness-Oriented Model

* Introduced equity constraints across ZIP codes
* Changed objective to maximize population-weighted coverage
* Imposed a global budget constraint

---

## Results

### Task 1

* Eliminated all childcare deserts across ~1,825 ZIP codes
* Added approximately 210,000 childcare slots
* Total cost: ~$311 million

### Task 2

* Eliminated over 97% of childcare deserts
* Added ~190,000–200,000 slots
* Remaining deserts due to spatial limitations

### Task 3

* Model found to be infeasible under:

  * $100 million budget
  * Strict fairness constraints
* Demonstrates trade-off between equity and feasibility

---

## Key Insights

* Eliminating childcare deserts is achievable but requires substantial investment
* Expansion of existing facilities is cost-effective but insufficient alone
* Spatial and fairness constraints significantly impact feasibility
* Equity-focused policies may require increased funding or relaxed constraints

---

## Tech Stack

* Python
* Pandas
* NumPy
* Gurobi (Mixed-Integer Linear Programming solver)
* Jupyter Notebook

---

## Repository Structure

```id="t9dj7u"
childcare-optimization/
│
├── data/                 
├── model/     
├── report/        
├── README.md
└── requirements.txt
```

---

## How to Run

```bash id="k8s2mc"
pip install -r requirements.txt
jupyter notebook
```

---

## Contributors

This project was completed as part of a group assignment.

* Hosung Ahn
* Eleni Apostolou
* Tianrun Chen
* Junyang Wu  

---

## My Contribution

* Contributed in the developement and implementation the baseline optimization model (Task 1), including formulation of decision variables, constraints, and objective function
* Contributed to data processing and preparation for the initial model
* Co-authored the project report, with contributions to the methodology, results, and final presentation of the work

---

## Report

See full details in:
`report/childcare_desert_elimination.pdf`

---

## Notes

* This project is for academic purposes
* Gurobi requires a valid license to run the optimization model

