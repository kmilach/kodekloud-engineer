## Task 22

The sysadmin is tasked with encrypting some data on the storage server `ststor01`. There are private and public keys located on `/home/*_key.asc`. Using these keys, the sysadmin must:
- Encrypt the file `/home/encrypt_me.txt` to `/home/encryt_me.asc`
- Decrypt the file `/home/decrypt_me.asc` to `/home/decryt_me.txt`

**Note:** the password used for the encryption is "kodekloud".

First, we can import the keys for further use like this:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/2584ae71-ffa4-487e-940c-0309f5832e36)

We can see those were successfully imported by using the following commands:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/5bafddcf-343a-4204-b267-9f4393deef25)

Since the `.asc` extension was mentioned, it mean that the files will be ASCII armored. The commands to encrypt and decrypt the files, as instructed, are thus:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/15850b5a-4b3d-42d7-9e30-dc94df7ee253)
