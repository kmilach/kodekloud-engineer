## Task 9

The sysadmin is tasked with installing the required packages for SElinux on `stapp01` server and also permanently disabling it for now.
Do not reboot the server or anything, while also ignoring the SElinux command line status.

First we use `yum update` and the `yum install selinux*` to install all SElinux packages.

With this, we can edit the `/etc/selinux/config` file and set `SELINUX=disabled` to permanently disable it, even after the reboot.

Editing the file:

<img width="368" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/7e50da7a-b26b-4568-a863-362ac89fde41">

Checking SElinux state with `sestatus`:

<img width="259" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/2d71f61a-79ef-4af4-9807-523f7433bfef">

References:
- [Getting Started with SELinux on CentOS 8](https://www.linode.com/docs/guides/a-beginners-guide-to-selinux-on-centos-8/)
- [A Beginner’s Guide to SELinux on CentOS 8](https://roman-academy.medium.com/a-beginners-guide-to-selinux-on-centos-8-c42ff57efd99)
