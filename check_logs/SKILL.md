---
name: check-logs
description: Check the logs of experiments.
---

Experiments are ran either with HTCondor or SLURM. Folders to check: .logs or .condor_logs. Experiments also have corresponding .sh files that had submitted them, you can usually find them in the experiments folder. 

General tips: 
- Files have a .out and a .err file, check both. 
- Files can be very large, so only check the last 100-200 lines.
- If you encounter environment-related errors (OOM, etc), check if this is related to the hyperparameter setting (i.e. all jobs with a LoRA rank > 32 fail) 
  or has a seemingly "random" pattern. If the pattern is random, check if all failing jobs where submitted to the same nodes

Workflow:
- check .experiment_log.md until which date jobs have been covered.
- Filter files to check only the most recent ones (first check yesterday, else expand to up to 3 days). 
- Check which runs have failed.
- Match experiments that went wrong to the corresponding experiment number. 
- (if present) Inspect the output tables unders plots/<experiment number> to see possible missing numbers. Check if the corresponding runs failed, if they just have not been submitted yet or if they miss from the experiment setup.
- Explain what went wrong.
- If there is an error, suggest a fix.
- Give advice on how to reschedule.

In the end, put a small write-up of your findings into .experiment_log.md. Append to the end with the date of the runs. 

DONT alter files (by writing or running bash/python that alters files), apart from .experiment_log.md
