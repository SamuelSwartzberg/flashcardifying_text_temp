# the kernel

Primary memory is often divided into kernel space and user space, mainly for security.
Kernel stuff runs in kernel space while user prcesses runs in userspace.
Monolithic kernels do more stuff in kernel space than micokernels.
Instead of doing stuff in kernel space, mircokernels provide servers that do things in userspace.
The daemon responsible for paging (swapper/sched) is the process with PID 0.
A system call is a request to the kernel of an OS.
system call → syscall. 

Drivers run in kernal space.
Drivers expose a well-defined interface of the hardware to the OS, but otherwise act as a black box.