#BlockofKnowledge

First step was to `ls -la` and to find out that we have ssh.key for the next level.

```bash
ssh -p 2220 bandit26@localhost -i bandit26.sshkey
```

It turns out that it logs you out after an attempt to do so.
The reason for that can be found in files and task

```
The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.
```

To find out we can read logs of connection failure, /usr/bin/showtext is named to be the reason for that issue.

```bash
cat /usr/bin/showtext
#!/bin/sh
export TERM=linux more
more ~/text.txt
exit 0
```

After googling out I've discovered that `more` is the secret entrance. More works in a specific way: it does read everything like cat, however, it does it in interactive format. The text is spreaded amongst many pages which you can switch via spacebar. Given that you are in the situation when text was not able to be shown on the same page.

=> the fix was to make window smaller.

Right after the same command worked without logging as out
```bash 
ssh -p 2220 bandit26@localhost -i bandit26.sshkey
```
because more ~/text.txt command from the bash script was not finished.

The next step was to open text editor, very specific one called vim. We do it by pressing hotkey for ''visualisation'', which is double v. It opened vim. And vim, in turn, has opportunity to open shell from itself. 

```bash
:set shell=/bin/bash #(original one was not bin/bash, you can find it here in cat /etc/passwd <</usr/bin/showtext>>
```
After that we just need to use command :shell and we can get password from typical location
```bash
cat /etc/bandit_pass/bandit26
```

```bash
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```




## Links:
[[level 26]]


Created: 2025-10-05 02:40