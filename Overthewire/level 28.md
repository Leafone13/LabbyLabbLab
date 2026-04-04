#BlockofKnowledge

We continue to work with git. This time we see that in readme file there's same readme, which doesn't have password. If we check git log using command "git log" - we'll see that one of the commit adds missing data. 

```bash
bandit28@bandit:**/tmp/tmp.YtU2qYeVgV/repo**$ git log
.
. 
.
commit 710c14a2e43cfd97041924403e00efb00b3a956e (**HEAD** -> **master**, **origin/master**, **origin/HEAD**)
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000
    fix info leak
commit 68314e012fbaa192abfc9b78ac369c82b75fab8f <<< <<< <<< <<< <<< <<< 
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000
    add missing data
commit a158f9a82c29a16dcea474458a5ccf692a385cd4

Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000
    initial commit of README.md
```


We can return repository to previous version, we just need to specify commit ID
```bash
bandit28@bandit:/tmp/tmp.YtU2qYeVgV/repo$ git checkout 68314e012fbaa192abfc9b78ac369c82b75fab8f

Note: switching to '68314e012fbaa192abfc9b78ac369c82b75fab8f'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.
If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:
  git switch -c <new-branch-name>
Or undo this operation with:
  git switch -
Turn off this advice by setting config variable advice.detachedHead to false
HEAD is now at 68314e0 add missing data

```

We can double check the result:
```bash
bandit28@bandit:/tmp/tmp.YtU2qYeVgV/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Oct  9 03:01 **.**
drwx------ 3 bandit28 bandit28 4096 Oct  9 02:57 **..**
drwxrwxr-x 8 bandit28 bandit28 4096 Oct  9 03:01 **.git**
-rw-rw-r-- 1 bandit28 bandit28  133 Oct  9 03:01 README.md
```

And then check if result is sufficient:
```bash
bandit28@bandit:/tmp/tmp.YtU2qYeVgV/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.
## credentials
- username: bandit29
- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```


Password:
```
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```




## Links:
[[level 29]]


Created: 2025-10-09 05:01