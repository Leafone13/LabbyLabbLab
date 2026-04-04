
#BlockofKnowledge

And again, first of all is:
```
logout
```

This time it is bandit3 
```
ssh -p 2220 bandit3@bandit.labs.overthewire.org
```
The password comes from [[level 2 - reading files with space in name]]

When you're inside ls will show you nothing. This time you have to cfind and observe files that are hidden in linux. Files are considered hidden if they have . in the beginning of their name.
As such, there are many ways of solving this assignment:

```
ls -la                                        -         It will show all directories with rights, owners, date and size of repositories

ls -d .*                                     -         It will show all directories that are starting with "."
```
This will show directory "Inhere", cd in there, ls -a in there, cat the file you'll get password

One could also do it through "find" command:
```
find . -name ".*"                            -         It will show all hidden files in directory you're currently in & deeper

find . -type -f -name ".*"                   -         It will show all hidden files in directory you're  currently in and ignore directories

find . -name ".*" ! -name "." ! -name ".."   -         It will show all hidden files, but will also ignore "." and ".." files (those are service-related)

```


One way or another, cat the file and lets move to the next


___

find -type (code)

- `f` → regular file
- `d` → directory
- `l` → symbolic link
- `c` → character device
- `b` → block device
- `s` → socket    
- `p` → named pipe (FIFO)

-executable 
for exe





Psswrd:
```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```











## Links:
[[how to read files without cd]]
[[level 4 – using file to find human-readable text]]
[[Controlling Linux]]

Created: 2025-09-14 02:18