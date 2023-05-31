## Task 4

The sysadmin is tasked with adding Google's public DNS server (IPv4) to the `App Server 3` as a temporary fix.
This is easily accomplished by editing the `/etc/resolv.conf` file with the `vi` or `nano` editors and adding the line `nameserver 8.8.8.8`.

**Note:** you can check the IP addresses for Google's public DNS servers [here](https://developers.google.com/speed/public-dns).
