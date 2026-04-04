#BlockofKnowledge

`nmap -p31000-32000 localhost`
To check which port is open:
```
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown
```

We found out that all these ports are open for listening.
Now we need to check which of those speak SSL/TLS:
```
openssl s_client -connect localhost:31046
openssl s_client -connect localhost:31518
openssl s_client -connect localhost:31691
openssl s_client -connect localhost:31790
openssl s_client -connect localhost:31960

31790 | 31518 - showed certificates output => they're what we need (otherwise it leads to an error output)
```

We need to send `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx` (passwd from previous level), if they return password back (echo) means it not what we're looking for.

```
printf "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx\n" | openssl s_client -connect localhost:31790 -quiet
```

We receive a huge SSH key.

```
mkdir /tmp/mykeyyesmy
cd /tmp/mykeyyesmy

printf "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx\n" | openssl s_client -connect localhost:31790 -quiet > /tmp/mykeyyesmy/my.key

ssh -i /tmp/mykeyyesmy/my.key -p 2220 bandit17@localhost
```

## Проблемы, с которыми столкнулись (и решения)
- **Шумный вывод TLS / KEYUPDATE** мешал увидеть ключ → помог `-quiet`.
- **Сначала заходил на порт 22 по умолчанию** → нужно явно `-p 2220`.
- **Кривой ключ в файле (обратные слэши, мусор)** из-за захвата шума → решение: заново сохранить с `-quiet` или вырезать чистый PEM:
    `... | sed -n '/BEGIN RSA PRIVATE KEY/,/END RSA PRIVATE KEY/p' > my.key`
- Предупреждения `self-signed certificate`, `Can't use SSL_get_servername` — **нормально** для задания.


## Links:

[[level 17]]
[[Overthewire]]

Created: 2025-09-20 04:02