## Task 36

The sysadmin is tasked with installing and configuring the `iptables` firewall in all application servers, blocking all incoming connections at port **3003** except for the LBR host. Make sure these are permanent configurations, even after reboots.

For this, we use the following commands after isntalling `iptables` and `iptables-services` packages:

```
yum install -y iptables iptables-services
systemctl start iptables && systemctl enable iptables
iptables -F
iptables -A INPUT -p tcp -s 172.16.238.14 --dport 3003 -j ACCEPT
iptables -A INPUT -p tcp --dport 3003 -j DROP
iptables-save > /etc/sysconfig/iptables
systemctl restart iptables
```

We can then test if the rules are working, both from the jumpclient and the LBR server:

<img width="566" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/b7517d41-28a4-434c-ab9b-ff3109419b39">
