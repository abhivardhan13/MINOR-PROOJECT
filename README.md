# MINOR-PROOJECT
CPU Task Scheduling Simulation

OVERVIEW:
This project implements three common CPU scheduling algorithms:

First Come First Serve (FCFS)
Shortest Job First (SJF)
Round Robin (RR)
The program efficiently simulates task scheduling through the use of various data structures, which aid in managing processes and their execution sequences. Below, we explain the key data structures involved and their specific roles in the scheduling process.

KEY DATA STRUCTURES:
Vector (vector):

Stores the execution durations of processes that are provided by the user.
The dynamic nature of the vector allows it to grow or shrink based on the number of processes entered.
It provides easy access to process data via simple indexing, which is vital for the scheduling algorithms.
Queue (queue):

Primarily used for the FCFS and Round Robin algorithms to handle processes in the order they arrive or need to continue execution.
The FIFO (First-In-First-Out) property of the queue is essential for both algorithms to maintain the correct processing order.
Priority Queue (priority_queue):

Used in the SJF algorithm to prioritize processes based on their burst time.
The queue ensures that the shortest available process is always selected for execution next.
A custom comparator, comparesjf, is implemented to adjust the queue from a max-heap to a min-heap for this purpose.
Struct (proc):

A custom structure used to define a process, consisting of its execution time (ptime) and its arrival sequence (entry).
This structure helps in managing the processes efficiently and allows us to track both their execution time and entry order, which is crucial for output accuracy.

ALGORITHM BREAKDOWN
First Come First Serve (FCFS):

Processes are executed in the exact order they are entered.
A simple queue handles the processes, ensuring they are executed in sequence.
The start and end times for each process are displayed in the output.
Shortest Job First (SJF):

In this algorithm, the process with the shortest burst time gets executed first.
A priority queue sorts the processes by duration, with the shortest process selected next.
The order of execution, along with their start and end times, is displayed.
Round Robin (RR):

Each process is executed cyclically with a fixed time slice or quantum.
Two queues (q1 and q2) are alternated to manage processes that are still waiting for execution.
The output shows how processes share the CPU time and the time intervals during each execution.

Running the Program
To compile and run the program, follow these steps:

Compile the source code using the following command:

bash
g++ -o CPU_Scheduler CPU_Task_Scheduler.cpp
Execute the program:

bash
./CPU_Scheduler
Follow the on-screen instructions to:

Input the number of processes and their respective execution durations.
Specify the quantum time for the Round Robin algorithm.

Sample Output
CPU TASK SCHEDULING SIMULATION

Enter the number of processes: 3
Enter duration for process 1: 5
Enter duration for process 2: 3
Enter duration for process 3: 7

Enter quantum time for Round Robin: 4

First Come First Serve Schedule:
Process 1 starts at 0, finishes at 5
Process 2 starts at 5, finishes at 8
Process 3 starts at 8, finishes at 15

Shortest Job First Schedule:
Process 2 starts at 0, finishes at 3
Process 1 starts at 3, finishes at 8
Process 3 starts at 8, finishes at 15

Round Robin Schedule:
Process 1 starts at 0, finishes at 4
Process 2 starts at 4, finishes at 7
Process 3 starts at 7, finishes at 11
Process 1 starts at 11, finishes at 12
Process 3 starts at 12, finishes at 15
