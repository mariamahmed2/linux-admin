## Chapter 5
# MANAGING LOCAL LINUX USERS AND GROUPS

## Users and groups
### What is a user?
The user associated with a running process determins the file and directories accessible to that process.
- `id` to show info about the current user and group
- `name` info about a specific user
```
$ id <name>
```
- `ls -l` To view the user associated with a file or dir
- `ps au` for process status in the current shell + `a` for all process + `u` for user

The operating system tracks the user by ID in `/etc/passwd`
It contains of 7 fields:
- 1 username
- 2 password: encrypted and stored in /etc/shadow
- 3 UID: user id
- 4 GID: user's primary group id
- 5 GECOS: user's real name
- 6 /home/dir
- 7 shell

### What is a group?
- defined in /etc/group
- every user has a primary group
- the user may be a member of 0,1,2.. supplementry groups

## Gaining Superuser Access
- `su <-> <username>` to change user
-  `sudo` allow users to run command as root based on /etc/sudoers file, all users under wheel group can use sudo
    - all commands excuted by `sudo` are logged to /var/log/secure 
 
 ## Mnaging Local User Accounts
 -`useradd <username>` to add a new user, can not login until set a password, rules from /etc/login.defs file
 - `usermod` modifies exiting users
 - `userdel -r <name>` removes the user from /etc/passwd and `-r` to remove the home dir its important for avoid info leakage and         security issues.
     - issue: if I delete a user that has a home dir and add another user, the new one takes the same id and owns the old home dir.
     - sol: - remove all unknoun files after deleting user
          - assin them to root by `find / -nouser -o -nogroup 2> /dev/null`     
          - `passwd <username>` set or change password

## UID ranges
- 0 to root
- 1-200 "system users" processes
- 201-999 "system users" processes that do not have file system
- 1000+ regular users
 
 ## Managing local Group Accounts
 - `groupadd <groupname> -g <GID>` to add group, `-g` to set id, and `-r` automatic from  the system
 - `groupmod -n <new> <old name>` to change group name 
 -  `groupdel` to delete a group, and it will not be removed if it is a primary group
 -  `usermod -g <groupname> <username>` change primary group
 -  `usermod -aG <groupname> <username>` add user to supgroup, `a` for append and without it the user would be removed from all other    supgroups
 
## Managing User Passwords
passwords are encrypted in hashes in /etc/shadow
```
$1$gCjLa2/Z$6Pu0EK0AzfCjxjv2hoLOB/
```
- 1 `$1$` the hashing algorithm, 1 for MD5, and 6 for SHA-512
- 2  `gCjLa2/Z` salt used to encrypt the hash, handel 2 users with same password
- 3 `6Pu0EK0AzfCjxjv2hoLOB/` the encrypted hash 

- `chage -d 0 <username>` force a pass update on the next login
- `chage -l <username>` list settings
- `chage -E yyyt-mm-dd` expire an account on that date -- lock account with `usermod -L`
- `data -d "+45 days"` calculate date in the future
---- nologin shell
