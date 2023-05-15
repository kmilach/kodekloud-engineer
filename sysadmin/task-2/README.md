## Task 2

A new backup script, `xfusioncorp.sh`, has been developed by the sysadmin team and placed in multiple server. The task asks to make the script executable for _all users_ on the `App Server 2`.

For that, we just SSH into the server and use the command `sudo chmod a+rx /tmp/xfusioncorp.sh` to make it executable for all users.

<img width="320" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/a3ab8c46-4ce6-4405-b28c-c1db120202e6">

**Remember:** for the script to be executed, it must also be readable!
