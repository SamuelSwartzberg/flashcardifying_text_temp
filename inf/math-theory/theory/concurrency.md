# concurrency

Concurrency is executing multiple things at the same time.

## multithreading

A thread is the smallest sequence of instructions that can be independently managed by a scheduler.
Threads can be divided into kernel and green/virtual/user threads.
green thread = virtual thread = user thread.
kernel threads are those managed by the kernel to be scheduled for some CPU time.
user threads are those threads managed by a user process.
N:1 Threading   all threads of the program map onto one kernel thread
M:N Threading   some amount of threads of the program corresponds to some amount of threads of the os/kernel 
1:1 Threading   1 thread of the program corresponds to 1 thread of the os/kernel

### thread pools

A thread pool is a group of pre-instantiated, idle threads which stand ready to be given work. These are preferred over instantiating new threads for each task when there is a large number of short tasks to be done rather than a small number of long ones. This prevents having to incur the overhead of creating a thread a large number of times.
A thread pool typically processes a queue of tasks waiting for processing.

### workers

Web Workers are threadlike things in JS.
Web Workers come in two flavors, dedicated workers and shared workers.
While a ⟮dedicated worker⟯ is accessible from ⟮a single script only⟯, a ⟮shared worker⟯ is accessible from ⟮multiple scripts⟯, even if ⟮within different windows or frames⟯
Because many JS APIs are not ⟮threadsafe⟯, ⟮Web Workers⟯ have access to ⟮ only a limited subset⟯

Web Workers are created by using the Worker/SharedWorker constructor taking the JS file that implements the worker.
Web Workers as well as the main thread communicate via message passing.
For Web Workers, messages are sent by using the method postMessage and recieved via the message event.
For Web Workers, messages always send a copy of the data.
To handle events in Web Workers, use the error event.
To stop a Web Worker, call the terminate() method on it.

### thread-safety

Thread-safe code is code that will work even if many Threads are executing it simultaneously. 

## concurrency control

concurrency control ensures that correct results for concurrent operations are generated.
Mutual exclusion is the requirement in concurrency control that no thing may access the critical section while another thing is already accessing the critical section.
lock = mutex
A lock or mutex is a thing that enforces mutual exclusion.

## classic problems

### race condition

A race condition is the condition of a system where the behavior of a system depends on the sequence/timing of uncontrollable events.
A race condition is often a flaw that may cause bugs.

### deadlock

flex-container:✫1280px-Process_deadlock.svg.png✫✫220px-Gridlock.svg.png✫
A ⟮deadlock⟯ is a situation where ⟮each member of  a group⟯ is ⟮waiting on another member to do something⟯, and therefore ⟮the system is stuck⟯
⟮Gridlock⟯ is a specific type of ⟮deadlock⟯ that occurs ⟮in a street network⟯
