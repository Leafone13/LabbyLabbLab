#BlockofKnowledge

This one was funny. They don't explain that you have to logout again, because it kinda have to be obvious. I didn't get in the beginning and permission to the file was denied.

So first of all is 
```
logout
```

The next step is to get inside the new user, this time it is bandit2 (since we need to go to the corresponding folder, which was mentioned in the task itself).

```
ssh -p 2220 bandit2@bandit.labs.overthewire.org
```
The password comes from [[level 1 - reading files with ''-'' in name]]

After that there is another file to read in bandit2 folder.

pwd - to check where we are (i think we start at needed folder)
ls - --there is file with spaces-- or whatever it's called.
In order to open such files you have to either write it comas ''there is file with spaces'' 
or use '' \ '': there\ is\ file\ with\ spaces
I prefer second option but both can be used in different scenarios.

So my command looked as follows

```
cat ./--spaces\ in\ this\ filename--
```

The new password is:
```
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```











## Links:

[[level 3 – using ls & find to locate hidden files]]
[[Controlling Linux]]

Created: 2025-09-14 01:55