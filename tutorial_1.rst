==========================
High Performance Computing
==========================

HPC Structure - the Hardware
============================

Important to develop an understanding of

 - how our program(s) will run
 - what the "computer" looks like - login node, head/management node, 
   compute nodes
 - what each of those nodes does and doesn't do ("don't run your job on 
   the login node!")
 - gives us an understanding of approximately what type of efficiencies we 
   can expect, and from this we can determine how many cores/cpus to 
   request
 - gives us an understanding of scheduling/job queueing and how it is done
 - nodes vs cores, why it matters, and when it doesn't 

Operating System and Scheduler
==============================

Learning OS (Linux) command line basics is left as an exercise to the 
reader. While the particular parts of the OS and command line focused on 
aren't particularly hard or obscure, we will focus on them without 
necessarily providing a broader context.

 - concepts: modules and module loading, $PBS_O_WORKDIR, new CLI tools for
   queue analysis, starting and stopping jobs, job dependencies 
 - the scripting details for PBS
 - inputs (reading data in) and outputs (reporting data out) - howto, best
   practice, data transfer and storage (tgz, scp)
 - home directories, temp directories
 - 
   


   
