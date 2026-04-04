#BlockofKnowledge

```
logout

ssh -p 2220 bandit4@bandit.labs.overthewire.org
```
Password at [[level 3 – using ls & find to locate hidden files]] page

To be honest, I am puzzled what exactly this task was checking. Only readable file was one of those that I've checked. I did it by checking each one of them separetely. It did take 10 seconds through cat command. That's kinda it...

```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
_____
Probably, it was designed so could delve myself into how to use file command properly. By doing `file ./*`

- `file` → command that describes type of content inside file (not by it's description, but what actually is in the data).
- `./*` → is a template, which can be translated as "all files in that category" 
    - `.` = current folder
    - `*` = symbol-placeholder, it represents any kind of name
    - together with ./* gives list such as: `./-file00 ./-file01 ./-file02 ... ./-file09`.

So, command
`file ./*`
Is equal to:
`file ./-file00 ./-file01 ./-file02 ./-file03 ...`
_____


## Links:

[[level 5 - complex fin & file filters]]
[[Controlling Linux]]

Created: 2025-09-14 06:06