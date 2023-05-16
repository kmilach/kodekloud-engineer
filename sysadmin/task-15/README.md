## Task 15

The sysadmin is tasked with altering the `/home/BSD.txt` file on the `stapp03` server. The modifications are as follows:
- remove all lines containing "code" and save that to `/home/BSD_DELETE.txt`
- replace all "or" *words* (**not** patterns) with "their" and save the result to `/home_BSD_REPLACE.txt` (remember to not replace "or" inside another word, like in "tutor")

Using the `sed` command we can make both substitutions like this:

<img width="462" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/b209e9e5-0831-4dcb-bdf3-b70d35bbb6f9">

**References:**
- https://stackoverflow.com/questions/1032023/sed-whole-word-search-and-replace
