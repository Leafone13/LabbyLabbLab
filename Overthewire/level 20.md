#BlockofKnowledge

 На этом уровне есть исполняемый файл `suconnect`, который подключается к `localhost:<port>` по TCP.  Мы это выяснил введя `./suconnect`
 Если на стороне слушателя прислать **текущий** пароль (пароль от этого уровня), `suconnect` вернёт **пароль следующего** уровня в stdout. 
 ____
Creating console 
 ```
 tmux
 ```
Dividing vertically
```
Ctrl+b %
```


Choosing free port (>1024)
```bash

# As an example 54321
# Checking if it is free:

ss -ltn | grep 54321 || echo "port 54321 is free"

```

One of the panels we use for listening:

```bash
nc -l 54321
```
It will await for our response.

Second panel:

```bash
./suconnect 54321
```


Password:
```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

- Остановить `nc`: `Ctrl+C` в левой панели.
- Если `suconnect` всё ещё висит — `Ctrl+C` в правой панели.
- Выйти из tmux: `exit` в каждой панели или `Ctrl+b d` чтобы отсоединиться.
- При желании убить все сессии tmux:
`tmux kill-server`











## Links:
[[level 21]]


Created: 2025-09-27 04:51