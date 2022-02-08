## Chapter 5
# MANAGING LOCAL LINUX USERS AND GROUPS

## Users and groups
### What is a user?
The user associated with a running process determins the file and directories accessible to that process.
- `id` to show info about the current user
- `name` info about a specific user
```
$ id <name>
```
- `ls -l` To view the user associated with a file or dir
- `ps au` for process status in the current shell + `a` for all process + `u` for user

The operating system tracks the user by ID in `/etc/passwd`
It contains of 7 fields:
1- username
2- password: encrypted and stored in /etc/shadow
3- UID: user id
4- GID: user's primary group id
5- GECOS: user's real name
6- /home/dir
7- shell

### What is a group?
- defined in /etc/group
- every user has a primary group
- the user may be a member of 0,1,2.. supplementry groups

## Gaining Superuser Access
