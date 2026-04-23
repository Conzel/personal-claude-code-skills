---
name: check-logs
description: Check the logs of experiments.
---

Experiments are ran either with HTCondor or SLURM. Folders to check: .logs or .condor_logs. Experiments also have corresponding .sh files that had submitted them, you can usually find them in the experiments folder. 

General tips: 
- Files have a .out and a .err file, check both. 
- Files can be very large, so only check the last 100-200 lines.

Workflow:
- Filter files to check only the most recent ones (first check yesterday, else expand to up to 3 days). 
- Check which runs have failed.
- Match experiments that went wrong to the corresponding experiment number. 
- (if present) Inspect the output tables unders plots/<experiment number> to see possible missing numbers. Check if the corresponding runs failed, if they just have not been submitted yet or if they miss from the experiment setup.
- Explain what went wrong.
- If there is an error, suggest a fix.
- Give advice on how to reschedule.
