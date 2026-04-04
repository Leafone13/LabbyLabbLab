#BlockofKnowledge
```
logout
ssh -p 2220 bandit7@bandit.labs.overthewire.org
```
Password at [[level 6 – using find to match user, group & size]]

This time I had to search for a password in a file.
I had to google how grep command is used

My final command was:
```
grep ''millionth'' data.txt
```

This way I found out password:.
```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

Addition:
I also was curious why only 1 line was showed. And found out that you can manipulate the output to show lines that are after and before the target.

```
grep -A 2 -B 2 ''millionth'' data.txt
==============
journeys P5o7ERLZqmxrzBnQj3jF5GWDNIQ6kYCx
===
outstrips 4gKYDGeug4XGlRwALX2IJ30rOZuYauyP
===
>> target << **millionth** dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc 
===
mercurial I7tYVpz7qhFZEQFiXG6MoTMXdiwL10Q0
===
Maude GaxCglGXDNyyPFQl1DyseXDaaLE89B1O
```
I could also use `-C 2` for the same output as combining A and B. 
A is for after the target
B is for before the target





## Links:
[[level 8 - using sort, uniq & grep to count unique lines]]


Created: 2025-09-16 02:31