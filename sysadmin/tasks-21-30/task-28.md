## Task 28

The sysadmin is tasked with configuring the logrotate for the `squid` package in all application servers. The requirements are:
- Install the squid package on all application servers
- Use logrotate to configure squid logs rotation to monthly and keep 3 rotated logs.

After installing the squid package, we check if it exists on the logrotate directories/files:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/25b3e3e8-4f64-4121-9bf1-8fb4183cb735)

We then change the configuration from this:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/8dd8f9de-22c2-42b6-b2ff-01107166c86a)

To this:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/dd039c75-ace5-4ec5-8cd2-e059d70a6b12)

Repeat for the other two servers.

**Reference:** [Log management with LogRotate in CentOS 7](https://fornex.com/en/help/logrotate-centos-7/)
