


## Docker

Magic behind the docker's success can be realized when we have an basic idea about the [Union File System](http://unionfs.filesystems.org/)

**Union FS  :**
Unionfs is a filesystem service for Linux, FreeBSD and NetBSD which implements a union mount for other file systems. It allows files and directories of separate file systems, known as branches, to be transparently overlaid, forming a single coherent file system. Contents of directories which have the same path within the merged branches will be seen together in a single merged directory, within the new, virtual filesystem.
[Source](https://en.wikipedia.org/wiki/UnionFS)

###Docker's Architecture :

![Docker's Architecture Image](https://rawgit.com/ynagarjuna1995/Deep-Dive-in-Operating-Systems-Linux/master/Material/architecture.svg)

 - Docker's Daemon can be contacted using a client which may reside on your computer or on the automated Dev Op's Server using a command line tool or through REST API's
 - Docker acquired a spanish company [Tutum](https://www.tutum.co/) which concentrate on automating the Dev Op's workflow 

