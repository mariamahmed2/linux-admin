Write the appropriate commands to do the following:
---------------------------------------------------
1-Write a cron job to run only once each system reboot.
Ans: 
```
@reboot sleep 60 && script.sh
```
2-Write two different cron jobs to excute "sestatus" at the start of day 1 of each month.
Ans:
```
1 24 1 * * script.sh
```
```
@monthly script.sh
```

3-Write a cron job to run only every saturday only 4 times during the day.
Ans:
```
0 */6 * * 6 script.sh
```
4-Schedule a job to only run one time after 3 days and 7 hours from now.
Ans:
```
at now + 79 hours
```
5-Forbid any normal user from scheduling jobs using "at" command.
Ans:
- run `which at` to know the file location
- then change the permission of the file to not be excuted by the users.

6-Edit the jobs created by a user called "Ebaa"
Ans:
```
crontab -u Ebaa -e
```

7-Add a cronjob that will run even if the system is shutdown :D
Ans:
By using `anacron`, then add the job to the configuration file `/etc/anacrontab`

8-get the last 3 commands written in a file called "Omnia" and get them added as cronjobs
Ans:
```
tail -3 Omnia >> /etc/crontab
```
9-Run a script called "Mo3az.sh" by 2 different ways making sure no error will be displayed even if exists.
Ans:
```
bash script.sh 2>/dev/null
```
```
./script.sh 2>/dev/null
```
10-schedule a cron job to run every 5 minutes in each odd number hour (ex: 1,3,5) to run a script 
called "/root/Rewan.sh" and no output or error should be sent by this job.
Ans:
 ```
 */5 1-23/2 * * * /root/Rewan.sh > /dev/null 2>&1
 ```
