#BlockofKnowledge

```bash
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.
```

```bash
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
```
Didn't work. I had to specify -p 2220 somehow.
Turned out it can be done this way:

```bash
git clone -c core.sshCommand="ssh -p 2220" bandit27-git@localhost:/home/bandit27-git/repo
```

```bash
ls -la
#repo directory
cd repo
ls -la
#README file
cat README
```

Password:
```
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```












## Links:
[[level 28]]


Created: 2025-10-09 04:53