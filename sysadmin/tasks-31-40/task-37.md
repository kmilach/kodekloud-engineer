## Task 37

The sysadmin is tasked with configuring the SFTP server at `stapp01`. The requirements are:
- Create a SFTP user `kirsty` with a password `Rc5C9EyvbU`
- Password authentication should be enabled for this user
- Set its ChrootDirectory to `/var/www/web`
- SFTP user should only be allowed to make SFTP connections

Going into the application server, we create the user and folders as necessary:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/28de9e02-45a7-494b-9eee-7d13ee2f2476)

We then edit the `/etc/ssh/sshd_config` file:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/a88518d1-a12a-4284-842d-1b6e8c998493)


**References:**
- [Arch wiki - SFTP chroot](https://wiki.archlinux.org/title/SFTP_chroot)
- [sshd_config(5) - Linux man page](https://linux.die.net/man/5/sshd_config)
- [OpenSSH: Difference between internal-sftp and sftp-server](https://serverfault.com/questions/660160/openssh-difference-between-internal-sftp-and-sftp-server)
