# Lab2
-----
## Write the appropriate commands to do the following:
---------------------------------------------------
-1 create the following dorectories: [dir1-dir2-dir3] and copy them and their contents to /tmp.
Ans: 
```
mkdir dir1 dir2 dir3
```
```
cp -r dir{1,2,3} /tmp
```

-2 Move back the three directories with their contents from the last step to /opt.
Ans: 
```
mv /tmp/dir{1,2,3} /opt
```
-3 List all the files/directories the are starting with "b" followed by any two characters and ending with "k".
Ans: 
```
ls b??k
```
-4 Print the result of the following equation in one command: (16/4+5).
Ans:
```
echo $[16/4+5]
```
-5 Print the man page/pages the have the word "system".
Ans:
```
man -k "system"
```
-6 Redirect the output and the error of the command: "ls -al /" to a file.
Ans: 
```
ls -al/ &> errorfile
```
-7 Find all files under "/etc" the has the word "conf" in its name.
Ans:
```
find /etc -name "*.conf"
```
Or by `locate` but run `ubdatedb` first

```
locate "/etc/*.conf"

```
-8 Enable numbering lines in vim.
Ans:
```
:set number
```
-9 Display all running proccess in your system.
Ans:
```
ps aux
```
-10 Add a user called "ahmed" to another group called "Finance" without changing his primary group.
Ans:
```
useradd ahmed
```
```
passwd ahmed
```
```
groupadd finance
```
```
usermod -aG finance ahmed
```

## Documenation
- in Q1 I am tried `cp dir{1,2,3} /tmp` it shows an error `cp: omitting directory 'directory'`, cp copies only the direct files in, and not subdirectories in the directory. so recursive must be used.
mv /tmp/dir{1,2,3} /opt
