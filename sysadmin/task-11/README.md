## Task 11

The sysadmin is tasked with creating a temporary user called `john` on the `stapp02` server, with an expiry date set to 2021-12-07.

This can be accomplished with the command `useradd` and the `-e` (for `--expiredate`) flag.

`sudo useradd -e 2021-12-07 john`

This can be confirmed by using the `chage` command.

<img width="482" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/f2a3c6da-c5c4-4a3b-8f47-4bc2caddf53d">
