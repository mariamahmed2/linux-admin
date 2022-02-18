Write the appropriate commands to do the following:
---------------------------------------------------
1-install "system-config-kickstart" and "vsftpd" by one command.
Ans: 
```
yum install system-config-kickstart vsftpd
```
2-Mount your cdrom to /media
Ans:
```
 mount /dev/cdrom /media
 ```

3-Disalbe the selinux on your system.
Ans:
- Open the `/etc/selinux/config` file and set the `SELINUX` mod to `disabled`, then save the file and reboot the system.

4-Stop and disable the firewall service on your system. 
(use two commands on one line , the first command has to succeed in order to run the second)
Ans:
```
systemctl stop firewalld && disable firewalld
```

5-Validate your Kick start file located in /opt/MyKsFile.cfg
Ans:
```
ksvalidator /opt/MyKsFile.cfg
```
6-Use regular expressions with "grep" command to match with the word "cat" on the file "/usr/share/dict/words"
  the output should only be "CAT"
Ans:
```
grep -i "cat" /usr/share/dict/words
```
7-Use regular expressions with "grep" command to match with the word "cat" on the file "/usr/share/dict/words"
  the output should contain every thing but not the word "CAT"
Ans:
```
grep -v "cat" /usr/share/dict/words

```

8-Use "cut" command to show only the last coloumn of the file /etc/passwd
Ans:
```
cut -d: -f7 /etc/passwd

```

9-Use three different commands to only show the first 3 lines of the file /etc/passwd
Ans:
```
head -n3 /etc/passwd
```
```
more -3 /etc/passwd
```
```
awk 'NR%3==0{print;getline <"-"}NR{print}' /etc/passwd
```
10-Only show the lines number 4,5 and 6 from the file /etc/passwd using the commands "head" and "tail" only
Ans:
```
head -6 lines.txt | tail +4
```
