==========================
High Performance Computing
==========================

HPC Structure - the Hardware
============================

What does a High Performance Computer look like, and why do I need to know?

There is no need for users to have a comprehensive understanding of the HPC 
hardware, but there is a need for users to have some idea of what it looks 
like - how it is made up.

HPC is normal computing, writ large. There is more RAM ("memory"), more CPU, 
more HD, more network bandwidth.

As such, we are more thoughtful about how we use those resources.

 -------------                                        ---------------
 | MGMT NODE |  >-------+                 +---------< | WORKER NODE |
 -------------          +-----------------+           ---------------
                        |                 |
 --------------         |  Network switch |           --------------- 
 | LOGON NODE | >-------+-----------------+---------< | WORKER NODE |
 --------------         |                 |           ---------------
                        |                 |
                        |                 |           ---------------
 -------------          |                 +---------< | WORKER NODE |
 |           | >--------+                             ---------------
 |  STORAGE  |
 |           |
 -------------


The Storage is the hard drive space - we don't need to worry too much about it, 
just know it exists.

The network switch is how all of these parts communicate, and is again 
relatively neutral, although we will address latency (speed of data across the 
network) when thinking about how to set up our projects.

THIS IS THE IMPORTANT STUFF:

The LOGON NODE looks after all of your authentication credentials, including 
the creation of your "home" space: /home/<username>. This home space is 
generic and shared across the cluster.

The Management (MGMT) Node does all the traffic control, manages the worker 
nodes and, most importantly, runs the program you would like to run.

This is an important distinction. The LOGON NODE is where you end up when 
you have logged in. It is important to remember to switch to the MGMT NODE when
running your programs so the LOGON NODE isn't rendered unusable by your large 
project. It has been specifically built for a single reason - to manage users 
and logins. The MGMT NODE is designed to run projects and farm out the work to 
the worker nodes.

Accidentally run your project on the LOGON NODE and you will have a bad 
experience: other people will have degraded experiences (probably wont be able
to do anything), your project will not run on the full power of the HPC, and
an admin will most likely kill it.

Each WORKER NODE has 16 cores and 64 GB of memory. The MGMT NODE will distibute
your project across the cores and nodes as necessary.

The current system has 180 WORKER NODES for 2880 cores total.

Working notes:
It's important for users to understand how HPC is constructed physically because:

 - there are performance reasons (it *is* HPC after all, this is no butter knife, it's a chainsaw.)
 - there is the practical *result* reason - an understanding of how to get the *best* result from HPC. If your project gets no positive value, why use HPC in the first place?
 - there is the practical working reason - without an understanding you may break it.


---------------------------------------------------------------- 


HPC Structure - the efficiencies 
================================

The first and most obvious efficiency is that the cluster can do parallel 
computing. With that many nodes and cores, a lot of software can perform with
better throughput.

This is the difference between a four core laptop taking a month to run a
complex function in MatLab and the cluster running in in tens of minutes 
utilising numerous cores - as many as you request.

working notes
 - gives us an understanding of approximately what type of efficiencies we 
   can expect, and from this we can determine how many cores/cpus to 
   request


HPC Structure - the limits
==========================

If you request more than 128 cores, you may be waiting a long time for 
those cores to be free. 




Working notes:

 - gives us an understanding of scheduling/job queueing and how it is done
 - nodes vs cores, why it matters, and when it doesn't 





   
