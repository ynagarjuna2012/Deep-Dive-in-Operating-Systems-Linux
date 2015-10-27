


## Docker

Magic behind the docker's success can be realized when we have an basic idea about the [Union File System](http://unionfs.filesystems.org/)

**Union FS  :**
Unionfs is a filesystem service for Linux, FreeBSD and NetBSD which implements a union mount for other file systems. It allows files and directories of separate file systems, known as branches, to be transparently overlaid, forming a single coherent file system. Contents of directories which have the same path within the merged branches will be seen together in a single merged directory, within the new, virtual filesystem.
[Source](https://en.wikipedia.org/wiki/UnionFS)

**Must Read : Interesting article on How UnionFS works can be found on [Linux Journal](http://www.linuxjournal.com/article/7714).**

 This article is exhaustive and concise which will change your perspective on how you look at the things while using docker.


###Docker's Architecture :

![Docker's Architecture Image](https://rawgit.com/ynagarjuna1995/Deep-Dive-in-Operating-Systems-Linux/master/Material/architecture.svg)

 - Docker's Daemon can be contacted using a client which may reside on your computer or on the automated Dev Op's Server using a command line tool or through REST API's
 - Docker acquired a spanish company [Tutum](https://www.tutum.co/) which concentrate on automating the Dev Op's workflow.


###Docker and IDE's :
Find the Docker plugin to use with your favorite IDE [here](http://domeide.github.io/) to manage your applications.

 - [Guide to work with Docker's Intellij IDEA Plugin](https://blog.jetbrains.com/idea/2015/03/docker-support-in-intellij-idea-14-1/)

As we know docker images are read-only we will get only versions of an image so we don't have folder syncing support with the containers like vagrant *(Disclaimer : As per my knowledge)*.We have to directly work with applications inside the docker containers these plugins will come handy while developing the applications.

Some useful tutorials :

 - [Distribute your applications with Docker Images](http://www.javacodegeeks.com/2015/05/distribute-your-applications-with-docker-images.html)
 - [Fast and easy integration testing with docker and overcast](http://blog.xebia.com/2014/10/13/fast-and-easy-integration-testing-with-docker-and-overcast/) : Overcast is a open source java library
developed by XebiaLabs to help you to write test that connect to cloud hosts. Overcast has support for various cloud platforms, including EC2, VirtualBox, Vagrant, Libvirt (KVM) and also supports docker.
 - [Developing Java apps with Docker](http://blogs.atlassian.com/2013/06/deploy-java-apps-with-docker-awesome/)

 


