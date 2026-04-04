#BlockofKnowledge

I have to use setuid for that task, which gives temporary permission for file usage, that allows users, that do not have rights, to use certain programmes with needed authority.

```
ssh -p 2220 bandit19@bandit.labs.overthewire.org 'ls -a'
```

This way I found exec file `bandit20-do`
I've tried to exec it, but it showed me request of an ID.

```
ssh -p 2220 bandit19@bandit.labs.overthewire.org './bandit20-do id'
```
This way I learned it's UID `11020`. Wasn't useful, though, only allowed me to investigate mistakes and current situation (id command shows your current rights and I could confirm that I didn't get rights for upcoming commands, unless I did it through that specific file)

```
ssh -t -p 2220 bandit19@bandit.labs.overthewire.org
```

Interactive shell allowed me to stay there in sort of a ''room'' that is hidden from logout sequence.
From there I was able to do this:

```
/home/bandit19/bandit20-do cat /etc/bandit_pass/bandit20
```

Which gave me password:

```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```








## Links:
[[Overthewire]]
[[level 20]]



Created: 2025-09-26 02:55