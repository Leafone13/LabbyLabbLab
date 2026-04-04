#BlockofKnowledge





```
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```






```bash
By using the “git add” command we instruct git what files need to be added into the staging area. The “.” means add all files with changes. So we are telling git to add all files that have changed in the repository folder to the staging area.

**Note :** Files that have been deleted are also staged so that when we commit the changes git can figure out what files need to be deleted/ modified.

Next we are committing (adding/ deleting) files into the local copy of the repository. The “-m” flag is used to specify the commit message. If this flag is not specified then the default text editor will be opened using which we can add the commit message.

After performing the above two steps we have added the “key.txt” file and deleted the “.gitignore” file from the repository but the changes will only be reflected on our local copy. The remote copy is still untouched so to update the remote copy we make use of the “git push” command to which we specify the remote repository URL (by default saved in the variable “origin” for a repository that is cloned) and the branch to which we want to push the changes.

Once we pushed the changes to the remote repository we see that we are given the password for the next level
```





## Links:
[[level 32]]


Created: 2025-10-10 04:50