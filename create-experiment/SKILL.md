---
name: create-experiment
description: Setup an experiment to be run in a HPC environment. 
---

A proper experiment is placed into experiments/<experiment_name> and should have as key points:

- run.sh, which submits the experiment files to a SLURM cluster. Be careful to setup environment variables (such as sourcing a python env)
- plot.sh, which when run, generates all output plots into plots/experiment/<experiment_name>. Outputs should be plots (png + pdf) and tables (md + tex).
  Ensure that plots have labels and titles and that tables have all relevant data, in addition to a summary table for a quick overview. If an experiment
  compares methods, you can bold the best result. If it compares results to a baseline, you can (in addition to absolute performance) include percentual
  changes along with colored cells to indicate performance. When coloring, use shades of green and red.

experiment_name is AXX_<descriptive_name>, where XX is an increasing unique experiment number. Explore the files in scripts/ to see what can help you with run submission and plot creation. 
Outside of that, keep experiments stand-alone. 

Additionally, read the experiments/ folder to look at other experiments and stay closely in style. 
