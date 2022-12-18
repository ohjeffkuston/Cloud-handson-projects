<p align="center">
 <img src="../../img/GLN_Logo.png?raw=true" alt="GIFTED LANE Logo" width="50%" height="50%" />
</p>

# Create a Cron Job
- [x] Install `cronie` on all 3 app servers
- [x] Ensure the `crond` service is started on all 3 app servers
- [x] Add a cron for the `root` user on all 3 app servers

## The Dig 

-  ♾️ Dig 1 > [How to Install Crontab](https://tecadmin.net/install-crontab-in-linux/)
-  ♾️ Dig 2 > [How to verify crond daemon and cron jobs are running on Linux](https://www.cyberciti.biz/faq/howto-check-cronjob-is-running-not/)
-  ♾️ Dig 3 > [Linux Start Restart and Stop The Cron or Crond Service](https://www.cyberciti.biz/faq/howto-linux-unix-start-restart-cron/)
-  ♾️ Dig 4 > [How To Add Jobs To cron Under Linux or UNIX](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)

## What I Ultimately Did

```bash
#log into the applicable server
ssh username@ip_address
```

```bash
#check if the crond service is running/installed
systemctl status crond.service



# **_OUTPUT_**
Unit crond.service could not be found.
```

```bash
#install cronie (Crontab)
sudo yum install cronie



# **_OUTPUT_**
#output shorten for brevity
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.web-ster.com
 * updates: mirror.stanford.edu
Setting up Install Process
Resolving Dependencies
--> Running transaction check
---> Package cronie.x86_64 0:1.4.4-12.el6 will be installed
```

```bash
#check if the crond service is now installed and running
systemctl status crond.service

#make note of 'Active: INACTIVE (dead)' in the output below


# **_OUTPUT_**
● crond.service - Command Scheduler
   Loaded: loaded (/usr/lib/systemd/system/crond.service; enabled; vendor preset: enabled)
   Active: inactive (dead)
```

```bash
#start the crond service
sudo systemctl start crond.service
systemctl status crond.service

#make note of 'Active: ACTIVE (running)' in the output below


# **_OUTPUT_**
● crond.service - Command Scheduler
   Loaded: loaded (/usr/lib/systemd/system/crond.service; enabled; vendor preset: enabled)
   Active: active (running) since Wed 2022-12-14 19:00:57 UTC; 27s ago
 Main PID: 744 (crond)
   CGroup: /system.slice/crond.service
           └─744 /usr/sbin/crond -n
```

```bash
#add cron job for root user via vim
sudo crontab -e

#list cron jobs for the root user
sudo crontab -u root -l



# **_OUTPUT_**
*/5 * * * * echo hello > /tmp/cron_text
```

[< prev Day 5](day05.md)  |  [Home](../../..)  |  [Day 7 next >](day07.md)
