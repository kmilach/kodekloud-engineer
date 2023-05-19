## Task 21

The sysadmin is tasked with creating a collaborative directory `/devops/data` on the `stapp03` server. The directory should be group owned by the `devops` group and the group should own the files inside the directory. The directory's permisions should be `read/write/execute` to the group owners, and `others` should not have any access.

For this, we use both `chown` and `chmod` commands, to change group ownership and directory permissions, respectively.

First, create the directory with the `mkdir -p /devops/data` command and then, change its ownershipg to the `devops` group with `chown -R :devops /devops/data` command.

Finally, change the permissions with `chmod -R 770 /devops/data`:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/e992ee14-157a-4ab8-8483-ab77e7a7fadd)
