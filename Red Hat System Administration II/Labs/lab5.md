Write the appropriate commands to do the following:
---------------------------------------------------
1-You have NFS, export "/var/data" to all IPs in "192.168.5.0" network with read and write permissions.
Ans: 
```
vim /etc/exports
```
then add `/var/data 192.168.5.0 rw`
```
systemd restart nfs-server
exportfs -f
```
2-Write the condition used to allow "root" to modify files on the remote NFS server.
Ans:
```
/var/data 192.168.5.0 (rw, no_root_squash) 
```
3-Force reading the NFS configuration file.
Ans:
```
exportfs -f
```
4-Write a sample line in fstap, to mount a NFS ensuring your system will boot event if the remote NFS
  server is not online.
Ans:
```
192.168.5.0:/var/data    /var/data    nfs    netdev    0 0
```
5-Restart your system by 3 different commands.
Ans:
```
reboot
```
```
systemctl start reboot.target
```
```
init 6
```

6-List all available targets on your system.
Ans:
```
systemctl list-units --type=target --all
```

7-Remount /sysroot as read/write.
Ans:
during booting, press `e`, scrolldown until linux16 line, ro --> 
```
rw init=/sysroot/bin/sh
```

8-write a sample line in NFS exports to ensure syncing is enabled.
Ans:
```
/var/data 192.168.5.0 (rw, no_root_squash, sync)
```
9-Show all avilable remote mounts.
Ans:
```
showmount -e <ip_mymachine>
```
10-Shutdown your machine.
Ans:
```
shutdown -c
```
