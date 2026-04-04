
#BlockofKnowledge

```
logout
ssh -p 2220 bandit6@bandit.labs.overthewire.org
```
Password at [[level 5 - complex fin & file filters]]

This time I had to find file in the whole directory. 
Criterias this time are:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

I knew how to manage bytes thing, but I didn't know about user

In the end I come up with the following command:

```
find . -user bandit7 -group bandit6 -size 33c -exec file {} \; | grep "text"
```
It showed me a lot of text and one I needed was highlighted by red colour.
I just needed to double check does it really belong to this group and criterias:

```
stat -c '%U %G %s %n' /var/lib/dpkg/info/bandit7.password
```
Out put showed that it does indeed.
After that I had to read it

```
 strings /var/lib/dpkg/info/bandit7.password
```

and I received password: 

```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```






## Links:
[[level 7 – using grep to search file content]]
[[Overthewire]]

Created: 2025-09-16 01:30