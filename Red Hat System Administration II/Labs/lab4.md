1-Use the command "parted" to make a new primary partition on "/dev/sdc" and with xfs format and size 2GB.
Ans: 
```
parted /dev/sdb
(parted) mklabel msdos
parted /dev/sdb mkpart primary xfs 2048s 2GB
```

2-Run a command so that the system detects the previous changes (create the device under /dev).
Ans:
```
ll /dev | grep sdb
```
3-Apply ext4 file system on the previously created partition.
Ans:
```
mkfs.ext4 /dev/sdb1
```
4-Mount the previous file system permanently.
Ans: edit `fstab` file and add partition UUID, first get UUID from
```
lsblk --fs
```
then 
```
vim /etc/fstab
```
before reboot chaeck if there is any error
```
mount -a
```
5-scan the block devices connected to your machine and retrieve the file system UUIDs.
Ans:
```
lsblk --fs
```
6-Format a device called "/dev/sdc3" to become a swap space. 
Ans:
```parted /dev/sdb mkpart primary linux-swap 1GB 0.2GB

```

7-Activate the previous swap space and make sure it will mount permanently.
Ans:

8-Label the following two devices as PVs (Physical volumes): "/dev/sdd1" and "/dev/sdd2"
Ans:

9-Extend the following logical volume "/dev/vg01/lv01" by 7GB.
Ans:

10-Remove the following logical volume "/dev/vg01/lv01".
Ans:
 
