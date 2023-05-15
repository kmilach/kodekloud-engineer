## Task 6

The sysadmin is tasked with disabling the SSH login for the `root` user on all app servers.

This can be accomplished by editing the `/etc/ssh/sshd_conf` file on each server and changing the `PermitRootLogin` parameter to `no`. Restart the `sshd` service afterwards.
