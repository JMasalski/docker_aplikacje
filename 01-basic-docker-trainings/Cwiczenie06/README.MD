# Basic docker trainging

## Ćwiczenie 6: Sieci

### Listowanie sieci

> Polecenie: `docker network ls`

![Screenshot01](scr01.png)

> Polecenie: `docker run --rm -d --name dummy kuba/ping:1.0`

> Polecenie: `docker network inspect bridge`

![Screenshot02](scr02.png)

> Polecenie: `docker run --rm -d -e PING_TARGET=172.17.0.2 --name pinger delner/ping:1.0`

> Polecenie: `docker logs pinger`

![Screenshot03](scr03.png)
*Ping po IP*

![Screenshot04](scr04.png)
*Ping po nazwie kontenera*

### Zarządzanie sieciami własnymi

> Polecenie: `docker network create skynet`

> Polecenie: `docker network ls`

![Screenshot05](scr05.png)
![Screenshot06](scr06.png)

> Polecenie: `docker run --rm -d --network skynet --name dummy delner/ping:1.0`

> Polecenie: `docker run --rm -d --network skynet -e PING_TARGET=dummy --name pinger delner/ping:1.0`

> Polecenie: `docker logs pinger`

![Screenshot07](scr07.png)

### Połączenia między kontenerami w sieci

> Polecenie: `docker run --rm -d --name widgetdb --network skynet -e POSTGRES_PASSWORD=secret -p 5432 postgres`

> Polecenie: `docker run --rm -d --name gadgetdb --network skynet -e POSTGRES_PASSWORD=secret -p 5432 postgres`

![Screenshot08](scr08.png)

> Polecenie: `docker exec -it widgetdb /bin/bash`

```bash
psql -U postgres
\q
```
```bash
psql -U postgres -h gadgetdb
\q
```

![Screenshot09](scr09.png)

### Mapowanie portów na hosta


> Polecenie: `docker run --rm -d --name widgetdb --network skynet -e POSTGRES_PASSWORD=secret -p 5432:5432 postgres`

> Polecenie `docker exec -it widgetdb /bin/bash`

```bash
psql -U postgres -h localhost
\q
```
![Screenshot10](scr10.png)