#BlockofKnowledge

```
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
```

As described in the task, **cronjobs** are programs running automatically at regular intervals. In Linux, there are multiple folders that can contain these cronjobs: cron.d, cron.daily, cron.hourly, cron.monthly, crontab, cron.weekly. The folders contain files with instructions on how the programs are run. It starts with the first five columns, which indicate at what time/interval the program should be done. Next is the command/program that is to be executed.

As such, we have to find that programme
``` bash
ls -a /etc/cron.d

-rw-r--r--   1 root root   120 Aug 15 13:16 cronjob_bandit22
```

If we try to take a look what's inside:
``` bash
strings cronjob_bandit22

@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```
Five stars indicate the occurance (every minute, every day, every week, every month)

```bash
strings /usr/bin/cronjob_bandit22.sh

#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

So, as we can see it reads file and puts it's output to specific direction. 
If we check it's rights, we'll see that everybody can read it => we can read the output of the bandit22, which is, indeed, our password

```bash
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

Password:
```
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```














## Links:
[[level 22]]


Created: 2025-09-29 02:29