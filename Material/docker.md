


## Docker

Magic behind the docker's success can be realized when we have an basic idea about the [Union File System](http://unionfs.filesystems.org/)

**Union FS  :**
Unionfs is a filesystem service for Linux, FreeBSD and NetBSD which implements a union mount for other file systems. It allows files and directories of separate file systems, known as branches, to be transparently overlaid, forming a single coherent file system. Contents of directories which have the same path within the merged branches will be seen together in a single merged directory, within the new, virtual filesystem.
[Source](https://en.wikipedia.org/wiki/UnionFS)

Docker's Architecture :

![Docker's Architecture Image](https://github.com/ynagarjuna1995/Deep-Dive-in-Operating-Systems-Linux/blob/master/Material/architecture.svg)