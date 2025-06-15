---
title: "Slurm"
teaching: 5
exercises: 2
questions:
- "Question 1": Understand what Slurm is, its main features, and how to manage the resources of a cluster.
- "Question 2": Resource optimization: Learn optimization strategies, efficient job management, and resource management.
objectives:
- "Objective 1"
keypoints:
- "Keypoint 1"
---

- Slurm as a workload manager (+practical session: how to use Slurm)

## Intro
Introduction to Slurm 

## Paragraph 1: Understand what Slurm is, its main features, and how to manage the resources of a cluster.

* What is Slurm and why it is used
* Architecture of Slurm: controllers, compute nodes, frontend
* Basic commands: srun, sbatch, squeue, scancel, sinfo
* Job configuration: example scripts, main parameters
* Concepts of partitions, resources, reservations

### Practical exercise:
* Run an example job with srun
* Create a simple batch script and schedule it with sbatch
* Check the status of jobs and resources with squeue and sinfo

## Paragraph 2: Resource optimization: Learn optimization strategies, efficient job management, and resource management.
* Best practices for resource demands (CPU, memory, runtime).
* How to set and use job quality parameters (--ntasks, --cpus-per-task, --mem, --time)
* Scheduling priorities and policies
* Queue and partition management
* Using scontrol and other tools to monitor and improve efficiency

### Practical exercises:
* Create and schedule different jobs with optimized resource requests
* Analyze cluster and job utilization status
* Modify configuration variables to improve efficiency
* Simulate a deadlock or suboptimal resource problem and solve it

{% include links.md %}
