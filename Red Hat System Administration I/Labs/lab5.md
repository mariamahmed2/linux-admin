-----
Write the appropriate commands to do the following:
---------------------------------------------------
1-Display the last 5 lines of the log file that logs cron jobs.
Ans:
```
tail -n 5 /var/log/cron 
```
2-Send a log message using "logger" and where can you find that message written?
Ans: logger <messages> 
```
  /var/log/boot.log
```
3-Display only error logs of the system.
Ans: 
```
  dmesg | grep -i error
```
4-Disply system logs since last week.
  ```
journalctl
```
5-Change your system's time zone to Africa/Kampala.
Ans:
  ```
  timedatectl list-timezones | grep -i cairo
```

6-Show the route to yahoo.com ?
Ans: 
  ```
  ping yahoo.com 
```
7-Disply the active network ports on your system and what is listening on them.
Ans:
  ```
  netsat -a
```
8-Display the info of a connection on your system called "Home Con"
Ans:
  ```
  ss --all
```
9-Reload the configuration of a connection and then restart it in one line.
Ans:

10-Using a command called "date" , display the date of your system 3 years ago.
Ans:
  ```
  date --date=2019-02-18
  ```
