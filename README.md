Namespaces: It just limits what a container can see

these are created using syscalls using the unshare syscall

unix 

pid

mounts

network

user id's

interprocess comms



/proc is a pseudo filesystem through which the kernel and userspace can share info

we need to let the kernel know that /proc in the container is the place where we need to populate info about the processes in the container

I have given a flag saying this is a new PID namespace it populates only those stuff running inside the container in that /proc(mount) and only those I can see when i run ps in the container.

This only works for cgroups - v1 and not for the updated cgroups - v2