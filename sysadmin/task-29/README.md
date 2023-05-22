## Task 29

The sysadmin is tasked with changing some `iptables` rules on the backup server `stbkp01`, with the following requirements:
- Open all incoming connections to Nginx on port 8097
- Block all incoming connections to Apache on port 3001
- Both rules must be permanent

For that, we SSH into the server and start the `iptables` service, listing its rules:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/137a899d-0c23-49c3-a096-6b70632b5a3c)

We then add two new rules on the `INPUT` chain, as requested:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/93cc7372-48e5-450f-b023-cca9a3322b52)

One of the rules (number 5, the last one before the two new rules) rejects everything which is then removed with `iptables -D INPUT 5`.

The rules are then saved with `iptables-save > /etc/sysconfig/iptables`.

**References:**
- [Using iptables to block specific ports](https://www.ibm.com/support/pages/using-iptables-block-specific-ports)
- [How to save iptables firewall rules permanently on Linux](https://www.cyberciti.biz/faq/how-to-save-iptables-firewall-rules-permanently-on-linux/)
