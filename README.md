Operating System Overview
An operating system (OS) is an interface between the user and the computer hardware. It manages hardware resources and provides services for application software.

Components
System Software: OS, Drivers
Application Software: Media players, Text editors (e.g., Word, Excel)
Services of OS
User Services
Program Execution: Programs must be loaded into main memory for execution.
User Interface:
CLI (Command Line Interface): Text-based commands (e.g., DOS)
GUI (Graphical User Interface): Visual elements like windows and icons (e.g., Windows, Linux, Mac)
System Services
I/O Operations: Manages input/output devices.
IPC (Inter-process Communication): Facilitates communication between processes.
File System & Manipulation: Store, delete, search, retrieve, and create data.
Resource Allocation: Manages resources among processes.
Security & Protection: Prevents unauthorized access, manages file permissions, and uses firewalls.
Accounting: Manages different user accounts.
Types of OS
Batch Operating System: Jobs are processed in batches without user interaction.
Multiprogrammed OS: Multiple jobs are loaded into memory and executed by the CPU.
Multiprocessing OS: Multiple CPUs are used to execute multiple processes simultaneously.
Distributed OS: Multiple computers are used to provide a cohesive system.
Real-Time Operating System: Processes are executed within a strict time limit.
Hard Real-Time OS: No delays are tolerated.
Soft Real-Time OS: Some delays are acceptable.
Embedded Systems: Designed for specific control functions within larger systems.
Functions of OS
Memory Management: Manages primary and secondary memory.
Process Management: Handles process creation, scheduling, and termination.
Device Management: Manages device communication via drivers.
File Management: Organizes, stores, retrieves, and manages data.
Security: Protects data and resources from unauthorized access.
Job Accounting: Tracks resource usage for billing and analysis.
Process Management
Process Scheduling: Determines which process should execute first and allocates CPU time.
Device Management: Maintains the status of all devices and allocates them to processes.
File Management: Tracks files and directories, managing storage and retrieval.
Security: Protects against unauthorized access using passwords.
Job Accounting: Tracks time and resources used by users.
Error Detection: Monitors and reports system errors.
Coordination: Provides language translators like compilers and interpreters.
Kernel
What is Kernel?
The kernel is the core part of the operating system. It acts as an interface between hardware and processes. It loads first in memory and remains until the OS is shut down.

Functions of Kernel
Device Management
Task Management
Memory Management
System Calls
System Calls
Provide an interface between applications and the kernel. Allow processes to request services from the OS.

Types of System Calls
Process Control: Creating and terminating processes.
File Management: File creation, reading, and writing.
Device Management: Device manipulation.
Information Maintenance: Managing system data.
Communication: Inter-process communication (IPC).
Examples
Windows: CreateProcess(), ReadFile()
Linux: fork(), read()
System Programs
Provide an environment to develop and execute programs.

Types include:
Status Information: System date, time, and memory usage.
Communication: Remote login and email.
File Management: File creation and deletion.
File Modification: Editing files using text editors.
Program Loading and Execution: Loading programs into memory.
Programming Language Support: Compilers and interpreters.
Process State Diagram
Process States
NEW: Process is about to be created.
READY: Process is ready for execution.
RUNNING: Process is being executed by the CPU.
TERMINATED: Process has completed execution.
BLOCK/WAIT: Process is waiting for I/O operations.
Preemption
High priority process interrupts (preemption).
Non-Preemption: No interruption allowed.
Schedulers
Long-Term Scheduler: Manages processes in secondary memory.
Mid-Term Scheduler: Manages suspended processes.
Short-Term Scheduler: Allocates CPU time to processes.
Scheduling Criteria
CPU Utilization: Measures how long the CPU is busy.
Throughput: Number of processes executed in a unit of time.
Turnaround Time: Total time taken for execution (End time - Arrival time).
Wait Time: Time a process waits to get CPU.
Response Time: Time from the start of execution to the first response.
Scheduling Algorithms
First Come First Serve (FCFS)
Type: Non-Preemptive
Description: Processes are executed in the order they arrive.
Metrics:
Turnaround Time (TAT): Completion Time - Arrival Time
Waiting Time (WT): Turnaround Time - Burst Time
Shortest Job First (SJF)
Mode: Non-Preemptive
Description: Executes the process with the shortest burst time first.
Shortest Remaining Time First (SRTF)
Mode: Preemptive
Description: Similar to SJF but allows interruption if a new process arrives with a shorter burst time.
Priority Scheduling Algorithm
Non-Preemptive Mode
Description: Processes are scheduled based on priority. Lower numbers indicate higher priority.
Preemptive Mode
Description: Similar to non-preemptive but allows interruption if a higher priority process arrives.
Round Robin Scheduling Algorithm
Description: Each process is assigned a fixed time slot (time quantum) in a cyclic order.
Page Replacement Algorithms
Introduction
Page: A fixed-length contiguous block of virtual memory.
Frame: A fixed-length block of physical memory.
Swapping: Moving pages between main memory and secondary storage.
Page Fault: Occurs when a requested page is not in memory.
Techniques
FIFO (First In First Out)
Pages are replaced in the order they were loaded.
Example: Page reference stream and calculation of page faults and hits.
Hit Ratio: Number of hits divided by the total number of page requests.
Belady’s Anomaly
An increase in the number of frames can lead to an increase in page faults in some cases.
Illustrated with examples showing different frame allocations.
Least Recently Used (LRU)
Replaces the page that has not been used for the longest period of time.
Example: Page reference stream and calculation of page faults and hits.
Optimal Page Replacement
Replaces the page that will not be used for the longest period of time in the future.
Example: Page reference stream and calculation of page faults and hits.
Threads
Overview
Process: A task under execution by the CPU.
Thread: A lightweight process or a segment of a process.
Improves CPU utilization and application performance.
Allows multiple threads within a single process.
Types of Threads
User-Level Threads
Managed by user-level libraries.
Not recognized by the OS.
Easy context switching.
Blocking operations affect all threads.
Kernel-Level Threads
Managed by the OS.
Recognized by the OS.
More complex context switching.
Blocking operations do not affect other threads.
Multithreading
Running multiple threads concurrently within a process.
Benefits include shared memory and data, simple context switching, and efficient inter-process communication.
Comparison: Process vs. Thread
Process:
Independent execution, more resource-intensive, longer creation and termination time.
Does not share memory/data, more time for IPC, and context switching.
Thread:
Part of a process, shares resources, faster creation and termination.
Errors in one thread can affect others.
Thread Management and Synchronization
Thread Library
Provides code for thread creation, deletion, and data transfer.
Hardware support is not required.
OS runs on any OS.
Thread management is different for user-level and kernel-level threads.
Thread Models
Mapping of User-Level Threads to Kernel-Level Threads:
User-level threads are created by the user and not recognized by the OS.
Kernel-level threads are created by the OS and recognized by it.
Models:
Many-to-One (M:1): Multiple user threads mapped to a single kernel thread.
One-to-One (1:1): Each user thread maps to a kernel thread.
One-to-Many (1:M): One user thread maps to multiple kernel threads.
Process Synchronization
Independent Process: Execution of one process does not affect others; no shared memory.
Co-operative Process: Execution of one process affects others; shared memory is used, leading to race conditions.
Producer-Consumer Problem
Involves two processes:
Producer: Produces items and places them in a buffer.
Consumer: Consumes items from the buffer.
Conditions:
Producer must check if the buffer is not full before placing items.
Consumer must check if the buffer is not empty before consuming items.
Critical Section Problem
Critical Section: A section of code where shared resources are accessed.
Requirements:
Mutual Exclusion: Only one process can be in the critical section at a time.
Progress: If no process is in the critical section, others can enter.
Bounded Waiting: Each process should have a bounded waiting time to enter the critical section.
Semaphores
Definition: An integer variable used to manage concurrent processes and prevent race conditions.
Types:
Binary Semaphore: Value is 0 or 1.
Counting Semaphore: Non-negative integer, allows multiple resources.
Advantages:
Prevents race conditions and deadlocks.
Implements mutual exclusion.
Disadvantages:
Improper use can lead to deadlocks.
High maintenance with more semaphores.
Difficult to debug synchronization issues.
Deadlocks
Definition
A deadlock is a situation where one or more processes are waiting for resources that are allocated to other processes, causing a standstill.

Example
Two processes, P1 and P2, and two resources.
P1 is allocated R1, and P2 is allocated R2.
If P1 requires R2 for completion (allocated to P2) and P2 requires R1 for execution (allocated to P1), a deadlock occurs.
Conditions for Deadlocks
Mutual Exclusion: Only one process can use a resource at a time.
Hold and Wait: Processes holding resources can request additional resources.
No Preemption: Resources cannot be forcibly taken from a process; the process must release them voluntarily.
Circular Wait: A closed chain of processes exists, where each process holds at least one resource needed by the next process in the chain.
Deadlock Detection
Resource Allocation Graph:

A tool to detect deadlocks, containing details about resources and processes.
Vertices: Represent processes (circles) and resources (rectangles).
Edges:
Assigned Edge: Resource is allocated to a process.
Requested Edge: Process is requesting a resource.
Single Instance:

If a cycle forms in the graph, a deadlock is present.
If no cycle forms, no deadlock exists.
Multiple Instances:

A cycle may indicate a deadlock, but not always.
If no cycle forms, no deadlock exists.
Formula for Minimum Resources:

R
≥
P
×
(
N
−
1
)
+
1
R≥P×(N−1)+1
R
R: Number of resources
P
P: Number of processes
N
N: Number of resource units
This formula helps determine the minimum resources needed to avoid deadlocks.
