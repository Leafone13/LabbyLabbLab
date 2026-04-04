#BlockofKnowledge

```
ssh -i ./sshkey.private bandit14@localhost -p 2220
```

This way we get to level 14. In level 13 task we received location of the password that level 14 can read. So we can read it and use output to proceed with nc connection, which is used for raw network tasks.

```
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```







## Links:
[[Open SSL]]
[[Overthewire]]
[[level 15 - using openssl to retrieve password]]

Created: 2025-09-19 05:01