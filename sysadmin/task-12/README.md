## Task 12

The sysadmin is tasked with changing the default runlevel in all application servers, so that those can be booted in GUI by default.

First we use systemctl get-default to see what is the runlevel currently used in the servers:

<img width="273" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/c5c4801f-d0cf-445e-9498-785362daa7b3">

In this case, we use the command systemctl set-default graphical.target in each server.

<img width="563" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/5941a4db-c025-4fa2-82f3-2aee1eb46fa2">

A good explanation on the topic (and commands to be used) can be found in [this link](https://www.cyberciti.biz/faq/switch-boot-target-to-text-gui-in-systemd-linux/).
