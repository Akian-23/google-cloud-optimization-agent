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
