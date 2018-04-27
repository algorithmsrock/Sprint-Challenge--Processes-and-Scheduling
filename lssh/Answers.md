Multiple choice and Short Answer Questions

Add your answers inline, below, with your pull request.

1. List all of the main states a process may be in at any point in time on a standard Unix system. Briefly explain what each of these states mean.

   Created - New Process that is first created by the scheduler. The Create processes awaits admission to the "ready" state. 
	 Admission typically will be approved automatically unless there are too many processes admitted to the "ready" state which will saturate the system's resources
	 and lead to an inability to meet process deadlines.

	 Ready - A "ready" or "waiting" process has been loaded into main memory and is awaiting execution on a CPU. 
	 There are multiple "ready" processes at any one point of system's execution, while computers are capable of "running" many different processes, 
	 the CPU is only capable of handling one process at a time. Processes ready for the CPU are kept in a queue for ready processes. 
	 Other processes waiting for events to occur are not in the ready queue.  
	 
	 Running - A process moves into the running state when its chosen for execution. The process's instructions are executed by one of the CPU or cores of the system.
	 There can only be one running process per CPU or core. A process can "run" in either of the modes, kernel mode or user mode.
	 
	 Blocked - A process transitions to a "blocked" state when it cannot carry on without an external change in state or event occuring. Processes also commonly block when 
	 they require user input or require access to a critical section which must be executed atomically. Such critical sections are protected using a synchronization object
	 such as a semaphore or mutex.

	 Terminated - A process can be terminated either from the "running" by completing its execution or explicitly being killed. In either or these cases, the process moves to
	 the "terminated" state. The underlying program is no longer executing, but the process remains in the process table as a zombie process until its parent process calls the
	 wait system call to read its exit status, at which point the process is removed from the process table, finally ending the process's lifetime.

2. What is a Zombie Process? How does it get created? How does it get destroyed?
    
   A Zombie Process is a process that has completed execution from the exit system call but still has a entry in the process table. It is a process in the Terminated state. 
	 This occurs for child processes, where the entry is still needed to allow the parent process to read the child's exit status: once the exit status is read via the wait 
	 system call, the zombie's entry is destroyed and removed from the process table and it is said to be "reaped". Since, zombie processes are not normal processes, the kill 
	 command has no effect on them. 

3. Describe the job of the Scheduler in the OS in general.
      

4. Describe the benefits of the MLFQ over a plain Round-Robin scheduler.

