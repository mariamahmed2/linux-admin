Lab3
-----
Write the appropriate commands to do the following:
---------------------------------------------------
1-using the sympolic method give a file called "newfile" the following permissions: 755
Ans:
```
chmod u=rwx,g=rx,o=rx newfile
```
2-using the numeric method give a directory and all its contents the following permissions: u=rw, g=rw, o=r
Ans:
```
chmod -R 664 /root/trydir
```
3-change the ownership of a file called "myfile" to be owned by a user called "hazal2om" and a group called "CEO".
Ans:
```
chown :CEO hazal2om
```
5-what command is used to kill a proccess immediately (mention two commands)?
Ans:
```
kill -9 pid
```
```
kill -SIGKILL pid
```
6-what are the default permissions set for a new created file or a directory in linux.
Ans:644

7-allow all users on the system to access and create files on /var using the sticky bit.
Ans: 
```
chmod 777 /var
```
8-Display the uptime of your system (mention two ways).
Ans:
```
uptime   #top (at first line)
```
9-What is a zombie proccess and mention a command to display them.
Anss:zombie processes are subprocesses (child) created by the parent processes 
```
ps -elf | grep Z
```
10-Display all users logged in to your system and from where they are logged in.
Ans:
```
who
```
