## Task 1

The sysadmin is tasked to create an user named `mark` with a non-interactive shell on `App Server 3`.

By SSHing into the server as user `banner`, we first take a look if we have any administrative rights with `sudo -l`:

<img width="341" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/4eaeb0a3-3409-44b9-a5d1-95fe31c4a4c4">

Since we have `sudo` access to all commands, we can simply use a `sudo useradd -s /sbin/nologin mark` command to successfully complete the task.
