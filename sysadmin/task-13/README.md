## Task 13

The sysadmin is tasked with troubleshooting the MariaDB instance on the `stdb01` server.

To accomplish this, we SSH into the server and try to restart the service and see what it yields as a result, but the error message only mentions an empty `cgroup`.
Looking in the `/etc/my.cnf` file, we observe that the MariaDB user `/var/lib/mysql` as a data directory and for the socket file. Checking the directory, we notice that it's completely empty, 

<img width="427" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/8a441604-1722-44e8-a362-d125a74e1920">


In this case, we use the command `mysql_install_db --user=mysql --basedir=/usr/ --datadir=/var/lib/mysql/` to properly start the database.

<img width="536" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/9b8b6982-c5a7-4a8a-b360-0498fc7aee8f">

- After the command:

<img width="356" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/b4a7f69d-9fdf-4bd2-a504-377a3fc7527d">
