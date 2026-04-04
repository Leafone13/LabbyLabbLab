
#BlockofKnowledge

The first task was to connect to SSH.
However, it is not something I got used to while I was installing Arch
There are few more variables to consider

Initially task is formulated as follows:

```
The host to which you need to connect is 
/// bandit.labs.overthewire.org ///
on port 2220 

The username is /// bandit0 /// 
and the password is /// bandit0 ///
```

I used to login through IP address because it was local network. Now I am connective to website itself with predefined Port and User.

For that I had to use this command as follows:

ssh -p 2220 bandit0@bandit.labs.overthewire.org

`I was confused by port and user; since guides mention that -u prefix is used for that issue. However, it was not needed. Need to understand why`








## Links:
[[Linux Node]], [[LinuxToDo]], [[level 0 – using ssh to connect with port & user]]

Created: 2025-09-14 01:28