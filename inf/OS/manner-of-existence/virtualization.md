# virtualization

Virtualization is creating something virtual instead of something real.
For the isolated execution of programs, generally either virtual-machine-based virtualization or os-level virtualiztion is used.
A virtual machine is a form of virtualization where an entire operating system is virtualized.

## OS-level virtualization

OS-level virtualization is where multiple isolated user space instances exist on the same OS.

### chroot ＆ chroot jail

chroot changes the root directory of a process, preventing it from changing anything outside.
A chroot jail is the environment set up by chroot.
Often, the basis of OS-level virtualization is a chroot jail.

### containerization

Containerization is (is an implementation) of OS-level virtualization, which generally refers to specifically using OS-level virtualization for running one app, including all its dependencies and its own fs.
Using OS-level virtualization/containerization, interactions with the larger OS is only allowed through limited, specified channels.
An application being contained in a container is said to be containerized.
Containerization improves security and portability.
Containerization is the standard for most mobile operating systems.
Containerization may limit functionality and increase size (since dependencies cannot be shared)
Docker is the most common service for os-level virtualiztion/containerization.

#### docker

In docker, a container is an instance of a container image.
A docker container can be run pretty much anywhere.
A container image contains everything needed to create the container, including the file system, all dependencies, and config.

the command `docker` is used to administer docker.