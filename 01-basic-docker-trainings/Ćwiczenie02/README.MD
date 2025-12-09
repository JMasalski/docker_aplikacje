# Basic docker trainging

## Ćwiczenie 2: Zmiana obrazów

### Przygotowanie środowiska

> Polecenie: `docker pull ubuntu:16.04`

![Screenshoot 12](scr12.png)


> Polecenie: `docker run -it ubuntu:16.04 /bin/bash`

```bash
ping google.com
```

![Screenshoot 13](scr13.png)

```bash
apt-get update
```

![Screenshoot 14](scr14.png)

```bash
apt-get install iputils-ping
```

![Screenshoot 15](scr15.png)


> Polecenie: `docker ps`

> Polecenie: ` docker commit 1faed708f67b kuba/ping:lates`

> Polecenie: `docker images`


![Screenshoot 16](scr16.png)


> Polecenie: `docker run -it kuba/ping /bin/bash`

```bash
ping google.com
```

![Screenshoot 17](scr17.png)
