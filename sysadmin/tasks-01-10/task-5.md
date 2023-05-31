## Task 5

The sysadmin is tasked with identifying the root cause of the Postfix service's failure at the mail server.

Through the documentation, we know that the mail server is stmail01 and we SSH into it, using the `systemctl status postfix.service` command to see any error messages.

<img width="534" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/e3286205-f9f1-4531-94d6-3e7d3ba88576">

Since the issue is with the local IPv6 address, we can modify `/etc/hosts` file and comment out the `::1` line, which makes the service start properly:

<img width="611" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/ef84994f-e52f-4180-8376-349b2529681a">
