
#BlockofKnowledge

ROT13 caesar code.

```
strings data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
Correct version, gave me password

```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```




This one is wrong:
```
strings data.txt | tr 'A-Za-z' 'N-Zn-zA-Ma-m'
```

Because A & a or Z & z are from different registers.
One can't apply them in wrong order, command will not read that properly. 





## Links:

[[level 12 - hex reverse & multi-layer archives]]

Created: 2025-09-18 03:26