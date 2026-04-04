#BlockofKnowledge

After we reached that level we can see in 
```bash
ls -la
### output that leads to 
### bandit27-do with rights: -rwsr-x---
### s meaning that it can execute commands from another used, which is bandit27

strings bandit27-do
### Run a command as another user.
### Example: %s id
### /usr/bin/env
```

Which means we can execute needed commands through it.
```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

Leads us to password:
```
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```




___
Additions:
```bash
#To leave more
Q - quit
q - quit

#To terminate SSH
~.
```






## Links:
[[Terminate SSH immedietly]]
[[level 27]]

Created: 2025-10-09 04:29