## Task 17

The sysadmin is tasked with updating the message of the day on all application and database servers. The template to be used is located in `/home/thor/nautilus_banner` on the jumphost.

In order to accomplish that, we copy the contents of the jumphost file into the /etc/motd file on all application servers (`stapp01`, `stapp02` and `stapp03`) and the `stdb01` database server.

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/362dff67-c0f5-4553-8928-a2d75531a505)

With this, you can substitute the empty `/etc/motd` file on each server with the `/tmp/nautilus_banner` file content.

For the `stdb01` server, we notice that the `scp` command fails. Logging into it, we can install the `openssh-clients` package, which contains the `scp` command:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/be6fb8ca-b453-4d0d-81d2-4ca17d727e96)
