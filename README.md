# Multi-Threaded-Parallel-Sort

__NOTE__: Cannot post this publicly. Please email me at rkwong12@gmail.com to see the source code.

Two variants: Multi-processes and multi-threads.

_Done for CS3650, Computer Systems._

The purpose was to quicksort large quantities of floats quickly.

Program Functionality:
Using a given number of processes or threads:

  Setup the data file of floats
  Take random samples from the floats
  Create partitions or pivots for quicksort
  Sort each sample locally
  Write the sorted sample to the data file.
  
The multi-threaded version writes to a separate file while the multi-process version writes in-place.
  
 
Command line syntax:


Processes:
$ ./ssort [num-threads/processes] data.dat


Threads:
$ ./ssort [num-threads/processes] data.dat data2.dat


The process version used barriers and semaphores to prevent data races, while the threaded version
used the pthread library and its mutexes to lock and broadcast to other threads.
The process version relied on forking and creating child processes rather than using threads.
