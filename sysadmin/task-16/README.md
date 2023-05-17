## Task 16

The sysadmin is tasked with creating a passwordless SSH access to each application server from the jumpclient for the `thor` user.

__Note:__ the access must be done for the sudo user of each application server (eg `steve` for `stapp02`)!

This can be accomplished by first generating a SSH key pair with `ssh-keygen` and then copying the public key to each server with `ssh-copy-id`.

- Generating the key pair:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/df890b84-29fe-4bac-b8d1-02fc0580287d)

- Copying it to the `stapp01` server and testing it out:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/cad396eb-8101-4c1c-a9e7-767aa0866f4f)

- Repeat the same process for the other servers:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/295c4a33-c9de-4d2e-839d-516a2753eaea)
