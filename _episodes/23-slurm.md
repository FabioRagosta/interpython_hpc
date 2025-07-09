---
title: "Slurm"
teaching: 5
exercises: 0
questions:
- "Question 1"
objectives:
- "Objective 1"
keypoints:
- "Keypoint 1"
---

- Slurm as a workload manager (+practical session: how to use Slurm)

## Intro
Slurm is an open source, fault-tolerant, and highly scalable cluster management and job scheduling system for large and small Linux clusters. Slurm requires no kernel modifications for its operation and is relatively self-contained. As a cluster workload manager, Slurm has three key functions. First, it allocates exclusive and/or non-exclusive access to resources (compute nodes) to users for some duration of time so they can perform work. Second, it provides a framework for starting, executing, and monitoring work (normally a parallel job) on the set of allocated nodes. Finally, it arbitrates contention for resources by managing a queue of pending work. 

## Architecture 
Slurm has a centralized manager, slurmctld, to monitor resources and work. There may also be a backup manager to assume those responsibilities in the event of failure. Each compute server (node) has a slurmd daemon, which can be compared to a remote shell: it waits for work, executes that work, returns status, and waits for more work. The slurmd daemons provide fault-tolerant hierarchical communications. There is an optional slurmdbd (Slurm DataBase Daemon) which can be used to record accounting information for multiple Slurm-managed clusters in a single database. There is an optional slurmrestd (Slurm REST API Daemon) which can be used to interact with Slurm through its REST API. User tools include srun to initiate jobs, scancel to terminate queued or running jobs, sinfo to report system status, squeue to report the status of jobs, and sacct to get information about jobs and job steps that are running or have completed. The sview commands graphically reports system and job status including network topology. There is an administrative tool scontrol available to monitor and/or modify configuration and state information on the cluster. The administrative tool used to manage the database is sacctmgr. It can be used to identify the clusters, valid users, valid bank accounts, etc. APIs are available for all functions.



[SLURM Quick Start Summary (PDF)](https://slurm.schedmd.com/pdfs/summary.pdf)
{% include links.md %}
