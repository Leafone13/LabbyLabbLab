#BlockofKnowledge


We're in shell-trap. It always changes our writings in caps, which excludes any agency.

Bash manual:
```
`$0` Expands to the name of the shell or shell script. This is set at shell initialization. 

If Bash is invoked with a file of commands (see Section 3.8 [Shell Scripts], page 39), `$0` is set to the name of that file. 

If Bash is started with the `-c` option (see Section 6.1 [Invoking Bash], page 80), then `$0` is set to the first argument after the string to be executed, if one is present.
```


=>
```bash
$0

ls -la
## total 36
## drwxr-xr-x   2 root     root      4096 Aug 15 13:16 .
## drwxr-xr-x 150 root     root      4096 Aug 15 13:18 ..
## -rw-r--r--   1 root     root       220 Mar 31  2024 .bash_logout
## -rw-r--r--   1 root     root      3851 Aug 15 13:09 .bashrc
## -rw-r--r--   1 root     root       807 Mar 31  2024 .profile
## -rwsr-x---   1 bandit33 bandit32 15140 Aug 15 13:16 uppershell

id
## uid=11033(bandit33) gid=11032(bandit32) groups=11032(bandit32)

cat /etc/bandit_pass/bandit33
## tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```






Password:
```
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```







## Links:



Created: 2025-10-10 05:02