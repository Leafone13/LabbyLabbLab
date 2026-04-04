
#BlockofKnowledge

```
sort data.txt | uniq -c | grep '^ *1'
```
I had to find a string that appearing only 1 time.
I chose `sort` - group identical lines in alphabetical order
`| uniq -c` count the output, how many of them coming in a row if order is alphabetical
`| Grep '^ *1'` - take that output and show only those that have 1 in the beginning.

Output provided tons of lines, I had to decrease their amount. I found out that most of them are 10 and only one is repeated once. So I decided to provide the opposite output by adding -v and putting 10, instead of 1.

`sort data.txt | uniq -c | grep -v '^ *10'`

Now the result is one line:

```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```






## Links:
[[level 9 - using strings to find text]]


Created: 2025-09-16 02:57