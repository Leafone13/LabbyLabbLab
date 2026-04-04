#BlockofKnowledge

Whenever I try to ssh login to the level 18 it prints out message ''byebye'' and logouts.
It turned out that if I try to use command in input - it will be able to print out the output before logging me out.

```
ssh -p 2220 bandit18@bandit.labs.overthewire.org 'ls -la'
```

This way I saw that there's a readme file.

```
ssh -p 2220 bandit18@bandit.labs.overthewire.org 'cat readme'
```

I've opened it before getting kicked out and it gave me a password:

```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```



___
The reason why it logs me out is that someone has modified `.bashrc` which reacts whenever anybody logs in with SSH.




## Links:
[[Overthewire]]
[[level 19]]


Created: 2025-09-26 02:42