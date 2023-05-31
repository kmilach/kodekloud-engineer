## Task 24

The sysadmin is tasked with CONFIGURING a local Yum repository in the `stbkp01` server. The files to be used are located in `/packages/downloaded_rpms/`, which should be configured into the repo.
The repo name should be `local_yum` and it should be used to install the `samba` package, as requested.

This can be accomplished with editing a file `/etc/yum.repos.d/local_yum.repo` as shown below:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/c9d7d739-c83e-466f-b956-67480ae8b781)

Installing the `samba` package:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/111bcc2b-51b2-43fa-9558-eb39178b0ad0)

**Reference:** [How To Create Local YUM repository on CentOS 7 / RHEL 7 using DVD](https://www.itzgeek.com/how-tos/linux/centos-how-tos/create-local-yum-repository-on-centos-7-rhel-7-using-dvd.html)
