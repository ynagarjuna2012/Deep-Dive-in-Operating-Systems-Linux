


##Linux - A Revolution by Humans towards a open and secure World.

###  **Importance of sudo & su and managing the user control in Linux  :**
Privilege separation is one of the fundamental security paradigms implemented in Linux and Unix-like operating systems.Regular users operate with limited privileges in order to reduce the scope of their influence to their own environment, and not the wider operating system.

A special user, called `root`, has "super-user" privileges. This is an administrative account without the restrictions that are present on normal users. Users can execute commands with "super-user" or "root" privileges in a number of different ways.

    When running on Ubuntu, sudo is already always  set up for you during installation. If you are running something in the Fedora or openSUSE families of distributions, you will likely need to set up sudo to work properly for you after initial installation. If users want root account password then they can manually set it up or can use 'sudo'. As we all know, Linux in many ways protects users' computer being used for bad purposes by some nasty people around us. Using sudo is one of those good ways. Whenever a user tries to install, remove and change any piece of software, the user has to have the root privileges to perform such tasks. `sudo`, linux command is used to give such permissions to any particular command that a user wants to execute. 

If your system does not already have sudo set up and enabled, you need to do the following steps:

 1. You will need to make modifications as the administrative or super user, root. While sudo will become the preferred method of doing this, we don’t have it set up yet, so we will use su.
    `> sudo su `
    or just 
   ` > su`
   Type the password when prompted
 2. Now you need to create a configuration file to enable your user account to use sudo. Typically, this file is created in the /etc/sudoers.d/ directory with the name of the file the same as your username. For example, for this demo, let’s say your username is “student”. After doing step 1, you would then create the configuration file for “student” by doing this
  ` # echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student`
 3. Finally, some Linux distributions will complain if you don’t also change permissions on the file by doing:
   ` # chmod 440 /etc/sudoers.d/student`


		Note : 
		1. As of Debian version 1.7.2p1-1, the default /etc/sudoers file created on installation of the package now includes the directive:
		
		      #includedir /etc/sudoers.d
		
		This will cause sudo to read and parse any files in the /etc/sudoers.d
		directory that do not end in '~' or contain a '.' character.
		
		Note that there must be at least one file in the sudoers.d directory (this
		one will do), and all files in this directory should be mode 0440.
		
		Note also, that because sudoers contents can vary widely, no attempt is
		made to add this directive to existing sudoers files on upgrade.  Feel free
		to add the above directive to the end of your /etc/sudoers file to enable
		this functionality for existing installations if you wish!
		
		Finally, please note that using the visudo command is the recommended way
		to update sudoers content, since it protects against many failure modes.
		See the man page for visudo for more information.
		
		2. CentOS doesn't have sudoers.d directory you need to make that directory and need to follow above steps if you are using any provisioning tools like puppet you can find puppet-sudo [here](https://github.com/arnoudj/puppet-sudo) including suoders.d can be done by following [issue#8 : missing check for /etc/sudoers.d and include](https://github.com/arnoudj/puppet-sudo/issues/8) in puppet-sudo

**[Su](http://man7.org/linux/man-pages/man1/su.1.html) :**  su allows to run commands with a substitute user and group ID.
*(Additional documentation can be found [here](http://man7.org/linux/man-pages/man1/su.1.html) or here on [techonnet](http://www.techonthenet.com/linux/commands/su.php))*

       When called without arguments, su defaults to running an interactive
       shell as root.

       For backward compatibility, su defaults to not change the current
       directory and to only set the environment variables HOME and SHELL
       (plus USER and LOGNAME if the target user is not root).  It is
       recommended to always use the --login option (instead of its shortcut
       -) to avoid side effects caused by mixing environments.

       This version of su uses PAM for authentication, account and session
       management.  Some configuration options found in other su
       implementations, such as support for a wheel group, have to be
       configured via PAM.

#####**[Sudo in a nutshell :](http://www.sudo.ws/intro.html)**

Sudo (su "do") allows a system administrator to give certain users (or groups of users) the ability to run some (or all) commands as root while logging all commands and arguments. Sudo operates on a per-command basis, it is not a replacement for the shell. Its features include:

- The ability to restrict what commands a user may run on a per-host basis.
- Sudo does copious logging of each command, providing a clear audit trail of who did what. When used in tandem with syslogd, the system log daemon, sudo can log all commands to a central host (as well as on the local host). At CU, all admins use sudo in lieu of a root shell to take advantage of this logging.
- Sudo uses timestamp files to implement a "ticketing" system. When a user invokes sudo and enters their password, they are granted a ticket for 5 minutes (this timeout is configurable at compile-time). Each subsequent sudo command updates the ticket for another 5 minutes. This avoids the problem of leaving a root shell where others can physically get to your keyboard. There is also an easy way for a user to remove their ticket file, useful for placing in a .logout file.
- Sudo's configuration file, the sudoers file, is setup in such a way that the same sudoers file may be used on many machines. This allows for central administration while keeping the flexibility to define a user's privileges on a per-host basis. Please see the samples sudoers file below for a real-world example.


**[Sudoers  is a default sudo security policy plugin](http://www.sudo.ws/man/sudoers.man.html) : ** This policy plugin determines a user's sudo privileges. It is the default sudo policy plugin. The policy is driven by the /etc/sudoers.d/username file or, optionally in LDAP. The policy format is described in detail in the SUDOERS FILE FORMAT section. For information on storing sudoers policy information in LDAP

Guides/Tutorials:

- [Sudoers on Ubuntu](https://help.ubuntu.com/community/Sudoers)
- ~~[How To Edit the Sudoers File on Ubuntu and CentOS](https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file-on-ubuntu-and-centos)~~ Deprecated Implementation as mentioned here.Included for reference of old users and for novice it has concise explanation of how `sudoers` file works
 