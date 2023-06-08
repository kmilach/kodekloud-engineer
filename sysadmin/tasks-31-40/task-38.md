## Task 38

The sysadmin is tasked with troubleshooting why the Apache service is down on one of the application servers. The faulty server must be identified and the service should be up on port 3003.

We first try the `systemctl status httpd` on all application servers and find out that the `stapp01` is the faulty one:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/438ba09f-1353-4b9c-bb61-fea512dfafa8)

Logging into the server, we notice the error with the command `journalctl -xe -u httpd` after trying to start the service:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/d306cb84-cffa-4a65-929d-d9095566441f)

Looking into the highlighted message, we then use `netstat` to see what process is using the socket:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/7db7ad91-7942-4b88-93c3-70903bc23381)

After killing the `sendmail` process, we start the `httpd` service again:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/31c689dd-2ce7-49c2-96f6-1c9a049d3692)
