#BlockofKnowledge

```bash
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```

```bash
mb

**OUTFILE**="/tmp/MyFirstBashScript/listing.txt"
**TARGETDIR**="/var/spool/$myname/foo"
**COPYDIR**="/tmp/MyFirstBashScript/STOLEN_GOODIES_FOR_MASTER"

if [ ! -d "$TARGETDIR" ]; then
    echo "MASTER, I've failed YOU... I am not allowed in $TARGETDIR!"
    exit 1
fi
  
if ls -la "$TARGETDIR" > "$OUTFILE"; then
       echo "Script Served you WELL, Master. Check $OUTFILE. Me go for goodies now..."
          mkdir -p "$COPYDIR"
          cp -r "$TARGETDIR"/* "$COPYDIR" 2>/dev/null || echo "MASTER, there were no goodies to steal..."
          echo "MASTER, GOODIES belong to YOU! Check $COPYDIR, right in your Chambers!"
       else 
           echo "MASTER, they don't gimme the GOODIES. Me do Better next time..."
       exit 1
fi
```


```bash
!/bin/bash

**OUTFILE**="/tmp/MyFirstBashScript/listing.txt"
**TARGETFILE**="/etc/bandit_pass/bandit24"
**COPYDIR**="/tmp/MyFirstBashScript/STOLEN_GOODIES_FOR_MASTER"

if [ ! -f "$TARGETFILE" ]; then
  echo "MASTER: target file not found: $TARGETFILE" >&2
  exit 1
fi

if /bin/cat "$TARGETFILE" > "$OUTFILE" 2>/dev/null; then
  echo "Script Served you WELL, Master. Check $OUTFILE. Me go for goodies now..."
  /bin/cp -a "$OUTFILE" "$COPYDIR/" 2>/dev/null \
    || echo "MASTER, could not copy to $COPYDIR but file is at $OUTFILE"
  exit 0
else
  echo "MASTER, I couldn't read $TARGETFILE" >&2
  exit 1
fi
```


```bash
  

#!/bin/bash
**OUTFILE**="/tmp/MyFirstBashScript/listing.txt"
**TARGETFILE**="/etc/bandit_pass/bandit24"
**COPYDIR**="/tmp/MyFirstBashScript/STOLEN_GOODIES_FOR_MASTER"

if [ ! -f "$TARGETFILE" ]; then
  echo "MASTER, I've failed YOU... I am not allowed to read $TARGETFILE!" >> "$OUTFILE"
  exit 1
fi

if /bin/cat "$TARGETFILE" > "$OUTFILE" 2>/dev/null; then
  echo "MASTER, Script served you WELL. Check $OUTFILE. Me go for goodies now..." >> "$OUTFILE"
  /bin/cp -a "$OUTFILE" "$COPYDIR/" 2>/dev/null \
    && echo "MASTER, GOODIES belong to YOU! Check $COPYDIR, right in your Chambers!" >> "$OUTFILE" \
    || echo "MASTER, there were goodies to steal but they give me no goodies to copy. What was inside the goodies you see here $OUTFILE" >> "$OUTFILE"
  exit 0
else
  echo "MASTER, they don't gimme the GOODIES. Me do Better next time..." >> "$OUTFILE"
  exit 1
fi
```


```
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```





## Links:
[[level 24]]


Created: 2025-09-29 04:44