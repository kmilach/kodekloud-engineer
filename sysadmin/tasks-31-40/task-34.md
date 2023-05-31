## Task 34

The sysadmin is tasked with configuring the mail server (`stmail01`), installing both postfix and dovecot packages to this end. An email, rose@stratos.xfusioncorp.com, should be create with a mail directory located in `/home/rose/Maildir` and also identified by the `Rc5C9EyvbU` password.

**Note:** `postfix` should be used for the mail transfer agent and `dovecot` for the IMAP/POP service. The full hostname for the server is `stmail01.stratos.xfusioncorp.com`.

For the postfix configuration, we edit the /etc/postfix/main.cf file:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/5d37134d-a8f9-44b1-bf49-f89144046bdc)

Per Postfix's recommendations, we change the following parameters as well:
- `myorigin = $mydomain` (since it's a large domain)
- `inet_interfaces = all` (listen on all interfaces)
- `mydestination = $myhostname, localhost.$mydomain, localhost, $mydomain` (we add the $mydomain since the mail server should be used for the entire stratos domain)
- `mynetworks = 172.16.238.0/24, 127.0.0.0/8` (the subnet of the domain is explicitly included)
- `home_mailbox = Maildir/` (pre-requisite)

Adding the rose user:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/684b0150-0ac3-4053-a4c8-2f91acdcb6ca)

Finally, we edit the /etc/dovecot/dovecot.conf and the /etc/dovecot/conf.d/* files:
- `protocols = imap pop3` in `/etc/dovecot/dovecot.conf`
- `mail_location = maildir:~/Maildir` in `/etc/dovecot/conf.d/10-mail.conf`
- `user = postfix` and `group = postfix` for `unix_listener auth-userdb` parameter for `service auth` in `/etc/dovecot/conf.d/10-master.conf`
- `auth_mechanisms = plain login` in `/etc/dovecot/conf.d/10-auth.conf`

After starting both services, we test sending an email:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/6e906416-16e9-415c-845c-68642544aa43)

Testing in port 110 for checking the email fails with dovecot, so we go back to the and explicit the `disable_plaintext_auth = yes` option to try again:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/e7aeeda0-1f0e-432d-ba69-2e7fbda8d3da)



**References:**
- [Dovecot - Quick Configuration](https://doc.dovecot.org/configuration_manual/quick_configuration/#id2)
- [How To Set Up a Postfix E-Mail Server with Dovecot](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-postfix-e-mail-server-with-dovecot)
