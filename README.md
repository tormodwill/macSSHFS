# macSSHFS

macSSHFS allows you to mount a remote filesystem using SFTP. 

Most SSH servers support and enable this SFTP access by default.
SSHFS is shipped by major operating systems and has been in production use across a wide range of systems for many years.

This is a macOS version of the Linux version 2.10.0 found here :
https://github.com/libfuse/sshfs

In coexistence with macSSHFS, we also have 
https://github.com/osxfuse/sshfs

The osxfuse/sshfs has not been updated since 2014, hence this separate version.

As of may 2022, this page will distribute an install package of
macSSHFS version 2.10.0.

The macSSHFS version 2.10.0 is a performance update of version 2.5.0
The performance improvements are significant.

The reason for offering this as a separate install package : It is not for the average macOS user to compile the sshfs Linux version.


To do list of this macSSHFS repository  :

* To include support for libfuse 3. If this can be achived, than it will be possible to compile the newest sshfs Linux versions to macOS. Need contributor to include support for libfuse 3.

* Make an option in the install package menu to run macSSHFS and mount at startup of macOS.  
I have the scripts needed to mount at startup, but need contibutor to incorporate this in the install package.

Tormod Willassen facilitates this repository as a service for people who would like a newer version of SSHFS for macOS.
The owner of this repository is totally dependent of contributors in order to be able to supply updates, new versions
and bugfixes. 




