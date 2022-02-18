Write the appropriate commands to do the following:
---------------------------------------------------
1-List all the proccess on the system with their nice values.
Ans: 
```
ps axo ni
```
2-List all the proccess on the system and sort them in a descending order by their nice value.
Ans:
```
ps axo nice --sort=-nice
```
3-change the nice value of a process id 13562 to -15
Ans:
```
renice -n -15 13562
```

4-run a script called "Youssef.sh" with an initial nice value of -12
Ans:
```
nice -n -12 ./Youssef.sh
```
5-renice all currently running proccesses of a user called "Ahmed" to 6
Ans:
```
renice 6 -u Ahmed
```
6-Modify the ACL on a file called "/tmp/abdelrahman.txt" to add write permission to all users 
Ans:
```
setfacl -m u::w /tmp/abdelrahman.txt
```
7-Using ACL, revoke the write permission of the previous command
Ans:
```
setfacl -m m::w /tmp/abdelrahman.txt
```

8-Disable Selinux entirely.
Ans:
```
vim /etc/selinux/config
SELINUX=disabled
reboot
```
9-change the selinux context on "/home/sara/accounts.txt" to be "new_con" 
Ans:
```
chcon -t new_con /home/sara/accounts.txt
```
10-Using the command "echo" , disable selinux temporarily.
Ans:
 ```
 echo 0 > /selinux/enforce
 ```
