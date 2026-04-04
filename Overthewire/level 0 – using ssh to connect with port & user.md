
#BlockofKnowledge

First level is just to read the file in home directory.

pwd - to check where you are
cat readme - to read the only file in /home directory (that's occasionally where you begin)

They've asked to write down the password somewhere.
They change occasionally though, so it's a subject to change in the future:

```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

After that one need to perform another SSH login, but this time to bandit1 user.
For that I needed to logout first
```
logout
```

After that the command looks as follows:

```
ssh -p 2220 bandit1@bandit.labs.overthewire.org
```

The password is needed to enter





## Links:
[[level 1 - reading files with ''-'' in name]]
[[Overthewire]]

Created: 2025-09-14 01:42