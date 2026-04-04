#BlockofKnowledge

```
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
```

In this assignment I did the following:

``` bash
cd /etc/cron.d/
ls -a
# found cronjob_bandit23.sh in output

strings /usr/bin/cronjob_bandit23.sh

### !/bin/bash
### myname=$(whoami)
### mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
### echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
### cat /etc/bandit_pass/$myname > /tmp/$mytarget
```

Reading this I understood that my answer is hidden through whoami decypher.
I've tried to use that command and echo it

```bash
echo mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
### mytarget=7db97df393f40ad1691b6e1fb03d53eb
```

I've checked the direction, but of course it was wrong: after all, my whoami is bandit 22 & not 23. However, I could replicate that name in another approach:

```bash
echo "I am user bandit23" | md5sum | cut -d' ' -f1
# 8ca319486bfbbc3663ea0fbe81326349
```
Which leads me to password area:

```bash
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

Password:
```
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

## Links:
[[Overthewire]]
[[level 23]]


Created: 2025-09-29 04:08