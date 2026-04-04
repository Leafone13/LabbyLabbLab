#BlockofKnowledge

We do same things: download git...
```bash
git clone -c core.sshCommand="ssh -p 2220" bandit30-git@localhost:/home/bandit30-git/repo
```

...check it...
```bash
**bandit30@bandit**:**/tmp/tmp.wTXxe4dN8R/repo**$ ls -la

total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Oct 10 02:16 **.**
drwx------ 3 bandit30 bandit30 4096 Oct 10 02:15 **..**
drwxrwxr-x 8 bandit30 bandit30 4096 Oct 10 02:16 **.git**
-rw-rw-r-- 1 bandit30 bandit30   30 Oct 10 02:16 README.md

**bandit30@bandit**:**/tmp/tmp.wTXxe4dN8R/repo**$ git log

commit de654f201881f820c364f176ffcdea2876431bee (**HEAD** -> **master**, **origin/master**, **origin/HEAD**)
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:14 2025 +0000

    initial commit of README.md
**bandit30@bandit**:**/tmp/tmp.wTXxe4dN8R/repo**$ man git
**bandit30@bandit**:**/tmp/tmp.wTXxe4dN8R/repo**$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

We don't see any clue here with all previous steps used.
Now we can use git tag as new approach:
```bash
git tag
# secret
```

Output shows secret. Lets open it.

```bash
git show secret
# fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```




```
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```
















## Links:
[[level 31]]

Created: 2025-10-10 02:49