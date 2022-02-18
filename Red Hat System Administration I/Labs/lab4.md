-----
Write the appropriate commands to do the following:
---------------------------------------------------
1-List all services on the system whatever is their state.
Ans: 
```
systemctl  --all
```

2-You want to know if sshd service is running or not , redirect your output to /tmp/out.txt
Ans: 
```
systemctl status sshd > /tmp/out.txt
```
3-write the two commands required to stop and disable firewalld service.
Ans: 
```
systemctl stop firewalld
``` 
```
vim /etc/selinux/config
   SELINUX=disabled
```


4-Disable a service from being run as a dependency to another service.
Ans:

5-Prevent crond service from being used by any user or even root.
Ans:
```
systemctl mask cron
```
6-How to connect to a remote host using SSH protocol ?
Ans: 
```
ssh remoteuser@remotehost
```

7-Display the status of sshd service on a remote server, redirect your output to a file called "status.log"
Ans:
```
systemctl status sshd >/etc/status.log
```

8-What command is used to generate public/private key files ? and where are they stored by default?
Ans: 
```
ssh-keygen
```
9-Send a copy of your public key to a remote server by two different ways.
Ans:
```
ssh-copy-id -i ~/.ssh/mykey user@host
```
10-terminate your remote logging session.
Ans:
```
exit
```
