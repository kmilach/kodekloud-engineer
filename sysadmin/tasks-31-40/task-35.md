## Task 35

The sysadmin is tasked with installing and configuring a Postgre SQL server on Nautilus DB server `stdb01`. A database user should be created, named `kodekloud_rin` and with the password `ksH85UJjhb`. This user should have full permission on a newly-created database named `kodekloud_db3`. All local socket connections should be allowed for this database and the aforementioned user, with the connections being made through the md5 method (do **not** try to encrypt the password).

After installing the `postgresql-server`, we initialize the database and the service itself:

<img width="411" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/c38b7629-37ac-4abf-9cac-aeebf767ede9">

Trying to use the `psql` command to interact with Postgre fails so we use `sudo` to access it:

<img width="359" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/9ded455f-2409-4e75-aa09-2669d28b3f2e">

For the creation of the database, the user `kodekloud_rin` and to give full permission to database, we use the following commands:

```
CREATE USER kodekloud_rin WITH PASSWORD 'ksH85UJjhb';
CREATE DATABASE kodekloud_db3;
GRANT ALL PRIVILEGES ON DATABASE kodekloud_db3 to kodekloud_rin;
\q
```

We then edit the `/var/lib/pgsql/data/postgresql.conf` and `/var/lib/pgsql/data/pg_hba.conf`, for connections and authentication method, respectively:

<img width="291" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/aca644bd-3299-4b9a-b071-fc88edb4f987">

<img width="617" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/93617e8c-02b3-4bde-ab45-7475ced850f7">

Finally, we test the local connection:

<img width="627" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/2375b640-9f30-43f9-95f7-330d0e0c8955">

**References:**
- [PostgreSQL CREATE DABASE command](https://www.postgresql.org/docs/current/sql-createdatabase.html)
- [PostgreSQL CREATE USER command](https://www.postgresql.org/docs/15/sql-createuser.html)
- [PostgreSQL GRANT command](https://www.postgresql.org/docs/15/sql-grant.html)
- [PostgreSQL file locations](https://www.postgresql.org/docs/current/runtime-config-file-locations.html)
- [PostgreSQL server configuration](https://www.postgresql.org/docs/9.3/runtime-config.html)
