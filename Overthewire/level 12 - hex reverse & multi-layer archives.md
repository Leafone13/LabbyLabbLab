#BlockofKnowledge


That level introduces us with hex-dump. 

As such, we can see that according to task

```
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
```

We can only take the file data.txt and to ''revert'' it back to binary.
For that I used following command: 

`xxd -r data.txt BinaryData`
	`xxd - name of utility`
	`-r for Reverse; return to binary` 
	`data.txt - name of the file that needs a change`
	`BinaryData - output`

_____
Next step is to understand what we've got, because that binary, according to task, have been several times decompressed. 

`file BinaryData`
```
BinaryData: gzip compressed data, was "data2.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 584
```

As such we see, that gzip was used to compress the file, original name was ''data2.bin'', max compression was applied, made by unix.

_______
### Chain of steps

The path was **multi-layered**, like nested dolls:
1. `xxd -r` → restore binary from hexdump.
2. `file` each step to identify the type.
3. Unpack accordingly:
    - `gzip -d` / `zcat`
    - `bzip2 -d`
    - `tar -xf`
4. Repeat until reaching ASCII text.

---

### Difficulties

- Confusion with suffixes (`.gz`, `.bz2`) → needed `-k` and `-c` flags to keep originals or redirect output.    
- Mixing up commands (`gzip` vs `zcat`, `tar` on wrong type).
- Handling filenames with spaces — had to use quotes or backslashes.
- Many false outputs (empty files) when redirect was misused.

### Final

After peeling off all layers:
`strings data8.bin.gzip.out`
Password revealed:

```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```


____

```
# 1. revert hex → binary
xxd -r data.txt BinaryData
file BinaryData
# → gzip compressed data, was "data2.bin"

# 2. decompress gzip
gzip -dk BinaryData
file BinaryData
# → BinaryData.gz (gzip)

# 3. zcat to new file
zcat BinaryData.gz > UnarchivedBzh
file UnarchivedBzh
# → gzip compressed data, was "data2.bin"

# 4. bzip2
bzip2 -k -d UnarchivedBzh
file UnarchivedBzh.out
# → gzip compressed data, was "data4.bin"

# 5. gzip again
gzip -dc UnarchivedBzh.out > "6 ArtifactOutBzip2"
file "6 ArtifactOutBzip2"
# → gzip compressed data, was "data4.bin"

# 6. gzip again
gzip -dc "6 ArtifactOutBzip2" > "7 ArtifactBzipGzip"
file "7 ArtifactBzipGzip"
# → POSIX tar archive

# 7. prepare dir
mkdir Tar
cp "7 ArtifactBzipGzip" Tar/POSIXTAR
cd Tar

# 8. tar
tar -xf POSIXTAR
file data5.bin
# → POSIX tar archive

# 9. tar again
tar -xf data5.bin
file data6.bin
# → bzip2 compressed data

# 10. bzip2
bzip2 -k -d data6.bin
file data6.bin.out
# → POSIX tar archive

# 11. tar again
tar -xf data6.bin.out
file data8.bin
# → gzip compressed data, was "data9.bin"

# 12. gzip final
gzip -dc data8.bin > data8.bin.gzip.out
file data8.bin.gzip.out
# → ASCII text

# 13. find password
strings data8.bin.gzip.out

```
## Links:
[[HexDump]]
[[Magical Signature]]
[[level 13, 14 - ssh private key login & password retrieval through nc utility]]


Created: 2025-09-18 04:00