#BlockofKnowledge
```
logout
ssh -p 2220 bandit5@bandit.labs.overthewire.org
```
Password at [[level 4 – using file to find human-readable text]]
____
This time I have to find a file that has password, which possess following qualities:
- human-readable
- 1033 bytes in size
- not executable

___
I've tried to use `find . -size 1033b` but output was empty.
It turned out that in Linux it doesn't make a lot of sense to look for exact number, especially in bytes.  `find . -size -1034` is more preferable. 

So I've tried to make it look in diapason `find . -size -1035b -size +1019b` , but out was empty.
It turned out that b doesn't stand for bytes, b is block, and c is bites.
`find . -size 1033c` - gave me list of files, so I had to apply other qualities.

``find . -type f ! -executable -size 1033c``
lead me to 
./maybehere07/.file2
_____
```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```




I could also try to find by  human-readable quality.
### . `-exec file {} \;`
- `-exec` позволяет выполнить команду для каждого найденного файла.
- `file {}` — здесь `file` проверяет файл на тип содержимого.  
    (`{}` подставляется имя файла, мол, сюда его закинь пожалуйста говоришь кампутеру)
- `\;` завершает блок `-exec`.

The final command would look this way:

```
find . -type f -size 1033c ! -executable -exec file {} \; | grep "text"
```




## Links:
[[level 6 – using find to match user, group & size]]
[[Controlling Linux]]

Created: 2025-09-15 03:08