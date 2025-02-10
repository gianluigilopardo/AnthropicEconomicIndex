---
license: mit
pretty_name: EconomicIndex
tags:
- text
viewer: true
configs:
- config_name: default
  data_files:
  - split: train
    path: "onet_task_mappings.csv"
---
## Overview
This directory contains O*NET task mapping and automation vs. augmentation data from "Which Economic Tasks are Performed with AI? Evidence from Millions of Claude Conversations." The data and provided analysis are described below.

**Please see our [blog post](https://www.anthropic.com/news/the-anthropic-economic-index) and [paper](https://assets.anthropic.com/m/2e23255f1e84ca97/original/Economic_Tasks_AI_Paper.pdf) for further visualizations and complete analysis.**

## Data

- `SOC_Structure.csv` - Standard Occupational Classification (SOC) system hierarchy from the U.S. Department of Labor O*NET database
- `automation_vs_augmentation.csv` - Data on automation vs augmentation patterns, with columns:
  - interaction_type: Type of human-AI interaction (directive, feedback loop, task iteration, learning, validation)
  - pct: Percentage of conversations showing this interaction pattern
  Data obtained using Clio (Tamkin et al. 2024)
- `bls_employment_may_2023.csv` - Employment statistics from U.S. Bureau of Labor Statistics, May 2023
- `onet_task_mappings.csv` - Mappings between tasks and O*NET categories, with columns:
  - task_name: Task description
  - pct: Percentage of conversations involving this task
  Data obtained using Clio (Tamkin et al. 2024)
- `onet_task_statements.csv` - Task descriptions and metadata from the U.S. Department of Labor O*NET database
- `wage_data.csv` - Occupational wage data scraped from O*NET website using open source tools from https://github.com/adamkq/onet-dataviz

## Analysis

The `plots.ipynb` notebook provides visualizations and analysis including:

### Task Analysis
- Top tasks by percentage of conversations
- Task distribution across occupational categories
- Comparison with BLS employment data

### Occupational Analysis  
- Top occupations by conversation percentage
- Occupational category distributions
- Occupational category distributions compared to BLS employment data

### Wage Analysis
- Occupational usage by wage

### Automation vs Augmentation Analysis
- Distribution across interaction modes

## Usage
To generate the analysis:

1. Ensure all data files are present in this directory
2. Open `plots.ipynb` in Jupyter
3. Run all cells to generate visualizations
4. Plots will be saved to the notebook and can be exported

The notebook uses pandas for data manipulation and seaborn/matplotlib for visualization. Example outputs are contained in the `plots\` folder.

**Data released under CC-BY, code released under MIT License**

## Contact
You can submit inquires to kunal@anthropic.com or atamkin@anthropic.com. We invite researchers to provide input on potential future data releases using [this form](https://docs.google.com/forms/d/e/1FAIpQLSfDEdY-mT5lcXPaDSv-0Ci1rSXGlbIJierxkUbNB7_07-kddw/viewform?usp=dialog).