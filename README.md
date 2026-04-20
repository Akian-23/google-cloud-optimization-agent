# google-cloud-optimization-agent
# Google Cloud Server Allocation Optimization

## Overview
This project optimizes server allocation in Google Cloud data centers to minimize infrastructure cost while maintaining fast response times. It identifies mathematically efficient solutions using multi-objective optimization.

## Business Problem
Cloud providers must balance cost and performance when allocating servers. Over-provisioning increases expenses, while under-provisioning risks SLA violations. This optimization engine helps identify the best tradeoffs.

## Status
🚧 Work in Progress - Part 1: Optimization Engine (Unit 11)

## Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Setup
Instructions coming soon...

## Part 1: Optimization Engine (Complete ✓)

### What It Does
This optimization engine analyzes 52 possible combinations of Google Cloud VM infrastructure decisions, including machine type, region, and instance count. The system evaluates how these decisions affect two key objectives: monthly infrastructure cost and system latency. Using Pareto frontier analysis, the engine identifies which configurations represent efficient tradeoffs between these objectives.

### Key Findings
- 52 infrastructure configurations were evaluated
- 16 solutions (30.8%) were Pareto optimal
- 36 configurations were dominated and represent inefficient infrastructure choices
- High-performance machines dramatically reduce latency but increase cost significantly
- Mid-range machine types often provide balanced cost-performance tradeoffs
- Some strategies converge (ex: Balanced and Latency-Priority), highlighting how objective scaling influences optimization results

### Running the Analysis
1. Ensure the following Python packages are installed: `pandas`, `numpy`, `matplotlib`
2. Open `optimization_engine.ipynb`
3. Run all cells sequentially
4. Generated visualizations will appear in the `images/` directory

### Next Steps
Part 2 will introduce a constraint-aware decision agent capable of selecting optimal infrastructure configurations from the Pareto frontier based on organizational constraints such as budget limits, performance requirements, or service-level targets.



# Part 2: Constraint-Aware Decision Agent (Complete ✓)

## What the System Does

The decision agent extends the optimization engine by:

- Filtering infeasible infrastructure options using business constraints
- Applying rule-based decision logic based on business context
- Generating explainable recommendations for decision-makers

## Key Findings

- Applied business constraints to Pareto-optimal solutions
- Reduced solution space to feasible, real-world options
- Agent adapted decisions across multiple business scenarios:
  - Budget cuts
  - High traffic / demand surge
  - Normal operations

- Final recommendation balances:
  - Cost efficiency
  - System performance (latency)
  - Business urgency

## Agent Features

- **Input:** Business scenario (priority, urgency, competitive pressure)
- **Output:** Recommended machine type + region
- **Explainability:** Step-by-step reasoning
- **Scenario Testing:** Behavior validated across multiple conditions

## Important Insight

Monthly cost and latency are on different scales:

- Cost values are much larger (hundreds–thousands)
- Latency values are smaller (tens–hundreds ms)

As a result:
- visualizations may appear cost-dominated
- normalization is required for fair comparison

This reflects unit differences, not model bias.

## Running the Agent

1. Run Phase 1 (optimization engine)
2. Execute all Phase 2 cells in `optimization_engine.ipynb`
3. Modify scenarios in Part 2.4 to test behavior
4. View final recommendation in Part 2.6

## Technologies Used

- Python (pandas, numpy, matplotlib)
- Jupyter Notebook
- Multi-objective optimization
- Rule-based decision system


## Next Steps

- Record executive presentation video (Unit 14)
- Discuss limitations and improvements
- Present complete system as portfolio piece