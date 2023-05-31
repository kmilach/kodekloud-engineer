## Task 30

The sysadmin is tasked with creating a bash script called `news_backup.sh` in the `stapp03` server for creating backups for the static website. The script should do the following tasks:
- Create a zip archive `xfusioncorp_news.zip` of the `/var/www/html/news` directory
- Save the archive in `/backup/`
- Save the archive in `/backup/` in the `stbkp01` server
- The script shouldn't ask for a password while copying the archive file. Additionally, user `steve` for the application server #2 must be able to run it

First, we create the script on the detailed place with a touch command and write the following commands in it:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/8495f54f-9160-4972-ad6e-6f5e02a04705)

After that, we generate a SSH key-pair and copy it to the backup server with ssh-copy-id.

Testing the script, we see that the file was generated and copied over:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/32fd0ae3-e7de-4f1d-8660-bdf5a1250458)
