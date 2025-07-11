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



## Commands
Man pages exist for all Slurm daemons, commands, and API functions. The command option --help also provides a brief summary of options. Note that the command options are all case sensitive.

**sacct** is used to report job or job step accounting information about active or completed jobs.

**salloc** is used to allocate resources for a job in real time. Typically this is used to allocate resources and spawn a shell. The shell is then used to execute srun commands to launch parallel tasks.

**sattach** is used to attach standard input, output, and error plus signal capabilities to a currently running job or job step. One can attach to and detach from jobs multiple times.

**sbatch** is used to submit a job script for later execution. The script will typically contain one or more srun commands to launch parallel tasks.

*sbcast* is used to transfer a file from local disk to local disk on the nodes allocated to a job. This can be used to effectively use diskless compute nodes or provide improved performance relative to a shared file system.

**scancel** is used to cancel a pending or running job or job step. It can also be used to send an arbitrary signal to all processes associated with a running job or job step.

*scontrol* is the administrative tool used to view and/or modify Slurm state. Note that many scontrol commands can only be executed as user root.

**sinfo** reports the state of partitions and nodes managed by Slurm. It has a wide variety of filtering, sorting, and formatting options.

**sprio** is used to display a detailed view of the components affecting a job's priority.

**squeue** reports the state of jobs or job steps. It has a wide variety of filtering, sorting, and formatting options. By default, it reports the running jobs in priority order and then the pending jobs in priority order.

**srun** is used to submit a job for execution or initiate job steps in real time. srun has a wide variety of options to specify resource requirements, including: minimum and maximum node count, processor count, specific nodes to use or not use, and specific node characteristics (so much memory, disk space, certain required features, etc.). A job can contain multiple job steps executing sequentially or in parallel on independent or shared resources within the job's node allocation.

*sshare* displays detailed information about fairshare usage on the cluster. Note that this is only viable when using the priority/multifactor plugin.

**sstat is used to get information about the resources utilized by a running job or job step.

*strigger* is used to set, get or view event triggers. Event triggers include things such as nodes going down or jobs approaching their time limit.

*sview* is a graphical user interface to get and update state information for jobs, partitions, and nodes managed by Slurm.

## To have a look to more general commands
[SLURM Quick Start Summary (PDF)](https://slurm.schedmd.com/pdfs/summary.pdf)


MPI use depends upon the type of MPI being used. There are three fundamentally different modes of operation used by these various MPI implementations.

Slurm directly launches the tasks and performs initialization of communications through the PMI2 or PMIx APIs. (Supported by most modern MPI implementations.)
Slurm creates a resource allocation for the job and then mpirun launches tasks using Slurm's infrastructure (older versions of OpenMPI).
Slurm creates a resource allocation for the job and then mpirun launches tasks using some mechanism other than Slurm, such as SSH or RSH. These tasks are initiated outside of Slurm's monitoring or control. Slurm's epilog should be configured to purge these tasks when the job's allocation is relinquished. The use of pam_slurm_adopt is also strongly recommended.

{% include links.md %}
