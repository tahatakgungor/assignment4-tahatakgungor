# assignment4-tahatakgungor
assignment4-tahatakgungor created by GitHub Classroom


Memory Management Project

The objective of this assignment is to become familiar with the virtual memory address page
replacement algorithms. You will implement FIFO (First-In, First-Out - the first page brought
in is the first to be removed), LRU (Least Recently Used - the least recently accessed page is
the one to be removed) page replacement algorithms part of memory management.
Each process has its own virtual address space, partitioned into chunks called pages. The
memory is logically divided into frames of the same size, ready to hold any virtual memory
pages. Not all pages are loaded into the memory at the same time – only the ones that are
needed by the process to run. When a process accesses a page that is not in the memory, a
page fault is generated and the requested page must be brought into the memory. If there is
no free memory frame to host the new page, then a victim page must be evicted from memory
to make room for the new page, so that the process can continue execution. The selection of
the victim page is made according to a specific page replacement policy.
Page replacement algorithms assume a fixed number of memory frames. We will work under the following assumptions:

• The virtual memory of the process consists of NP pages, numbered 0 through NP-1.

• A page reference stream is a sequence of integers ranging from 0 to NP-1. Each integer represents one reference to page.

• The main memory consists of NF frames, numbered 0 through NF-1. This is represented
as an array Frames. Each entry in the array Frames contains the number of the page
currently residing in that frame.


Implementation Steps:

• Your program should take three parameters on the command line, the first for number
of frames, the second for which algorithm to use, and the third for the filename to
examine. The possible values for the first argument are 3, 4, and 5, the possible values
for the second argument are FIFO and LRU, and the third parameter can be any valid
filename. Make sure you handle invalid arguments. For instance, a valid run of your
program might look like

Assignment4.java 3 FIFO data1.txt or
Assignment4.c 3 FIFO data1.txt

If the parameters are not valid or missing, you should print an error message and exit.


• Read the reference stream from the input file and save it in an array.

• Implement methods for FIFO and LRU that use the array and frame number and
calculate the page faults.

• Print the output with total page faults.


Example Input/Output:

Input : 0 1 2 0 3 0 4 2 3 2

Output:

0 --> [0]

1 --> [0 1]

2 --> [0 1 2]

0 --> [0 1 2]

3 --> [0 3 2] page fault

0 --> [0 3 2]

4 --> [0 3 4] page fault

2 --> [0 2 4] page fault

3 --> [3 2 4] page fault

2 --> [3 2 4]

Total number of page faults is 4.
